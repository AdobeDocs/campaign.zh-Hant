---
audience: user
user-guide-title: Campaign自動化指南
user-guide-description: Campaign自動化指南
feature: Overview
source-git-commit: 8ff207246bea1f476b37b1d4f2c79498362e7481
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 81%

---


# Campaign自動化指南 {#automation}

+ [Campaign自動化指南](home.md)
+ 使用工作流程自動化{#workflows}
   + 開始使用工作流程 {#introduction}
      + [關於工作流程](workflow/about-workflows.md)
      + 工作流程的型別{#wf-type}
         + [目標工作流程](workflow/targeting-workflows.md)
         + [行銷活動工作流程](workflow/campaign-workflows.md)
         + [技術工作流程](workflow/technical-workflows.md)
      + [建置工作流程](workflow/build-a-workflow.md)
      + [最佳實務](workflow/workflow-best-practices.md)
      + [使用工作流程資料](workflow/use-workflow-data.md)
   + 執行工作流程 {#executing-a-workflow}
      + [開始工作流程](workflow/start-a-workflow.md)
      + [工作流程生命週期](workflow/workflow-life-cycle.md)
      + [設定核准](workflow/define-approvals.md)
   + 監視工作流程 {#monitoring-workflows}
      + [監視工作流程的執行](workflow/monitor-workflow-execution.md)
      + [監視技術工作流程](workflow/monitor-technical-workflows.md)
      + [工作流程熱度圖](workflow/heatmap.md)
   + 工作流程活動{#wf-activities}
      + [開始使用活動](workflow/activities.md)
      + 目標定位活動 {#targeting-activities}
         + [目標定位活動清單](workflow/targeting-activities.md)
         + [儲存格](workflow/cells.md)
         + [變更資料來源](workflow/change-data-source.md)
         + [變更維度](workflow/change-dimension.md)
         + [CRM 連結器](workflow/crm-connector.md)
         + [去重複化](workflow/deduplication.md)
         + [傳遞大綱](workflow/delivery-outline.md)
         + [編輯方案](workflow/edit-schema.md)
         + [擴充](workflow/enrichment.md)
         + [排除](workflow/exclusion.md)
         + [增量查詢](workflow/incremental-query.md)
         + [交集](workflow/intersection.md)
         + [清單更新](workflow/list-update.md)
         + [依儲存格列出的優惠](workflow/offers-by-cell.md)
         + [優惠引擎](workflow/offer-engine.md)
         + [查詢](workflow/query.md)
         + [讀取清單](workflow/read-list.md)
         + [分割](workflow/split.md)
         + [訂閱服務](workflow/subscription-services.md)
         + [聯合](workflow/union.md)
         + [更新資料](workflow/update-data.md)
      + 流量控制活動 {#flow-control-activities}
         + [流量控制活動清單](workflow/flow-control-activities.md)
         + [警報](workflow/alert.md)
         + [合併連結](workflow/and-join.md)
         + [核准](workflow/approval.md)
         + [外部訊號](workflow/external-signal.md)
         + [分支](workflow/fork.md)
         + [跳至 (起點和終點)](workflow/jump-start-point-and-end-point.md)
         + [開始和結束](workflow/start-and-end.md)
         + [排程器](workflow/scheduler.md)
         + [子工作流程](workflow/sub-workflow.md)
         + [測試](workflow/test.md)
         + [時間限制](workflow/time-constraint.md)
         + [等待](workflow/wait.md)
      + 動作活動 {#action-activities}
         + [動作活動清單](workflow/action-activities.md)
         + [內容管理](workflow/content-management.md)
         + [持續傳遞](workflow/continuous-delivery.md)
         + [跨頻道傳遞](workflow/cross-channel-deliveries.md)
         + [資料擷取 (檔案)](workflow/extraction-file.md)
         + [資料載入 (檔案)](workflow/data-loading-file.md)
         + [資料載入 (RDBMS)](workflow/data-loading-rdbms.md)
         + [傳遞](workflow/delivery.md)
         + [傳遞控制](workflow/delivery-control.md)
         + [本地核准](workflow/local-approval.md)
         + [載入 (SOAP)](workflow/loading-soap.md)
         + [Nlserver 模組](workflow/nlserver-module.md)
         + [週期性傳遞](workflow/recurring-delivery.md)
         + [SQL 程式碼和 JavaScript 程式碼](workflow/sql-code-and-javascript-code.md)
         + [SQL 資料管理](workflow/sql-data-management.md)
         + [更新彙總](workflow/update-aggregate.md)
      + 事件活動 {#event-activities}
         + [事件活動清單](workflow/event-activities.md)
         + [檔案收集器](workflow/file-collector.md)
         + [檔案傳輸](workflow/file-transfer.md)
         + [傳入電子郵件](workflow/inbound-emails.md)
         + [傳入簡訊](workflow/inbound-sms.md)
         + [網頁下載](workflow/web-download.md)
   + 使用實例 {#use-cases}
      + [關於工作流程使用實例](workflow/workflow-use-cases.md)
      + 傳遞 {#deliveries}
         + [使用本地核准活動](workflow/local-approval-activity.md)
         + [傳送生日電子郵件](workflow/send-a-birthday-email.md)
         + [載入傳遞內容](workflow/load-delivery-content.md)
         + [跨頻道傳遞工作流程](workflow/cross-channel-delivery-workflow.md)
         + [使用自訂日期欄位擴充電子郵件](workflow/email-enrichment-with-custom-date-fields.md)
      + 監視 {#monitoring}
         + [傳送報吿至清單](workflow/send-a-report-to-a-list.md)
         + [監督您的工作流程](workflow/workflow-supervision.md)
         + [傳送個人化警示給營運商](workflow/send-alerts-to-operators.md)
      + 資料管理 {#data-management}
         + [協調資料更新](workflow/coordinate-data-updates.md)
         + [建立摘要清單](workflow/create-a-summary-list.md)
         + [豐富資料](workflow/enrich-data.md)
         + [使用彙總](workflow/using-aggregates.md)
         + [使用去重複化活動的合併功能](workflow/deduplication-merge.md)
         + [設定週期性匯入工作流程](workflow/recurring-import-workflow.md)
      + 設計查詢 {#designing-queries}
         + [使用增量查詢更新每季清單](workflow/quarterly-list-update.md)
      + 查詢和篩選器 {#designing-queries}
         + [查詢收件者表格](workflow/querying-recipient-table.md)
         + [查詢傳遞資訊](workflow/query-delivery-info.md)
         + [計算彙總](workflow/compute-aggregates.md)
         + [使用分組管理進行查詢](workflow/query-grouping-management.md)
         + [使用多對多關係進行查詢](workflow/query-many-to-many-relationship.md)
         + [新增分項清單類型計算欄位](workflow/adding-enumeration-type-calculated-field.md)
         + [建立篩選器](workflow/create-a-filter.md)
         + [篩選重複的收件者](workflow/filter-duplicated-recipients.md)
   + 進階設定{#advanced-management}
      + [工作流程屬性](workflow/workflow-properties.md)
      + [高級參數](workflow/advanced-parameters.md)
      + [JavaScript 指令碼和範本](workflow/javascript-scripts-and-templates.md)
      + [工作流程中的 JavaScript 程式碼範例](workflow/javascript-in-workflows.md)
      + [存取外部資料庫](workflow/accessing-an-external-database-fda.md)
      + [管理權限](workflow/managing-rights.md)
      + [變更活動影像](workflow/change-activity-images.md)
      + [管理時區](workflow/managing-time-zones.md)
+ Campaign 策劃 {#campaign-orchestration}
   + [開始使用行銷活動](campaigns/set-up-campaigns.md)
   + [建立方案和行銷活動](campaigns/marketing-campaign-create.md)
   + [建立及設定範本](campaigns/marketing-campaign-templates.md)
   + [新增傳遞](campaigns/marketing-campaign-deliveries.md)
   + [選取客群](campaigns/marketing-campaign-target.md)
   + [管理文件和資產](campaigns/marketing-campaign-assets.md)
   + [設定及管理核准](campaigns/marketing-campaign-approval.md)
   + [循環和定期行銷活動](campaigns/recurring-periodic-campaigns.md)
   + [監視您的行銷活動](campaigns/marketing-campaign-monitoring.md)
   + [供應商、庫存和預算](campaigns/providers-stocks-and-budgets.md)
+ 行銷活動最佳化（附加元件）{#campaign-optimization}
   + [開始使用行銷活動型別](campaign-opt/campaign-typologies.md)
   + [篩選規則](campaign-opt/filtering-rules.md)
   + [控制規則](campaign-opt/control-rules.md)
   + [壓力規則](campaign-opt/pressure-rules.md)
   + [一致性規則](campaign-opt/consistency-rules.md)
   + [套用規則](campaign-opt/apply-rules.md)
   + [Campaign 模擬](campaign-opt/campaign-simulations.md)
+ 行銷資源管理（附加元件）{#mrm}
   + [開始使用行銷資源管理](mrm/about-marketing-resource-management.md)
   + [建立及管理設定檔](mrm/creating-and-managing-tasks.md)
   + [控制成本](mrm/controlling-costs.md)
   + [管理行銷資源](mrm/managing-marketing-resources.md)
   + [論壇](mrm/discussion-forums.md)
+ 分散式行銷（附加元件） {#distributed-marketing}
   + [開始使用分散式行銷](distributed-marketing/about-distributed-marketing.md)
   + [建立本機行銷活動](distributed-marketing/creating-a-local-campaign.md)
   + [建立協作行銷活動](distributed-marketing/creating-a-collaborative-campaign.md)
   + [發佈行銷活動套件](distributed-marketing/publishing-the-campaign-package.md)
   + [存取行銷活動](distributed-marketing/accessing-campaigns.md)
   + [追蹤行銷活動](distributed-marketing/tracking-a-campaign.md)
   + [使用案例](distributed-marketing/examples.md)
+ [&lt;返回Campaign v8檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/campaign-home)
