---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 16%

---

# 最新版本 {#latest-release}

本頁面列出Campaign v8 （主控台） **最新發行版本**&#x200B;的新功能、改善和修正。 在此頁面](upgrades.md)中[了解有關Campaign版本、版本和升級的詳細信息。本文檔的上一個版本部分中列出了其他版本。

>[!BEGINSHADEBOX]

**在此頁面**

* [發行版本 8.7.4](#release-8-7-4)
* [發行版本 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## 發行版本 8.7.4 {#release-8-7-4}

_4月10， 2025_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為過渡到 Campaign v8 用戶Campaign Standard，請在 Campaign v8 Web 用戶 介面文檔中](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}了解有關[此轉變的更多信息。

### 新功能 {#features-8-7-4}

* **SMS REST API支援** — 異動訊息REST API現在可用於SMS頻道。 當電子郵件和行動電話都出現在有效負載中時，您可以使用「widedChannel」欄位來指定頻道。 如果未提供，默認情況下將使用電子郵件，除非希望Channel明確請求簡訊。

* **多語言傳遞** - 從 Web 使用者介面 4 月版本 Campaign 開始，您將能夠以不同的語言發送多個電子郵件傳遞，並存取相關的動態報告。 此功能僅在 4 月底Adobe Campaign Web 使用者介面中可用，並且需要伺服器更新才能Campaign v8.7.4。

### 修正 {#fixes-8-7-4}

此版本已修正下列問題：

NEO-80245， NEO-83559

## 發行版本 8.6.4 {#release-8-6-4}

_1月15， 2025_

### 一般改善 {#improvements-8-6-4}

* 在[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)內容中的傳遞分析期間，已改善行銷活動應用程式穩定性。
* 此版本隨附改善及增強的FFDA架構機制，包括金鑰管理、測試和資料複製。
* 已為[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。 這些工作流程通過將並行複製請求集中在相應表上來複製傳遞和相關數據。 這些工作流程開始。`Replicate nms`[閱讀更多](../architecture/replication.md)
* 工作流程屬性中現在提供了新的 **「啟用監視程式主管以保持工作流程永久** 運行」選項。 啟用此選項後，工作流程發生錯誤後自動重新啟動。 如果工作流程仍然錯誤，則預設每 30 秒重新啟動一次。 若要調整此間隔，可以創建新 `XtkWorkflow_WatchdogRestartTimerTimeout` 選項並設置 Integer 資料類型以指定新的延遲。 此選項只能在 技術工作流程 中啟用。 [閱讀更多](../../automation/workflow/workflow-properties.md#execution)

### 安全性改善 {#security-8-6-4}

透過 **[!UICONTROL Adobe Experience Cloud]** 外部帳戶與 Adobe 解決方案和應用程式的連線已更新，以加強安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

已新增下列FDA聯結器。 請參閱此[頁面](compatibility-matrix.md#FederatedDataAccessFDA)。

* Databricks現在可支援為具有Adobe Campaign同盟資料存取(FDA)的外部資料庫。

* 現已推出全新的 Amazon Redshift FDA ODBC 連接器。 它提供了改進的連接性、更易於維護和增強的相容性。 這個新版本帶來了以下改進：

   * 新連接器基於 ODBC 介面，該介面與我們最新的 FDA 連接器保持一致。 這確保了長期支援。
   * 它還引入了使用 s3 儲存桶的新數據載入機制，從而顯著提高了性能。

  舊版連接器仍可使用。 如果您想嘗試新的，請聯繫您的Adobe 代表。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512 NEO-81520， NEO-81566， NEO-81704， NEO-81908， NEO-82195， NEO-82591， NEO-82592， NEO-82640， NEO-82665， NEO-82781， NEO-82920， NEO-83081 83096 83137 83143。

