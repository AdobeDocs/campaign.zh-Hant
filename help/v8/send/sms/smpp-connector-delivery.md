---
title: 傳遞屬性中的SMPP聯結器
description: 關於傳遞中SMPP聯結器的設定
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 704e151a-b863-46d0-b8a1-fca86abd88b9
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 5%

---

# SMPP聯結器說明 {#smpp-connector-desc}

>[!IMPORTANT]
>
>本檔案適用於Adobe Campaign v8.7.2和更新版本。 若要從舊版切換至新的SMS聯結器，請參閱此[技術檔案](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}。
>
>若為舊版，請閱讀[Campaign Classic v7檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## SMS聯結器資料流程 {#sms-data-flow}

本節說明SMS程式如何處理資料。

以下是SMS流程與環境互動概覽的高階區塊圖。

![](assets/smsv2_highlevel.png){zoomable="yes"}

SMS流程託管2個重要元件：處理與SMPP提供者通訊的SMPP聯結器本身，以及SR調解的背景工作。

### SMPP帳戶的資料流 {#sms-data-flow-smpp-accounts}

SMS程式會輪詢nms：extAccount並在其SMPP聯結器中衍生新連線，傳遞每個帳戶的設定。 可以在&#x200B;*configRefreshMillis*&#x200B;設定的serverConf中調整輪詢頻率。

對於每個作用中的SMPP帳戶，SMPP聯結器會嘗試一直保持連線作用中。 如果連線中斷，它會重新連線。

### 傳送訊息時的資料流程 {#sms-data-flow-sending-msg}

* SMS程式會透過掃描nms：delivery來選取作用中傳送。 傳送在下列情況下為作用中：
   * 其狀態表示可以傳送訊息
   * 其有效期未過期
   * 這實際上是一種傳遞（例如，它不是範本，不會刪除）
   * SMPP聯結器可以為連結到傳遞的外部帳戶開啟至少一個連線
* 對於每個傳遞，SMS流程會載入傳遞部分。 如果傳送部分已部分傳送，SMS程式會檢查廣泛記錄檔以檢查已傳送的訊息。
* SMS程式會使用傳送部分的個人化資料來展開範本。
* SMPP聯結器會產生符合內容和其他設定的MT (SUBMIT_SM PDU)。
* SMPP聯結器會透過傳送器（或收發器）連線傳送MT。
* 提供者會傳回此MT的ID。 它會插入到nms：providerMsgId中。
* 簡訊程式會將廣泛記錄更新為已傳送狀態。
* 在最終錯誤的情況下，SMS流程會相應地更新廣義記錄，並且可能會在nms：broadLogMsg中建立新的錯誤。

### 接收SR時的資料流程 {#sms-data-flow-sr}

* SMPP聯結器會接收並解碼SR (DELIVER_SM PDU)。 它會使用外部帳戶中定義的規則集來取得訊息ID和狀態。
* 訊息ID和狀態會插入nms：providerMsgStatus
* 插入後，SMPP聯結器會以DELIVER_SM_RESP PDU回覆。
* 如果過程中發生任何錯誤，SMPP聯結器會傳送負DELIVER_SM_RESP PDU並記錄訊息。

### 接收MO時的資料流程 {#sms-data-flow-mo}

* SMPP聯結器會接收並解碼MO (DELIVER_SM PDU)。
* 關鍵字會從訊息中擷取。 如果它符合任何宣告的關鍵字，則會執行對應的動作。 它可以寫入nms：address以更新隔離。
* 如果宣告自訂TLV，則會根據其各自的設定進行解碼。
* 完全解碼和已處理的MO會插入nms：inSms表格中。
* SMPP聯結器會以DELIVER_SM_RESP PDU回覆。 如果偵測到任何錯誤，則會傳回錯誤碼給提供者。

### 協調MT和SR時的資料流程 {#sms-reconciling-mt-sr}

* SR調解元件會定期讀取nms：providerMsgId和nms：providerMsgStatus。 來自兩個表格的資料會連結。
* 對於在兩個表格中都含有專案的所有訊息，會更新相符的nms：broadLog專案。
* 如果偵測到新型別的錯誤，則可以在處理程式中更新nms：broadLogMsg表格，或者更新未手動限定的錯誤的計數器。

## 符合MT、SR和broadlog專案 {#sms-matching-entries}

以下圖表說明整個程式：

![](assets/message_processing.png){zoomable="yes"}

**階段1**

* 該訊息會進行掃描、格式化，然後傳輸至SMPP聯結器。
* SMPP聯結器會將其格式化為SUBMIT_SM MT PDU。
* MT會傳送給SMPP提供者。
* 提供者會以SUBMIT_SM_RESP回覆。 SUBMIT_SM與SUBMIT_SM_RESP會以其序號進行比對。
* SUBMIT_SM_RESP提供來自提供者的識別碼。 此ID會與廣義記錄ID一起插入nms：providerMsgId表格。

**階段2**

* 提供者會傳送DELIVER_SM SR PDU。
* 會剖析SR以擷取提供者ID、狀態和錯誤代碼。 此步驟使用擷取規則運算式。
* 提供者ID及其對應狀態會插入nms：providerMsgStatus。
* 將所有資料安全地插入資料庫時，SMPP聯結器會以DELIVER_SM_RESP回應。 DELIVER_SM與DELIVER_SM_RESP以它們的序號來比對。

**階段3**

* SMS程式的SR調解元件會定期掃描nms：providerMsgId和nms：providerMsgStatus表格。
* 如果任何資料列在兩個資料表中具有相符的提供者ID，則這2個專案會連結在一起。 這可讓廣泛的記錄檔ID （儲存在providerMsgId中）和狀態（儲存在providerMsgStatus中）相符
* 廣泛記錄檔會以對應的狀態更新。

## 相關性與專用程式聯結器 {#sms-affinities}

專用流程聯結器會忽略相關性，它只會在SMS流程中執行。

## serverConf選項 {#sms-serverconf-options}

某些設定可在serverConf.xml中調整。 就像這個檔案中的其他設定一樣，它應該在config-instance.xml檔案中指定。 所有設定都在&lt; mta2 >元素中。

此表格總結列出所有設定值。 最小/最大合理值可讓您大致瞭解在大多數情況下應該考慮的範圍。 偵錯值是在嘗試尋找與效能無關的問題時要選擇的值。

| 設定 | 說明 | 預設 | 最小合理值 | 最大合理值 | 偵錯值 |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | 更新微批次的大小 | 5000 | 100：極低延遲 | maxWaitingMessages/updateThreads：超過此值是無用的，因為maxWaitingMessages仍會限制緩衝 | 1：停用微批次處理程式，逐一更新訊息 |
| configRefreshMillis | 設定重新載入的期間 (以毫秒為單位) | 10000 | pollPeriodMillis：低延遲 | 600000：重新載入的速度不要太快，以儲存資源 | 500：低延遲可讓您更快速地嘗試新設定 |
| deliveryPartRetryCount | deliveryPart重試或延遲的最大次數。 注意：重新啟動傳送程式即計為重試，當機即計為重試。 | 20 | 1：停用重試 | 50：讓訊息更具持續性，以處理不穩定的提供者 | 1：停用重試。 1000：避免排清失敗的訊息。 |
| deliveryPartRetryDelaySeconds | 重試 deliveryPart 之前的最小延遲。這是跨處理序和跨容器的。延遲以秒為單位。 | 60 | 0：立即重試 | 3600：非常緩慢的重試（每次重試間隔1小時） | 1：讓在忙碌的記錄檔中輕鬆追蹤重試。 |
| logOutput | 在主要記錄檔輸出上傳送監視與設定檔資料。 | 真 | false：可能會增加一些輸送量。 不鼓勵您這麼做。 | true：啟用記錄。 | 真 |
| maxWaitingMessages | 隨時處理的訊息數上限 | 50000 | 256：足以容納單一deliveryPart | 200000：受SQL查詢長度限制(64k) | 1：逐一處理訊息 |
| pollPerioMillis | 資料庫輪詢頻率（以毫秒為單位）以檢查新訊息 | 2000 | 500：極低延遲 | 10000：較大的批次 | 500：低延遲可讓您輕鬆進行偵錯。 |
| prepareThreads | 訊息準備的執行緒數量 | 3 | 1：單一執行緒 | CPU數目。 請小心RAM的使用。 若增加到6以上，可能需要增加maxSMSMemoryMb、maxProcessMemoryAlertMb和maxProcessMemoryWarningMb | 1：單一執行緒產生更乾淨的記錄。 |
| profDeliveryStat | 記錄有關SMS程式內部的各種彙總統計資料 | 真 | false：可能會增加一些輸送量。 不鼓勵您這麼做。 | true：低詳細記錄檔 | 真 |
| profLogPerMessage | 記錄每則訊息的每個處理步驟 | 假 | false：減少記錄詳細程度。 | true：非常高的詳細記錄檔。 **只有在絕對必要時才使用**。 對效能有重大影響。 **收集到足夠的資料後，請立即停用此設定**。 | 真 |
| providerIdScanPeriod | 掃描要調解的新提供者ID之間的時段（以秒為單位） | 10 | 1：低延遲 | 60：更大的批次，以獲得更大的輸送量 | 1：低延遲有助於偵錯訊息處理。 |
| providerIdThreads | 用於調和提供者 ID 的執行緒數量。每個執行個體 1 個執行緒就足夠了。設定為 0 可在此容器上停用。 | 1 | 0：在此容器上停用 | 1 | 1 |
| sendingThreads | 傳送執行緒的數量 | 1 | 1：單一執行緒 | CPU數目。 太多執行緒通常會損害效能。 | 1：單一執行緒產生更乾淨的記錄。 |
| updateThreads | 用於更新資料庫的系線數目 | 1 | 1：單一執行緒 | CPU數目。 每個執行緒都會建立自己的DB連線。 | 1：單一執行緒產生更乾淨的記錄。 |
| verifymode | 模擬傳送訊息。 訊息實際上並未傳送。 對偵錯很有用 | 假 | 假 | 真 | false：正常執行系統。 true：僅測試DB存取和訊息準備。 |
