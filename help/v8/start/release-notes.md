---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 041df8d2d6128d72a04008affbc9680ba5b640a1
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 18%

---

# 最新版本 {#latest-release}

本頁面列出Campaign v8 （主控台） **最新發行版本**&#x200B;的新功能、改善和修正。 在[本頁面](upgrades.md)中進一步瞭解Campaign的發行、版本和升級。 本檔案的先前版本區段將列出其他版本。

>[!BEGINSHADEBOX]

**在此頁面**

* Campaign v8.6 - [版本8.6.4](#release-8-6-4)
* Campaign v8.7 - [版本8.7.3](#release-8-7-3)

>[!ENDSHADEBOX]


## 發行版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#features-8-7-3}

* **異動訊息的動態報告** — 您現在可以在動態報告使用者介面中監視異動訊息。 這些報表可讓行銷人員即時檢視異動訊息的所有報表量度和維度，以及透過範本傳送的傳送劃分。 [閱讀全文](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **異動訊息REST API** — 事件型異動API現在可用於電子郵件。 [閱讀全文](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### 修正 {#fixes-8-7-3}

此版本已修正下列問題：

NEO-79373， NEO-81908， NEO-83081。


## 發行版本 8.6.4 {#release-8-6-4}

_2025年1月15日_

### 一般改善 {#improvements-8-6-4}

* 在[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)內容中的傳遞分析期間，已改善行銷活動應用程式穩定性。
* 此版本隨附改善及增強的FFDA架構機制，包括金鑰管理、測試和資料複製。
* 已為[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。 這些工作流程會集中對應表格上的平行復寫請求，以復寫傳遞和相關資料。 這些工作流程以`Replicate nms`開始。 [閱讀更多](../architecture/replication.md)
* 新的&#x200B;**啟用監督員以保持工作流程永久執行**&#x200B;選項現在可在工作流程屬性中使用。 啟用此選項後，工作流程會在發生錯誤時自動重新啟動。 如果工作流程仍然錯誤，預設會每30秒重新啟動一次。 若要調整此間隔，您可以建立新的`XtkWorkflow_WatchdogTimerTimeout`選項，並設定Integer資料型別以指定新的延遲。 此選項只應在技術工作流程中啟用。 [閱讀更多](../../automation/workflow/workflow-properties.md#execution)

### 安全性改善 {#security-8-6-4}

透過&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帳戶與Adobe解決方案和應用程式的連線已更新，以加強安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

已新增下列FDA聯結器。 請參閱此[頁面](compatibility-matrix.md#FederatedDataAccessFDA)。

* Databricks現在可支援為具有Adobe Campaign同盟資料存取(FDA)的外部資料庫。

* 全新Amazon Redshift FDA ODBC聯結器現已推出。 提供更優異的連線能力、更輕鬆的維護作業，以及更優異的相容性。 此新版本提供下列改善專案：

   * 新的聯結器以ODBC介面為基礎，與我們最新的FDA聯結器一致。 這可確保長期支援。
   * 此外也引進了使用s3貯體的新資料載入機制，大幅改善效能。

  仍可使用舊版聯結器。 如果您想要試用新版應用程式，請洽詢您的Adobe代表。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512 NEO-81520， NEO-81566， NEO-81704， NEO-81908， NEO-82195， NEO-82591， NEO-82592， NEO-82640， NEO-82665， NEO-82781， NEO-82920， NEO-83081 83096 83137 83143。

