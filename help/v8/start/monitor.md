---
title: 行銷活動監控概觀
description: 瞭解如何監視傳遞、工作流程和您的行銷活動執行個體
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 1%

---

# 行銷活動監控概觀 {#monitor-campaign}

Adobe Campaign可讓您檢視每個層級的資訊 — 從是否有傳送的個別訊息、工作流程失敗的原因，到執行個體還剩下多少資料庫容量。 此頁面會對應所有監控功能，讓您知道當有需要注意的事物時應該檢視何處。

>[!NOTE]
>
>身為Campaign管理員，您也可以使用[Campaign控制面板](#control-panel)來監視您的執行個體、管理效能，以及設定具有自助服務功能的設定。

>[!TIP]
>
>**不確定從何處開始？**
>
>- 行銷人員正在檢查行銷活動→ [監視您的傳遞](#monitor-deliveries)
>- 疑難排解[監視→作流程](#monitor-workflows)的工作流程
>- 管理員檢查執行個體健康狀況→ [監視您的執行個體](#monitor-instance)

## 監視您的傳遞 {#monitor-deliveries}

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 傳送傳遞後，您可以在傳遞控制面板中監視其狀態並追蹤關鍵量度。 控制面板提供傳送記錄、排除記錄、追蹤記錄及其他監視功能的存取權，可協助您分析所有管道的傳送成效。

>[!NOTE]
>
>**Campaign新使用者？** 傳遞控制面板是您的主要日常畫面。 開啟任何已傳送的傳遞，按一下&#x200B;**記錄檔**&#x200B;索引標籤，您就會看到哪些收件者已收到郵件、哪些收件者已被排除、原因以及哪些收件者已按一下或開啟。

**電子郵件傳遞** — 監視電子郵件傳遞狀態、追蹤關鍵量度，並存取詳細記錄檔。 深入瞭解[在Campaign UI](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/monitor/delivery-dashboard)、[傳遞狀態](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/monitor/delivery-statuses)和[電子郵件傳遞監視](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/emails/send#email-monitoring)中監視傳遞。

**簡訊傳遞** — 追蹤SMS傳遞狀態，並在SMS傳遞控制面板中監視關鍵量度。 深入瞭解[簡訊監視](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/sms/sms-monitor)。

**推播通知** — 監視推播通知傳遞，以確保它們能有效觸及您的行動應用程式使用者。 深入瞭解[推播通知監視](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/push/push#push-test)。

**異動訊息** — 對於由事件觸發的訊息，監視事件處理狀態、訊息執行和傳遞狀態。 深入瞭解[異動訊息監視](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages)。

**傳遞失敗** — 瞭解傳遞失敗的原因對於維持乾淨的資料庫並確保良好的傳遞率至關重要。 傳送失敗分為三種型別 — 瞭解差異有助於您決定要採取的行動：

| 失敗類型 | 其含義 | 行銷活動的功能 |
| --- | --- | --- |
| **硬退信** | 地址永久無效（不存在，網域未知） | 連絡人會自動隔離 — 在未來的傳送中不會鎖定該連絡人 |
| **軟退信** | 暫時性問題（信箱已滿，伺服器暫時無法使用） | Campaign會在設定的期間內自動重試 |
| **已忽略** | 該地址在傳送前已被隔離或列入封鎖名單 | 未嘗試；與退信分別計算 |

深入瞭解[傳送失敗和隔離](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/monitor/delivery-failures)。

## 監視傳遞能力 {#monitor-deliverability}

>[!NOTE]
>
>計為「已傳遞」的郵件表示接收伺服器已接受該郵件 — 無法保證收件匣的位置。 傳遞能力監視可告訴您傳送網域驗證、IP信譽和電子郵件內容是否符合收件匣提供者的標準。

傳遞能力監視可協助您確保訊息抵達收件者的收件匣，並避免垃圾郵件篩選器。 Adobe Campaign提供數個內建工具，用於監視和改善傳遞能力，包括傳遞報告、收件匣轉譯、SpamAssassin測試和廣播統計資料。 遵循傳遞能力最佳實務（例如保持清晰的電子郵件清單、監控寄件者信譽和驗證傳送網域）對於保持良好的傳遞率至關重要。

深入瞭解[傳遞能力監視工具](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability)和[傳遞能力最佳實務](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability)。

## 監視工作流程 {#monitor-workflows}

工作流程是自動化行銷活動和資料處理的關鍵。 監視工作流程執行可協助您：

- 確保工作流程成功完成
- 識別錯誤並進行疑難排解
- 最佳化工作流程效能

>[!TIP]
>
>如果工作流程顯示&#x200B;**失敗**&#x200B;狀態，請開啟它，用滑鼠右鍵按一下紅色活動，然後選取&#x200B;**顯示記錄**。 錯誤訊息會明確指出哪裡出錯了，以及在哪筆記錄上。

### 工作流程監視功能 {#workflow-monitoring}

**監視下列工作流程元素：**

**工作流程執行狀態** — 追蹤工作流程是否正在執行、暫停、失敗或完成。 [進一步瞭解工作流程執行](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**活動執行記錄** — 存取每個工作流程活動的詳細記錄，以疑難排解問題並最佳化效能。

**工作流程熱度圖** — 跨執行個體同時執行的所有工作流程視覺化概觀。 使用它來識別尖峰載入期間、找出消耗不成比例資源的工作流程，並計畫排程以避免執行衝突。 僅供Campaign管理員使用。 [進一步瞭解工作流程熱度圖](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**工作流程歷史記錄** — 追蹤所有工作流程執行和一段時間內的修改，以瞭解工作流程行為和效能。

## 監視您的執行個體 {#monitor-instance}

執行個體監視可協助您確保Adobe Campaign環境的健康狀況和效能。 針對Campaign v8受管理的Cloud Services，Adobe也會代表您監控及管理基礎結構。 深入瞭解[Adobe管理的監視](#adobe-cloud-monitoring)。

### 稽核軌跡 {#audit-trail}

稽核軌跡自助式介面可讓您監視在Adobe Campaign執行個體中所做的變更。 稽核軌跡可以即時擷取執行個體中發生之動作和事件的完整清單。

**使用稽核軌跡：**

- **追蹤元件變更**：監視您的工作流程、結構描述、選項和其他元件發生什麼狀況
- **識別變更者**：檢視上次更新特定元素的人和時間
- **瞭解使用者動作**：檢閱使用者在執行個體中執行的動作，以進行疑難排解或稽核
- **維護法規遵循**：追蹤所有設定變更，以符合法規遵循及安全性目的

稽核軌跡可透過Campaign使用者端主控台存取，並提供使用者所執行動作的詳細資訊。

深入瞭解[稽核軌跡](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/analytics/audit-trail)

### 效能監視 {#performance-monitoring}

Campaign v8提供數個監視功能，可追蹤您的執行個體效能並確保最佳化操作：

**資料庫監視** — 透過[控制檯]監視資料庫使用量和容量，以確保最佳效能和儲存管理。 [進一步瞭解資料庫監視](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**作用中設定檔監控** — 根據您的合約限制追蹤作用中設定檔的使用情況，以維持法規遵循並最佳化資源配置。 [進一步瞭解作用中設定檔](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**工作流程監視** — 監視工作流程執行狀態以識別長期執行的工作流程，並確保所有技術工作流程都正確執行。 [進一步瞭解技術工作流程](#technical-workflows)

**傳遞輸送量和延遲** — 透過「控制面板」追蹤傳遞輸送量（每小時傳送的訊息）和異動通訊的延遲。 [進一步瞭解輸送量監視](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>對於Campaign v8受管理的Cloud Services，伺服器基礎結構（CPU、記憶體、磁碟）由Adobe監控和管理。 深入瞭解[Adobe管理的監視](#adobe-cloud-monitoring)。

### Adobe管理監控 {#adobe-cloud-monitoring}

Adobe Campaign雲端服務提供關鍵任務支援，可透過彈性的雲端基礎建設，滿足高要求的客戶體驗提供需求。 這讓組織能夠啟動、監控和最佳化客戶體驗，而不需要自己管理或操作Campaign基礎結構。

Adobe會監視您的Campaign Cloud Services環境，透過偵測技術問題並提供有關效能和進行中專案的持續意見回饋，協助管理各種問題並將中斷的情況降至最低。

**Adobe如何回應**

Adobe會全天候監控Campaign網路上的所有關鍵網路裝置，並在需要修正或升級時接收來自監視系統的通知。 偵測到問題時，系統會使用自動重新啟動和自動啟動機制來嘗試修復。 如果系統無法自我修復，Adobe電話工程會介入，根據預先定義的警報Runbook執行疑難排解。

>[!NOTE]
>
>Adobe所執行的某些監視動作會顯示在&#x200B;**campaign-loginmonitor**&#x200B;使用者下的Campaign記錄檔中。

除了Adobe的內部監控之外，您也可以直接透過Campaign使用者端主控台或[Campaign控制面板](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/permissions/self-service)存取監控功能。 使用「控制面板」，您可以訂閱有關執行個體的即時警報，並針對已識別的事件（例如接近到期的SSL憑證）接收建議的補救步驟。

**監視分類**

Adobe會跨三個層級監控您的環境：

| 階層 | 群組 | 潛在業務影響 |
| --- | --- | --- |
| **第1層：基礎結構** | 資料庫空間耗盡 | 效能問題，包括無法登入、執行批次傳遞或執行查詢 |
| **第1層：基礎結構** | 資料庫可用性 | 使用者和服務可能無法使用系統 |
| **第1層：基礎結構** | 資料庫超載（高載平衡） | 效能問題，包括無法登入、執行批次傳遞或執行查詢 |
| **第1層：基礎結構** | 資料庫序列和交易ID耗盡 | 無法建立新的工作流程、傳遞或傳送批次電子郵件 |
| **第1層：基礎結構** | SFTP儲存 | 無法更新或擷取SFTP伺服器上的資料 |
| **第2層：平台和網頁** | 登入 | 使用者可能無法登入；排程的活動和工作流程可能無法執行 |
| **第2層：平台和網頁** | API鎖定 | 使用者或服務可能無法驗證或執行作業 |
| **第2層：平台和網頁** | Web | 無法建立與Campaign的新連線 |
| **第2層：平台和網頁** | 資料中心網路 | 資料中心使用者的效能問題或完全無法使用 |
| **第3層：軟體** | 傳遞追蹤 | 無法處理追蹤記錄 |
| **第3層：軟體** | inMail | 沒有電子郵件傳送錯誤和退回的回饋 |
| **第3層：軟體** | 訊息中心狀態 | 無法傳送任何交易式傳遞 |
| **第3層：軟體** | MTA | 無法傳送排程和隨選電子郵件傳遞 |
| **第3層：軟體** | 工作流程伺服器狀態 | 無法執行工作流程 |
| **第3層：軟體** | Web API可用性 | 無法處理HTTP要求或執行API呼叫 |
| **第3層：軟體** | 傳入互動 | 無法處理傳入互動 |

>[!NOTE]
>
>Adobe Campaign雲端服務建置在多雲端策略上，並提供AWS和Azure上的部署功能。 由於廠商差異，AWS、Azure和其他資料中心部署的監控功能會有所不同。 除非另有說明，否則上表適用於AWS上託管的Campaign Cloud Services客戶。 另請注意，Adobe Campaign目前不會向客戶公開隨叫隨到工程使用的所有監控資料。

### 技術工作流程 {#technical-workflows}

技術工作流程是在背景執行以維護您的Campaign執行個體的基本流程。

**監視技術工作流程為：**

- 依排程執行
- 順利完成且沒有錯誤
- 正確處理資料

**要監視的關鍵技術工作流程：**

| 工作流程 | 用途 | 如果失敗 |
| --- | --- | --- |
| **追蹤** | 處理來自電子郵件傳遞的追蹤資料 | 按一下並開啟量度即停止在報告中更新 |
| **清理** | 移除舊資料和記錄以維持資料庫效能 | 未受檢查的資料庫成長，降低查詢和傳遞效能 |
| **傳遞能力更新** | 更新傳遞規則和垃圾郵件篩選模式 | 規則過時；篩選準確性可能會降低 |
| **資料庫清理** | 清除舊傳遞和追蹤記錄 | 隨著時間推移，記錄累積會減慢查詢和報告的速度 |

深入瞭解[技術工作流程](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Campaign 控制面板 {#control-panel}

Campaign控制面板為管理員提供自助服務功能，以監控和管理Campaign執行個體。

| 監視型別 | 功能 |
| --- | --- |
| **效能** | 追蹤作用中設定檔使用量、監控資料庫使用量和容量、檢視工作流程執行狀態、監控傳遞輸送量和延遲 |
| **基礎架構** | 監視SFTP儲存容量、追蹤子網域設定、監視SSL憑證過期、管理IP允許清單 |
| **執行個體** | 檢視組建版本和已安裝的套件、監視系統組態、管理授權的外部網域 |

深入瞭解[控制面板](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/permissions/self-service)和[控制面板效能監視](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>針對Campaign v8受管理的Cloud Services，Adobe會監控及管理伺服器基礎結構、作業系統和應用程式層。 深入瞭解[Adobe管理的監視](#adobe-cloud-monitoring)。 您可以使用本頁和「控制面板」中所述的監視功能，來監視執行個體效能、工作流程和傳送。

## 追蹤與報告 {#tracking-reporting}

### 訊息追蹤 {#message-tracking}

追蹤收件者行為並評估行銷活動的成效：

- **開啟**：追蹤收件者何時開啟您的電子郵件
- **點按**：監視收件者點按的連結
- **取消訂閱**：追蹤選擇退出要求
- **映象頁面檢視**：檢視有多少收件者在瀏覽器中檢視您的電子郵件

深入瞭解[訊息追蹤](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/analytics/tracking/tracking)

### 傳遞報告 {#delivery-reports}

Adobe Campaign提供全方位的報告集，可分析您的傳送績效：

- **傳遞摘要**：傳送、傳遞和失敗概觀
- **追蹤指標**：開啟次數、點按次數和點進率
- **個URL和點按資料流**：傳遞中最受歡迎的連結
- **熱點點按**：收件者點按您電子郵件之位置的視覺化表示

深入瞭解[傳遞報告](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### 全域報告 {#global-reports}

存取全域報告，以分析所有行銷活動和傳送的效能：

- **傳遞輸送量**：一段時間內傳送的訊息
- **無法傳遞的專案和退信**：失敗傳遞的分析
- **使用者活動**：所有行銷活動的開啟、點按和取消訂閱

深入瞭解[全域報告](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## 相關主題 {#related-topics}

- [關於傳遞的最佳實務](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/delivery-best-practices)
- [隔離管理](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/monitor/quarantines)
- [設定並傳送傳遞](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [開始使用報告功能](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
