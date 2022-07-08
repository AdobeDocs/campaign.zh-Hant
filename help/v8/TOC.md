---
audience: end-user
user-guide-title: Campaign v8
description: Campaign v8 文件
breadcrumb-title: Campaign v8
title: Campaign v8 文件
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: ht
source-wordcount: '352'
ht-degree: 100%

---


# Adobe Campaign v8 文件 {#campaign-v8}

+ [Campaign v8 文件](campaign-home.md)
+ 有哪些新增功能？{#new}
   + [主要功能](start/whats-new.md)
   + [發行說明](start/release-notes.md)
   + [護欄](start/ac-guardrails.md)
   + [已知問題](start/known-issues.md)
   + [Classic v7 到 v8](start/v7-to-v8.md)
+ 開始 {#start}
   + [開始使用](start/get-started.md)
   + [元件與流程](start/ac-components.md)
   + Campaign UI {#ac-ui}
      + [瞭解 Campaign 介面](start/campaign-ui.md)
      + [自訂 Campaign 介面](start/customize-ui.md)
   + [配合受眾](start/audiences.md)
   + [管理隱私權請求](start/privacy.md)
   + [匯入資料](start/import.md)
   + [建立行銷活動](start/campaigns.md)
   + [傳送訊息](start/create-message.md)
   + [管理訂閱](start/subscriptions.md)
   + [追蹤與監視](start/tracking.md)
   + [指標與報吿](start/reporting.md)
   + [常見問答集](start/campaign-faq.md)
+ 架構 {#architecture}
   + [全域原則](architecture/general-architecture.md)
   + [架構](architecture/architecture.md)
   + FDA Snowflake 部署 {#fda}
      + [什麼是 FDA-Snowflake?](architecture/fda-deployment.md)
   + 企業 (FFDA) 部署 {#ffda}
      + [什麼是 Campaign FFDA？](architecture/enterprise-deployment.md)
      + 特性 {#ffda-characteristics}
         + [金鑰管理和唯一性](architecture/keys.md)
         + [新 API](architecture/new-apis.md)
         + [API 準備機制](architecture/staging.md)
         + [複製機制](architecture/replication.md)
+ 實施 {#implement}
   + [實施步驟](start/implement.md)
   + [自訂您的執行個體](dev/customize.md)
   + [安全性方針](config/security.md)
   + [設計網頁應用程式和表單](dev/webapps.md)
   + [資料模型最佳實務](dev/datamodel-best-practices.md)
+ 部署{#deploy}
   + [相容性矩陣](start/compatibility-matrix.md)
   + [連結至 Campaign](start/connect.md)
   + [權限](start/permissions.md)
   + [控制面板](config/self-service.md)
+ 設定檔和受眾 {#profiles-and-audiences}
   + [開始使用](audiences/gs-audiences.md)
   + [存取設定檔](audiences/view-profiles.md)
   + 新增設定檔 {#add-profiles}
      + [手動建立設定檔](audiences/create-profiles.md)
      + [從檔案匯入設定檔](audiences/import-profiles.md)
      + [使用外部設定檔](audiences/external-profiles.md)
      + [在網路表單中收集設定檔資料](audiences/collect-profiles.md)
   + 建立對象 {#create-audiences}
      + [建立連絡人清單](audiences/create-audiences.md)
      + [建立及管理篩選器](audiences/create-filters.md)
   + [管理資料夾和檢視](audiences/folders-and-views.md)
   + [最佳實務](audiences/audiences-best-practices.md)
+ 傳送訊息{#send}
   + 電子郵件 {#emails}
      + [設計和驗證電子郵件](send/email.md)
      + [傳送和監視電子郵件](send/send.md)
   + [SMS](send/sms.md)
   + [推播通知](send/push.md)
   + [LINE 傳送訊息](send/line.md)
   + [直接郵件](send/direct-mail.md)
   + [社交行銷](send/twitter.md)
   + [異動訊息](send/transactional.md)
   + 失敗、邊界和隔離{#failures}
      + [隔離](send/quarantines.md)
      + [傳遞失敗](send/delivery-failures.md)
+ 即時互動{#interaction}
   + [開始使用即時互動](interaction/interaction.md)
   + [環境與架構](interaction/interaction-architecture.md)
   + [最佳實務](interaction/interaction-best-practices.md)
   + 定義設定{#interaction-settings}
      + [建立運算子](interaction/interaction-operators.md)
      + [建立環境](interaction/interaction-env.md)
      + [建立預先定義的篩選器](interaction/interaction-predefined-filters.md)
      + [建立優惠方案空間](interaction/interaction-offer-spaces.md)
   + [建立優惠方案目錄](interaction/interaction-offer-catalog.md)
   + [建立優惠優惠方案](interaction/interaction-offer.md)
   + [傳送優惠方案(傳出)](interaction/interaction-send-offers.md)
   + 呈現優惠方案 (傳入){#inbound}
      + [內容](interaction/interaction-present-offers.md)
      + [呼叫網頁中的優惠](interaction/interaction-integration.md)
      + [管理匿名互動](interaction/anonymous-interactions.md)
   + [報告和歷史記錄](interaction/interaction-tracking.md)
   + [使用案例](interaction/interaction-use-cases.md)
+ 設定 {#config}
   + [使用工作流程自動化](config/workflows.md)
   + [電子郵件設定](config/email-settings.md)
   + [異動訊息設定](config/transactional-msg-settings.md)
   + [將 Campaign SDK 與您的應用程式整合](config/push-config.md)
   + [外部帳戶](config/external-accounts.md)
+ 連結 {#connect}
   + [連結其他解決方案](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud 觸發程式](connect/ac-triggers.md)
   + [Campaign + RTCDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + 外部資料庫](connect/fda.md)
   + Campaign + 您的 CRM{#ac-crm}
      + [開始使用 CRM 連接器](connect/crm.md)
      + [使用 Campaign 及 SFDC](connect/ac-sfdc.md)
      + [使用 Campaign 及 Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [同步資料](connect/crm-data-sync.md)
+ 開發人員資源{#developer}
   + [促銷活動資料模型](dev/datamodel.md)
   + 方案和表單{#shemas-forms}
      + [使用方案](dev/schemas.md)
      + [建立方案](dev/create-schema.md)
      + [擴充方案](dev/extend-schema.md)
      + [篩選結構](dev/filter-schema.md)
      + [方案結構](dev/schema-structure.md)
      + [資料庫對應](dev/database-mapping.md)
      + [限制 PI 檢視](dev/restrict-pi-view.md)
      + [使用自訂收件者表格](dev/custom-recipient.md)
      + [更新資料庫](dev/update-database-structure.md)
      + [輸入表單](dev/forms.md)
   + [Campaign API](dev/api.md)
+ [Campaign 控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)

