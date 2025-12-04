---
title: 行銷活動監控概觀
description: 瞭解如何監視傳遞、工作流程和您的行銷活動執行個體
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# 行銷活動監控概觀 {#monitor-campaign}

Adobe Campaign提供全方位的功能，可監控您的流程、傳遞和環境，以確保最佳效能和主動疑難排解問題。

>[!NOTE]
>
>身為Campaign管理員，您也可以使用[Campaign控制面板](#control-panel)來監視您的執行個體、管理效能，以及設定具有自助服務功能的設定。

## 監視您的傳遞 {#monitor-deliveries}

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 傳送傳遞後，您可以在傳遞控制面板中監視其狀態並追蹤關鍵量度。 控制面板提供傳送記錄、排除記錄、追蹤記錄及其他監視功能的存取權，可協助您分析所有管道的傳送成效。

**電子郵件傳遞** — 監視電子郵件傳遞狀態、追蹤關鍵量度，並存取詳細記錄檔。 深入瞭解[在Campaign UI](../send/delivery-dashboard.md)、[傳遞狀態](../send/delivery-statuses.md)和[電子郵件傳遞監視](../send/send.md#email-monitoring)中監視傳遞。

**簡訊傳遞** — 追蹤SMS傳遞狀態，並在SMS傳遞控制面板中監視關鍵量度。 深入瞭解[簡訊監視](../send/sms/sms-monitor.md)。

**推播通知** — 監視推播通知傳遞，以確保它們能有效觸及您的行動應用程式使用者。 深入瞭解[推播通知監視](../send/push.md#push-test)。

**異動訊息** — 對於由事件觸發的訊息，監視事件處理狀態、訊息執行和傳遞狀態。 深入瞭解[異動訊息監視](../send/delivery-execution.md#monitor-messages)。

**傳遞失敗** — 瞭解傳遞失敗的原因對於維持乾淨的資料庫並確保良好的傳遞率至關重要。 傳送失敗分為硬退信、軟退信和忽略訊息。 深入瞭解[傳送失敗和隔離](../send/delivery-failures.md)。

## 監視傳遞能力 {#monitor-deliverability}

傳遞能力監視可協助您確保訊息抵達收件者的收件匣，並避免垃圾郵件篩選器。 Adobe Campaign提供數個內建工具，用於監視和改善傳遞能力，包括傳遞報告、收件匣轉譯、SpamAssassin測試和廣播統計資料。 遵循傳遞能力最佳實務（例如保持清晰的電子郵件清單、監控寄件者信譽和驗證傳送網域）對於保持良好的傳遞率至關重要。

深入瞭解[傳遞能力監視工具](../send/monitoring-deliverability.md)和[傳遞能力最佳實務](../send/about-deliverability.md)。

## 監視工作流程 {#monitor-workflows}

工作流程是自動化行銷活動和資料處理的關鍵。 監視工作流程執行可協助您：

* 確保工作流程成功完成
* 識別錯誤並進行疑難排解
* 最佳化工作流程效能

### 工作流程監視功能 {#workflow-monitoring}

**監視下列工作流程元素：**

**工作流程執行狀態** — 追蹤工作流程是否正在執行、暫停、失敗或完成。 [進一步瞭解工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hant){target="_blank"}

**活動執行記錄** — 存取每個工作流程活動的詳細記錄，以疑難排解問題並最佳化效能。

**工作流程熱度圖** — 視覺化工作流程執行模式、識別瓶頸並監視並行工作流程。 Campaign管理員可使用Workflow HeatMap。 [進一步瞭解工作流程熱度圖](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=zh-Hant){target="_blank"}

**工作流程歷史記錄** — 追蹤所有工作流程執行和一段時間內的修改，以瞭解工作流程行為和效能。

## 監視您的執行個體 {#monitor-instance}

執行個體監視可協助您確保Adobe Campaign環境的健康狀況和效能。

### 稽核軌跡 {#audit-trail}

稽核軌跡自助式介面可讓您監視在Adobe Campaign執行個體中所做的變更。 稽核軌跡可以即時擷取執行個體中發生之動作和事件的完整清單。

**使用稽核軌跡：**

* **追蹤元件變更**：監視您的工作流程、結構描述、選項和其他元件發生什麼狀況
* **識別變更者**：檢視上次更新特定元素的人和時間
* **瞭解使用者動作**：檢閱使用者在執行個體中執行的動作，以進行疑難排解或稽核
* **維護法規遵循**：追蹤所有設定變更，以符合法規遵循及安全性目的

稽核軌跡可透過Campaign使用者端主控台存取，並提供使用者所執行動作的詳細資訊。

深入瞭解[稽核軌跡](../reporting/audit-trail.md)

### 效能監視 {#performance-monitoring}

Campaign v8提供數個監視功能，可追蹤您的執行個體效能並確保最佳化操作：

**資料庫監視** — 透過[控制檯]監視資料庫使用量和容量，以確保最佳效能和儲存管理。 [進一步瞭解資料庫監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=zh-Hant){target="_blank"}

**作用中設定檔監控** — 根據您的合約限制追蹤作用中設定檔的使用情況，以維持法規遵循並最佳化資源配置。 [進一步瞭解作用中設定檔](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=zh-Hant){target="_blank"}

**工作流程監視** — 監視工作流程執行狀態以識別長期執行的工作流程，並確保所有技術工作流程都正確執行。 [進一步瞭解技術工作流程](#technical-workflows)

**傳遞輸送量和延遲** — 透過「控制面板」追蹤傳遞輸送量（每小時傳送的訊息）和異動通訊的延遲。 [進一步瞭解輸送量監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=zh-Hant){target="_blank"}

>[!NOTE]
>
>對於Campaign v8受管理的Cloud Services，伺服器基礎結構(CPU、記憶體、磁碟)由Adobe監控和管理。

### 技術工作流程 {#technical-workflows}

技術工作流程是在背景執行以維護您的Campaign執行個體的基本流程。

**監視技術工作流程為：**

* 依排程執行
* 順利完成且沒有錯誤
* 正確處理資料

**要監視的關鍵技術工作流程：**

| 工作流程 | 用途 |
|----------|---------|
| **追蹤** | 處理來自電子郵件傳遞的追蹤資料 |
| **清理** | 移除舊資料和記錄以維持資料庫效能 |
| **傳遞能力更新** | 更新傳遞規則和垃圾郵件篩選模式 |
| **資料庫清理** | 清除舊傳遞和追蹤記錄 |

深入瞭解[技術工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=zh-Hant){target="_blank"}

### Campaign 控制面板 {#control-panel}

Campaign控制面板為管理員提供自助服務功能，以監控和管理Campaign執行個體。

| 監視型別 | 功能 |
|-----------------|--------------|
| **效能** | 追蹤作用中設定檔使用量、監控資料庫使用量和容量、檢視工作流程執行狀態、監控傳遞輸送量和延遲 |
| **基礎架構** | 監視SFTP儲存容量、追蹤子網域設定、監視SSL憑證過期、管理IP允許清單 |
| **執行個體** | 檢視組建版本和已安裝的套件、監視系統組態、管理授權的外部網域 |

深入瞭解[控制面板](../config/self-service.md)和[控制面板效能監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hant){target="_blank"}

>[!NOTE]
>
>針對Campaign v8受管理的Cloud Services，Adobe會監控及管理伺服器基礎結構、作業系統和應用程式層。 您可以使用本頁和「控制面板」中所述的監視功能，來監視執行個體效能、工作流程和傳送。

## 追蹤與報告 {#tracking-reporting}

### 訊息追蹤 {#message-tracking}

追蹤收件者行為並評估行銷活動的成效：

* **開啟**：追蹤收件者何時開啟您的電子郵件
* **點按**：監視收件者點按的連結
* **取消訂閱**：追蹤選擇退出要求
* **映象頁面檢視**：檢視有多少收件者在瀏覽器中檢視您的電子郵件

深入瞭解[訊息追蹤](../send/tracking.md)

### 傳遞報告 {#delivery-reports}

Adobe Campaign提供全方位的報告集，可分析您的傳送績效：

* **傳遞摘要**：傳送、傳遞和失敗概觀
* **追蹤指標**：開啟次數、點按次數和點進率
* **個URL和點按資料流**：傳遞中最受歡迎的連結
* **熱點點按**：收件者點按您電子郵件之位置的視覺化表示

深入瞭解[傳遞報告](../reporting/delivery-reports.md)

### 全域報告 {#global-reports}

存取全域報告，以分析所有行銷活動和傳送的效能：

* **傳遞輸送量**：一段時間內傳送的訊息
* **無法傳遞的專案和退信**：失敗傳遞的分析
* **使用者活動**：所有行銷活動的開啟、點按和取消訂閱

深入瞭解[全域報告](../reporting/global-reports.md)

## 相關主題 {#related-topics}

* [關於傳遞的最佳實務](delivery-best-practices.md)
* [隔離管理](../send/quarantines.md)
* [設定並傳送傳遞](../send/configure-and-send.md)
* [開始使用報告功能](../reporting/gs-reporting.md)

