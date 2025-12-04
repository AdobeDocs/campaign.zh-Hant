---
title: 簡訊管道特性
description: 瞭解簡訊頻道的特性
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 1%

---

# 簡訊管道特性 {#sms-channel}

>[!AVAILABILITY]
>
>此功能適用於所有Campaign FDA環境。 **不**&#x200B;可用於Campaign FFDA部署。 本檔案適用於Adobe Campaign v8.7.2和更新版本。 若要從舊版切換至新的SMS聯結器，請參閱此[技術檔案](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>若為舊版，請閱讀[Campaign Classic v7檔案](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## 簡訊型別 {#sms-types}

透過SMS提供者傳送SMS時，您會遇到3種不同的SMS：

* **SMS MT （已終止行動裝置）**：這是Adobe Campaign透過SMPP提供者向行動電話發出的SMS。
* **SMS MO （行動原始）**：這是行動裝置透過SMPP提供者傳送給Adobe Campaign的SMS。
* **SMS SR （狀態報告）或DR或DLR （傳遞回條）**：這是行動裝置透過SMPP提供者傳送給Adobe Campaign的回條，表示已成功收到簡訊。 Adobe Campaign也可能收到指出訊息無法傳送的SR，通常附有錯誤說明。

您需要區分確認（RESP PDU，SMPP通訊協定的一部分）和SR。 SR是一種透過網路端對端傳送的SMS，而確認僅是確認一次傳送成功。

確認和SR都可以觸發錯誤，區分兩者有助於疑難排解。

### 簡訊所攜帶的資訊  {#sms-info}

簡訊包含的資訊多於文字。 以下是您可在SMS中找到的專案清單：

* 限制在140個位元組的文字，根據編碼方式，這表示70到160個字元之間。 請參閱下方的[SMS文字編碼](#sms-text-encoding)，以取得詳細資料和限制。
* 收件者地址，有時稱為ADC或MSISDN （「電話號碼」的技術名稱）。 這是將會接收簡訊的行動裝置號碼。
* 寄件者地址，可稱為oADC或有時稱為寄件者ID。 這可以是電話號碼（日間使用）、短代碼（透過提供者傳送時）或名稱（這是選用功能，在此情況下您無法回覆簡訊）。
* 指出訊息是否為快閃訊息的旗標（快閃訊息是未儲存在記憶體中的快顯視窗）
* 用於指示是否需要SR的旗標。
* 有效日期，在此日期之後不允許任何網路裝置重試（不一定會存在或遵守）。
* 一個data_coding欄位，表示文字的編碼。

## SMS文字編碼 {#sms-text-encoding}

>[!IMPORTANT]
>
>SMS編碼是一個龐大而複雜的主題，有許多陷阱和不合規的實施！

第一個規則是&#x200B;**如果出現編碼問題，請一律聯絡SMPP提供者**。 只有他們，才對其支援的編碼方式有確切的瞭解，且由於其技術平台的限制而可能適用的特殊規則。 讓他們檢查您傳送給他們的內容以及他們傳回給您的內容，這是成功且穩定互連的唯一途徑。

SMS訊息使用特殊的7位元編碼，通常稱為GSM7編碼。  Wikipedia有[篇關於它的好文章（英文GSM 03.38）](https://en.wikipedia.org/wiki/GSM_03.38)。

在SMPP通訊協定中，會將GSM7文字展開為每個字元8位元，以較容易進行疑難排解。 SMSC會將其封裝成每個字元7位元，再傳送給行動裝置。 這表示SMS的short_message欄位在SMPP框架中可能長達160位元組，而在行動網路上傳送時上限卻是140位元組（簡單地捨棄了最重要的位元）。

如果出現編碼問題，請檢查以下重要事項：
* 首先，請確定您知道哪些字元屬於哪種編碼。 GSM7由於其變音符號（重音符號）的部分支援而聲名狼藉。 尤其是在法文中，é和è是GSM7的一部分，但ê、â或ï卻不是。 西班牙文也是如此。
* 包含cedilla (c)的C在GSM7字母表中僅以大寫形式出現，但有些手機以小寫或「智慧」型大小寫呈現：一般建議是完全避免並移除cedilla （仍然可以法文讀取）或切換至UCS-2。
* **請勿在簡訊中使用ASCII！**，除非SMPP提供者明確要求：此編碼會浪費空間，因為它有8位元字元且覆蓋範圍比GSM7少。 CDMA網路（用於北美）可能需要此編碼。
* 不一定會支援Latin-1。 在嘗試使用Latin-1之前，請檢查與您的SMPP提供者的相容性。
* Adobe Campaign聯結器不支援國家語言轉換表。 您必須改用UCS-2或其他data_coding。
* UCS-2和UTF-16經常被手機混合使用。 對於傳送表情符號和其他UCS-2中不存在且很少使用的字元的人來說，這是一個問題。
* 只有舊版手機沒有所有UCS-2字元的字型字元。 最新版的智慧型手機往往能夠輕鬆顯示稀有字元，舊版的智慧型手機通常缺少許多表情符號，而且功能非常陳舊的手機通常只支援購買時所在國家的母語有用的功能。 如果您想要使用某種表情符號或ASCII-art，請在傳送前於各種手機上測試。 促銷活動預覽不會模擬缺少的字元，且將顯示在顯示預覽的網頁瀏覽器上可用的任何符號。

*data_coding*&#x200B;欄位會說明使用哪種編碼。 主要問題是值0表示規格中的&#x200B;*預設SMSC編碼*，通常表示GSM7，但情況並非總是如此。 向編碼與data_coding = 0關聯的SMPP提供者查詢。 其他data_coding值通常遵循規格，但唯一能確定的方法是向SMPP提供者查詢。

訊息的大小上限取決於其編碼。 下表總結了所有相關資訊：

| 編碼 | 通常的data_coding | 訊息大小（字元） | 多部分SMS的部分大小 | 可用字元 |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | GSM7基本字元集+擴充功能（擴充字元佔2個字元） |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode （因手機而異） |

## 多部分SMS （長SMS） {#multipart-sms}

多部分SMS （通常稱為長SMS）是以多個部分傳送的SMS。 由於行動網路通訊協定中的技術限制，SMS不能大於140位元組（請參閱下面的SMS文字編碼一節，以瞭解SMS中可容納的字元數），因此需要分割較長的訊息。

長訊息的每個部分是個別的SMS。 這些零件在網路上獨立運作，並由接收的行動電話組裝。 為了適當地處理重試和連線問題，Campaign會以相反順序傳送部分，並只在訊息的第一部分（最後傳送的部分）要求SR；由於行動電話只會在收到其第一部分時顯示訊息，因此對其他部分的重試不會在行動電話上產生重複專案。

您可以使用傳遞範本中的每則訊息簡訊數量上限設定，來設定每則傳遞的簡訊數量上限。 超過此限制的訊息將在傳送期間因簡訊失敗原因過長而失敗。

傳送長簡訊的方式有兩種：

* UDH
* message_payload

UDH是預設且建議使用的傳送長訊息的方式。 在此模式中，聯結器會將訊息分割到多個SUBMIT_SM PDU，其中包含UDH資訊。 此通訊協定是行動電話本身使用的通訊協定，這表示Campaign對訊息產生具有最大控制權，使其能夠準確計算已傳送多少部分及其分割方式。

*message_payload*&#x200B;是在單一SUBMIT_SM PDU中傳送整個長訊息的方式。 提供者必須加以分割，這表示Campaign無法得知已傳送的確切數量。 有些提供者需要此模式，只有在他們不支援UDH時才使用。

如需有關通訊協定和格式的詳細資訊，請參閱上述SUBMIT_SM PDU的esm_class、short_message和message_payload欄位說明。

>[!NOTE]
>
>雖然Adobe Campaign支援UDH和message_payload的傳送功能，但傳入的SMS (MO)僅支援message_payload。
