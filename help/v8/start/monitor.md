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
source-git-commit: 4a626787cafd7cc9bfb1d26b26a703aa5fb86a58
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 2%

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

傳送傳遞後進行監視是確保行銷活動效率並觸及客戶的關鍵步驟。 傳送傳遞後，您可以追蹤其進度，並從傳遞控制面板診斷問題。 控制面板可讓您存取每個使用管道的傳送記錄、排除記錄、追蹤記錄及其他資料。

>[!NOTE]
>
>**Campaign新使用者？** 傳遞控制面板是您的主要日常畫面。 開啟任何已傳送的傳遞，按一下&#x200B;**記錄檔**&#x200B;索引標籤，您就會看到哪些收件者已收到郵件、哪些收件者已被排除、原因以及哪些收件者已按一下或開啟。

**電子郵件傳遞** — 監視電子郵件傳遞狀態、追蹤關鍵量度，以及存取詳細記錄檔。 深入瞭解[在Campaign UI](../send/delivery-dashboard.md)、[傳遞狀態](../send/delivery-statuses.md)和[電子郵件傳遞監視](../send/send.md#email-monitoring)中監視傳遞。

**SMS傳遞** — 追蹤SMS傳遞狀態並在SMS傳遞控制面板中監視關鍵量度。 深入瞭解[簡訊監視](../send/sms/sms-monitor.md)。

**推播通知** — 監視推播通知傳遞，以確保它們能有效觸及您的行動應用程式使用者。 深入瞭解[推播通知監視](../send/push.md#push-test)。

**異動訊息** — 對於由事件觸發的訊息，監視事件處理狀態、佇列深度和執行結果。 深入瞭解[異動訊息監視](../send/delivery-execution.md#monitor-messages)。

**傳遞失敗** — 瞭解傳遞失敗的原因對於維護乾淨的資料庫並確保良好的傳遞率至關重要。 傳送失敗分為三種型別 — 瞭解差異有助於您決定要採取的行動：

| 失敗類型 | 其含義 | 行銷活動的功能 |
| --- | --- | --- |
| **硬退信** | 地址永久無效（不存在，網域未知） | 連絡人會自動隔離 — 在未來的傳送中不會鎖定該連絡人 |
| **軟退信** | 暫時性問題（信箱已滿，伺服器暫時無法使用） | Campaign會在設定的期間內自動重試 |
| **已忽略** | 該地址在傳送前已被隔離或列入封鎖名單 | 未嘗試；與退信分別計算 |

深入瞭解[傳送失敗和隔離](../send/delivery-failures.md)。

## 監視傳遞能力 {#monitor-deliverability}

傳遞能力是衡量訊息成功抵達收件者收件匣的程度，而非被篩選為垃圾郵件或拒絕的程度。 Adobe Campaign提供數種內建工具，協助您瞭解並改善收件匣放置率。

>[!NOTE]
>
>計為「已傳遞」的郵件表示接收伺服器已接受該郵件 — 無法保證收件匣的位置。 傳遞能力監視可告訴您傳送網域驗證、IP信譽和電子郵件內容是否符合收件匣提供者的標準。

Adobe Campaign提供下列內建傳遞工具：

- **傳遞報告** — 內建報告，顯示一段時間的傳送量、跳出率和取消訂閱數。
- **收件匣轉譯** — 預覽您的電子郵件在主要使用者端(Gmail、Outlook、Apple Mail)上傳送前後的顯示方式。
- **SpamAssassin測試** — 根據常見的垃圾郵件篩選規則對您的電子郵件內容評分，以在傳遞前攔截問題。
- **廣播統計資料** — 彙總傳送磁碟區和IP信譽的傳遞資料。

遵循傳遞能力最佳實務（例如維護清晰的電子郵件清單、監控寄件者信譽和驗證傳送網域），對於保持良好的傳遞率至關重要。

深入瞭解[傳遞能力監視工具](../send/monitoring-deliverability.md)和[傳遞能力最佳實務](../send/about-deliverability.md)。

## 監視工作流程 {#monitor-workflows}

工作流程是行銷自動化和資料處理背後的引擎。 監控可確保排程活動如預期完成，並可在錯誤影響傳遞或資料品質之前擷取錯誤。

>[!TIP]
>
>如果工作流程顯示&#x200B;**失敗**&#x200B;狀態，請開啟它，用滑鼠右鍵按一下紅色活動，然後選取&#x200B;**顯示記錄**。 錯誤訊息會明確指出哪裡出錯了，以及在哪筆記錄上。

### 工作流程監視功能 {#workflow-monitoring}

**監視下列工作流程元素：**

**工作流程執行狀態** — 追蹤工作流程是否正在執行、暫停、失敗或完成。 一眼即可發現卡住或長期執行的工作流程。 [進一步瞭解工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**活動執行記錄** — 深入瞭解每個活動的記錄以瞭解每個步驟發生的情況 — 對於疑難排解失敗的轉換或未預期的資料輸出很有用。

**工作流程熱度圖** — 跨執行個體同時執行的所有工作流程視覺化概觀。 使用它來識別尖峰載入期間、找出消耗不成比例資源的工作流程，並計畫排程以避免執行衝突。 僅供Campaign管理員使用。 [進一步瞭解工作流程熱度圖](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=zh-Hant){target="_blank"}

**工作流程歷史記錄** — 追蹤所有工作流程執行和隨時間進行的修改，以瞭解工作流程行為和效能模式。

## 監視您的執行個體 {#monitor-instance}

執行個體監視涵蓋Campaign環境的健康情況，包括資料庫容量、設定檔使用量、輸送量和基礎架構。 對於Campaign v8受管理的Cloud Services，Adobe會代表您監視和管理基礎基礎結構，但您可以透過使用者端主控台和控制面板保持完整的可見度。 深入瞭解[Adobe管理的監視](#adobe-cloud-monitoring)。

### 稽核軌跡 {#audit-trail}

稽核軌跡自助式介面可讓您監控在Adobe Campaign執行個體內進行的每次重大變更。 稽核軌跡可以即時擷取您執行個體中發生之動作和事件的完整清單。

**使用稽核軌跡：**

- **追蹤元件變更** — 監視您的工作流程、結構描述、選項和其他元件發生什麼狀況
- **識別變更者** — 檢視上次修改元素的使用者及修改時間
- **疑難排解非預期行為** — 透過使用者動作回溯以找出問題發生的時間和方式
- **支援法規遵循與稽核** — 保留所有組態變更的完整、不經篡改的記錄

稽核軌跡可透過Campaign使用者端主控台存取，並提供使用者所執行動作的詳細資訊。

深入瞭解[稽核軌跡](../reporting/audit-trail.md)

### 效能監視 {#performance-monitoring}

Campaign v8提供數個監視功能，可追蹤您的執行個體效能並確保最佳化操作：

**資料庫監視** — 透過[控制檯]監視資料庫使用量和容量，以確保最佳效能和儲存管理。 [進一步瞭解資料庫監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**作用中設定檔監控** — 根據您的合約限制追蹤作用中設定檔的使用情況，以維持法規遵循並最佳化資源配置。 [進一步瞭解作用中設定檔](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**工作流程監視** — 監視工作流程執行狀態以識別長期執行的工作流程，並確保所有技術工作流程都正確執行。 [進一步瞭解技術工作流程](#technical-workflows)

**傳遞輸送量和延遲** — 透過「控制面板」追蹤傳遞輸送量（每小時傳送的訊息）和異動通訊的延遲。 [進一步瞭解輸送量監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>對於Campaign v8受管理的Cloud Services，伺服器基礎結構（CPU、記憶體、磁碟）由Adobe監控和管理。 本頁和「控制面板」中所述的監控功能相輔相成，可讓您檢視資料與設定，而不需要存取基礎結構。 Adobe所執行的某些動作會顯示在您的Campaign記錄檔中，位於&#x200B;**campaign-loginmonitor**&#x200B;使用者下方。 深入瞭解[Adobe管理的監視](#adobe-cloud-monitoring)。

### Adobe管理監控 {#adobe-cloud-monitoring}

Adobe Campaign雲端服務提供關鍵任務支援，可透過彈性的雲端基礎建設，滿足高要求的客戶體驗提供需求。 如此一來，組織便可啟動、監控及最佳化客戶體驗，不需自行管理或操作Campaign基礎架構。

Adobe會全天候監控您的Campaign Cloud Services環境，以偵測技術問題並將中斷的情況降至最低。 偵測到問題時，系統會使用自動重新啟動和自動啟動機制來嘗試修復。 如果系統無法自我修復，Adobe電話工程會根據預先定義的警報Runbook進行干預。

>[!TIP]
>
>您可以透過[Campaign控制面板](#control-panel)訂閱即時執行個體警示，並針對偵測到的問題（例如即將到期的SSL憑證）接收建議的補救步驟。

**監視層級**

Adobe會跨三個層級監控您的環境。 第1級問題具有最廣泛的影響，並獲得最快的回應：

| 階層 | 群組 | 您可能會體驗到的內容 |
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
>Adobe Campaign雲端服務建置在多雲端策略上，並在AWS和Azure上進行部署。 AWS、Azure和其他資料中心部署的監控功能不同。 除非另有說明，否則上表適用於AWS上託管的Campaign Cloud Services客戶。 Adobe Campaign目前不會向客戶公開隨叫隨到工程使用的所有監控資料。

### 技術工作流程 {#technical-workflows}

技術工作流程會在背景以無訊息方式執行，以維護您的Campaign執行個體。 它們不是由使用者建立 — 而是隨產品一起提供。 如果技術工作流程失敗，可能會直接影響傳遞和資料品質。

確認每個技術工作流程都依排程執行、順利完成並正確處理資料。

| 工作流程 | 用途 | 如果失敗 |
| --- | --- | --- |
| **追蹤** | 處理來自電子郵件傳遞的追蹤資料 | 按一下並開啟量度即停止在報告中更新 |
| **清理** | 移除舊資料和記錄以維持資料庫效能 | 未受檢查的資料庫成長，降低查詢和傳遞效能 |
| **傳遞能力更新** | 更新傳遞規則和垃圾郵件篩選模式 | 規則過時；篩選準確性可能會降低 |
| **資料庫清理** | 清除舊傳遞和追蹤記錄 | 隨著時間推移，記錄累積會減慢查詢和報告的速度 |

深入瞭解[技術工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Campaign 控制面板 {#control-panel}

Campaign「控制面板」為管理員提供自助服務功能，可監控和管理Campaign執行個體，不需要支援票證。

| 監視型別 | 功能 |
| --- | --- |
| **效能** | 作用中設定檔使用情形與合約限制、資料庫使用情形和容量、工作流程執行狀態、傳遞輸送量和延遲的比較 |
| **基礎架構** | SFTP儲存容量、子網域設定、SSL憑證到期警報、IP允許清單 |
| **執行個體** | 組建版本和已安裝的套件、系統設定概觀、授權的外部網域 |

深入瞭解[控制面板](../config/self-service.md)和[控制面板效能監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hant){target="_blank"}

>[!NOTE]
>
>針對Campaign v8受管理的Cloud Services，Adobe會監控及管理伺服器基礎結構、作業系統和應用程式層。 本頁所述的監控功能與「控制面板」相輔相成，讓您無需存取基礎建設即可檢視資料與設定。

## 追蹤與報告 {#tracking-reporting}

### 訊息追蹤 {#message-tracking}

追蹤會記錄收件者在傳遞後與您的訊息互動的方式。 所有追蹤的事件都會儲存在追蹤記錄中，並出現在傳送報告中。

- **開啟次數** — 追蹤畫素載入時錄製（僅限電子郵件）
- **點按** — 已針對訊息中的每個追蹤連結錄製
- **取消訂閱** — 透過取消訂閱連結的選擇退出請求
- **映象頁面檢視** — 在瀏覽器中檢視電子郵件的收件者

深入瞭解[訊息追蹤](../send/tracking.md)

### 傳遞報告 {#delivery-reports}

Adobe Campaign提供全方位的報告集，可分析您的傳送績效：

- **傳遞摘要** — 單一傳遞的傳送、傳遞和失敗概觀
- **追蹤指標** — 開啟次數、點按次數和點進率以及隨時間變化的趨勢
- **URL和點按資料流** — 最多點按連結的排名，包含計數和百分比
- **熱點點按** — 視覺化覆蓋顯示收件者在電子郵件內文中的點按位置

深入瞭解[傳遞報告](../reporting/delivery-reports.md)

### 全域報告 {#global-reports}

存取全域報告，以分析所有行銷活動和傳送的效能：

- **傳遞輸送量** — 一段期間內，所有傳遞每小時傳送的訊息
- **無法傳遞的專案和退信** — 依失敗型別和原因劃分失敗的傳遞
- **使用者活動** — 所有行銷活動的開啟、點按和取消訂閱彙總

深入瞭解[全域報告](../reporting/global-reports.md)

## 相關主題 {#related-topics}

- [關於傳遞的最佳實務](delivery-best-practices.md)
- [隔離管理](../send/quarantines.md)
- [設定並傳送傳遞](../send/configure-and-send.md)
- [開始使用報告功能](../reporting/gs-reporting.md)
