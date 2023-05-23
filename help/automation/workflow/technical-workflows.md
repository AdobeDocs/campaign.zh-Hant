---
product: campaign
title: 技術工作流程
description: 瞭解有關市場活動提供的技術工作流的更多資訊
feature: Workflows
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 3%

---

# 技術工作流程{#about-technical-workflows}

Adobe Campaign提供了一套內置的技術工作流程。 它們管理計畫在伺服器上定期執行的操作和作業。 它們允許您對資料庫進行維護、轉發有關交貨的跟蹤資訊或設定交貨的臨時流程。 通過 **[!UICONTROL Administration > Production > Technical workflows]** 的下界。

![](assets/navtree.png)

本機模板可用於建立技術工作流。 可以根據您的需要配置這些設備。

的 **[!UICONTROL Campaign process]** 子資料夾集中了在市場活動中執行流程所需的工作流：任務通知、庫存管理、成本計算等。

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>隨每個模組一起安裝的技術工作流清單可在 [專用段](technical-workflows.md)。

您可以在 **[!UICONTROL Administration > Production > Technical workflows]** 樹結構的節點。 但是，此過程保留給專家用戶。

提供的活動與針對工作流的活動相同。 [了解更多](targeting-workflows.md)

本節中詳細介紹的工作流都安裝了不同的Adobe Campaign內置軟體包。 這些軟體包和相關的技術工作流取決於您的許可協定。

預設情況下，技術工作流可在以下節點的子資料夾中使用： **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**。

請注意，只有具有「管理」權限的操作員才能啟動和修改技術工作流。

>[!NOTE]
>
>預設情況下，與「消息中心」載入項相關的技術工作流在 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** 的下界。

瞭解如何監視此中的技術工作流 [專用段](monitor-technical-workflows.md)。


## 技術工作流程清單 {#list-technical-workflows}

| 技術工作流 | 套件 | 說明 |
|------|--------|-----------|
| **別名清除** （別名清除） | 預設安裝 | 此工作流標準化了枚舉值。 預設情況下，每天凌晨3點觸發。 |
| **計費** （帳單） | 預設安裝 | 此工作流通過電子郵件將系統活動報告發送給「開單」操作員。 它是每月25號對營銷實例的觸發。 |
| **市場活動工作** （運營管理） | 預設安裝 | 此工作流管理市場營銷活動（目標啟動、檔案提取等）的作業。 它還建立與定期市場活動相關的工作流。 |
| **收集HeatMap服務的資料** (collectDataHeatMapService) | 預設安裝 | 此工作流檢索HeatMap服務所需的資料。 |
| **收集隱私請求** （收集隱私請求） | 隱私權資料保護法規 | 此工作流將生成儲存在Adobe Campaign的收件人資料，並在隱私請求的螢幕中提供下載。 |
| **成本計算** （預算管理） | 預設安裝 | 此工作流開始計算預算、計畫、方案、市場活動、交貨和任務上的費用和成本行。 |
| **資料庫清理** （清理） | 預設安裝 | 此工作流是資料庫維護工作流：它從統計和進程中進行不同的計算，並根據部署助理中定義的配置從資料庫中刪除過時的資料。 預設情況下，每天凌晨4點觸發。 |
| **刪除阻止的LINE用戶** (deleteBlockedLineUsersV2) | LINE 頻道 | 此工作流確保在LINE V2用戶阻止LINE官方帳戶180天後刪除其資料。 |
| **刪除隱私請求資料** (deletePrivacyRequestsData) | 隱私權資料保護法規 | 此工作流刪除收件人儲存在Adobe Campaign的資料。 |
| **交付指標** （交付指標） | 中間來源平台 | 此工作流更新交貨的交貨跟蹤指示符。 預設情況下，此工作流每小時觸發一次。 |
| **分佈式營銷流程** （中央本地管理） | 中央/本地市場（分佈式市場） | 此工作流開始與使用分佈式市場營銷模組相關的處理。 它啟動本地市場活動的建立，並管理與訂單和市場活動包可用性相關的通知。 |
| **事件清除** (WebAnalyticsPurgeWebEvents) | Web Analytics連接器 | 此工作流允許您根據在「生命週期」欄位中配置的期間從資料庫欄位中刪除每個事件。 |
| **向Adobe Experience Cloud輸出觀眾** (exportSharedAuvience) | 與Adobe Experience Cloud | 此工作流將訪問群導出為共用的訪問群/網段。 這些對象可用於您所使用的不同 Adobe Experience Cloud 解決方案。  |
| **預測** （預測） | 傳遞 | 此工作流分析保存在臨時日曆中的交貨（建立臨時日誌）。 預設情況下，每天凌晨1點觸發它。 |
| **完全聚合計算（propositionrcp多維資料集）** (agg_nmspropositrcp_full) | 提供引擎（交互） | 此工作流更新「優惠」命題多維資料集的「完全」聚合。 預設情況下，每天早上6點觸發。 此聚合捕獲以下維：渠道、交付、營銷優惠和日期。 然後，使用「優惠」命題多維資料集生成基於優惠的報告。 若要深入了解多維度資料集，請參閱[本節](../../v8/reporting/gs-cubes.md)。 |
| **已轉換聯繫人的標識** (webAnalyticsFindConverted) | Web Analytics連接器 | 此工作流為在重新營銷活動後完成採購的站點訪問者編製索引。 通過此工作流恢復的資料可以在「重新營銷效率」報告（請參閱此頁）中訪問。 |
| **從Adobe Experience Cloud引進觀眾** (importSharedAuvience) | 與Adobe Experience Cloud | 此工作流允許您將不同Adobe Experience Cloud解決方案的受眾/段導入Adobe Campaign。 |
| **市場活動中交貨的作業** （交貨管理） | 預設安裝 | 此工作流將觸發已批准的交貨，並啟動對外部交貨的服務提供商進行後處理。 它還會發送審批通知和提醒。 |
| **服務提供商上的作業** （供應商管理） | 預設安裝 | 一旦傳送獲得批准，此工作流將開始處理提供程式（向路由器發送電子郵件和後處理）。 |
| **MID到LineUserID遷移** (MIDToUserIDMigration) | LINE 頻道 | 此工作流將生成LINE V2用戶的ID，以便從LINE V1遷移到LINE V2。 |
| **消息中心 &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | 事務性消息控制項（消息中心 — 控制項） | 此工作流： <ul><li>恢復由操作處理的事件清單。</li><li>與NmsBroadLogMsg表同步以恢復傳遞消息資格。</li><li>與NmsBroadLogMsg表的同步完成後，立即恢復事件傳遞日誌。</li><li>與NmsTrackingUrl表同步以恢復傳遞URL的跟蹤。</li><li>在完成與NmsTrackingUrl表的同步後，立即恢復事件跟蹤URL。</li><li>允許您在發送交貨後每三小時恢復隔離的所有電子郵件地址。</li></ul> |
| **MessageCenter完整聚合計算** (agg_messageCenter_full) | 事務性消息控制項（消息中心 — 控制項） | 此工作流更新消息中心多維資料集的完整聚合。 預設情況下，每天凌晨3點觸發。 此聚合捕獲以下維：渠道、日期、狀態和事件類型。 然後使用消息中心多維資料集生成基於事件的報告。 您可以在中瞭解有關立方的詳細資訊  |
| **中間採購（交貨計數器）** (defaultMidSourcingDlv) | 轉移至中間來源 | 此工作流將收集中間採購伺服器上交貨的計數資訊。 盤點資訊包括一般交貨指標，如發送的交貨數量等。 不包括開啟等跟蹤資訊。 預設情況下，每10分鐘觸發一次。 |
| **中間採購（交貨日誌）** （預設MidSourcingLog） | 轉移至中間來源 | 此工作流將收集中間採購伺服器上的交貨日誌。 預設情況下，每小時觸發一次。 |
| **NMAC選擇退出管理** （移動應用選擇退出管理） | 移動應用通道（推送） | 此工作流更新移動設備上的通知取消訂閱。 從凌晨1點到午夜，每6小時觸發一次。 |
| **優惠通知** （聘用管理） | 預設安裝 | 此工作流將批准的優惠部署到線上環境以及優惠目錄中包含的每個類別。 |
| **暫停的工作流清理** (cleanupPausedWorkflows) | 預設安裝 | 此工作流分析嚴重性設定為正常的暫停工作流，並在暫停過長時觸發警告和通知。 一個月後，暫停的技術工作流將無條件停止。 預設情況下，每週一早上5點觸發。 有關詳細資訊，請參閱 [處理暫停的工作流](monitor-workflow-execution.md#handling-of-paused-workflows)。 |
| **隱私請求清理** (cleanupPrivacyRequests) | 隱私權資料保護法規 | 此工作流會擦除90天以前的訪問請求檔案。 |
| **處理批處理事件** (batchEventsProcessing) | 事務性消息執行（消息中心 — 執行） | 通過此工作流，您可以在將批處理事件與消息模板關聯之前，將它們放入隊列。 |
| **處理即時事件** (rtEventsProcessing) | 事務性消息執行（消息中心 — 執行） | 通過此工作流，您可以在將即時事件與消息模板關聯之前，將它們放入隊列。 |
| **命題同步** （命題同步） | 具有執行實例的供應引擎的控制 | 此工作流將市場營銷實例和用於交互的執行實例之間的建議同步。 |
| **Web事件的恢復** (webAnalyticsGetWebEvents) | Web Analytics連接器 | 每小時，此工作流都會在指定站點上下載網際網路用戶行為段，將它們放入Adobe Campaign資料庫並啟動重新營銷工作流。 |
| **報告聚合** (reportingAggregates) | 傳遞 | 此工作流更新報表中使用的聚合。 預設情況下，每天凌晨2點觸發。 |
| **發送指標和市場活動屬性** (webAnalyticsSendMetrics) | Web Analytics連接器 | 此工作流允許您通過Adobe®分析連接器將電子郵件促銷活動指標從Adobe Campaign發送到Adobe Experience Cloud套件。 有關的指標如下：發送(iSent)、開啟總數(iTotalRecipientOpen)、按一下的收件人總數(iTotalRecipientClick)、錯誤(iError)、選擇退出(opt-out)(iOptOut)。 |
| **股票：訂單和警報** （庫存管理） | 預設安裝 | 此工作流將啟動訂單行上的庫存計算並管理警告預警閾值。 |
| **跟蹤** （跟蹤） | 預設安裝 | 此工作流執行跟蹤資訊的恢復和合併。 它還確保重新計算跟蹤和傳遞統計資訊，特別是消息中心存檔工作流所使用的統計資訊。 預設情況下，每小時觸發一次。 |
| **更新事件狀態** (updateEventsStatus) | 事務性消息執行（消息中心 — 執行） | 此工作流允許您為事件分配狀態。 事件狀態如下：<ul><li>待定：事件在隊列中。 尚未將郵件模板與其關聯。</li><li>待交付：該事件在隊列中，消息模板已與其關聯，並且當前正由傳遞處理。</li><li>已發送：此狀態從交貨日誌中複製。 這意味著送貨已經寄出。</li><li>被傳遞忽略：此狀態從交貨日誌中複製。 這意味著傳遞被忽略。</li><li>傳遞錯誤：此狀態從交貨日誌中複製。 這意味著交貨失敗。</li><li>未涵蓋的事件：事件未能與消息模板關聯。 將不再處理該事件。</li></ul> |
| **更新可交付性** (deliverabilityUpdate) | 預設安裝 | 一旦安裝了「可遞送性監視（電子郵件可遞送性）」包，此工作流將每晚運行，並管理退回的電子郵件限定規則以及域和MX的清單。 這要求在平台上開啟HTTPS埠。 |
