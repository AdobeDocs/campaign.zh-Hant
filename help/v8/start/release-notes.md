---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 9187ac7fd0d17a6dc28c3b6564913bcd93e45943
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 最新版本 {#latest-release}

本頁面列出 Campaign v8 (主控台) **最新版本**&#x200B;中的新功能、改善和修正。在[此頁面](upgrades.md)進一步了解 Campaign 行銷活動發布、版本和更新。本文件的先前版本區段將列出其他版本。

>[!BEGINSHADEBOX]

**在此頁面上**

* [發行版本 8.6.5](#release-8-6-5)
* [發行版本 8.7.4](#release-8-7-4)
* [發行版本 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## 發行版本 8.6.5 {#release-8-6-5}

_2025 年 4 月 25 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。

### 新功能 {#features-8-6-5}

**新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充連接器。[閱讀全文](../send/sms/sms.md)。

### 一般改善 {#improvements-8-6-5}

* 在企業 (FFDA) 部署的情境下，應用程式的全域效能已改善，包括傳遞證明傳送和資料庫清理。

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

* 郵件傳輸代理程式 (MTA) — 已修正孤立 MTA 子代理卡在 **[!UICONTROL Start pending]** 狀態的問題。

### 修正 {#fixes-8-6-5}

此版本還修正下列問題：

NEO-67620、NEO-71534、NEO-80245、NEO-81105、NEO-81758、NEO-81908、NEO-82351、NEO-82742、NEO-83044、NEO-83138、NEO-83350、NEO-83729、NEO-83793、NEO-83809、NEO-84038、NEO-84108、NEO-85269、NEO-86121、NEO-86556、NEO-86739

## 發行版本 8.7.4 {#release-8-7-4}

_2025 年 4 月 10 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#features-8-7-4}

* **簡訊 REST API 支援** - 交易型傳訊 REST API 現在已可用於簡訊頻道。當承載中同時存在 email 和 mobilePhone 時，您可以使用「wishedChannel」欄位來指定頻道。如果未提供，除非 wishedChannel 明確地要求簡訊，否則預設會使用電子郵件。

* **多語言傳送** - 自 4 月發行的 Campaign Web 使用者介面版本起，您將能夠以不同語言傳送多封電子郵件，並存取相關的動態報告。此功能僅於 4 月底在 Adobe Campaign Web 使用者介面中提供，且需要伺服器更新至 Campaign v8.7.4。

### 修正 {#fixes-8-7-4}

此版本已修正下列問題：

NEO-80245、NEO-83559

## 發行版本 8.6.4 {#release-8-6-4}

_2025 年 1 月 15 日_

### 一般改善 {#improvements-8-6-4}

* 已改善 Campaign 應用程式在[企業 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)情境下的傳遞分析期間的穩定性。
* 此版本隨附改善及增強的 FFDA 架構機制，包括金鑰管理、暫存和資料複寫。
* 已為[企業 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。這些工作流程會集中對應表格上的平行複寫請求，以複寫傳遞和相關資料。這些工作流程以 `Replicate nms` 開始。[閱讀更多](../architecture/replication.md)
* 新的&#x200B;**啟用監督者以保持工作流程永久執行**&#x200B;選項現在可在工作流程屬性中使用。啟用此選項後，工作流程會在發生錯誤時自動重新啟動。如果工作流程仍然錯誤，預設會每 30 秒重新啟動一次。若要調整此間隔，您可以建立新的 `XtkWorkflow_WatchdogRestartTimerTimeout` 選項，並設定整數資料類型以指定新的延遲。此選項只應在技術工作流程中啟用。[閱讀更多](../../automation/workflow/workflow-properties.md#execution)

### 安全性改善 {#security-8-6-4}

透過 **[!UICONTROL Adobe Experience Cloud]** 外部帳戶與 Adobe 解決方案和應用程式的連線已更新，以加強安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

已新增下列 FDA 連接器。請參見此[頁面](compatibility-matrix.md#FederatedDataAccessFDA)。

* 現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。

* 全新 Amazon Redshift FDA ODBC 連接器現已推出。提供更優異的連線能力、更輕鬆的維護作業，以及更優異的相容性。此新版本帶來下列改進：

   * 新的連接器以 ODBC 介面為基礎，與我們最新的 FDA 連接器一致。這可確保長期支援。
   * 此外也引進了使用 s3 儲存貯體的新資料載入機制，大幅改善效能。

  仍可使用舊版連接器。如果您想要試用新版連接器，請洽詢您的 Adobe 代表。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512、NEO-81520、NEO-81566、NEO-81704、NEO-81908、NEO-82195、NEO-82591、NEO-82592、NEO-82640、NEO-82665、NEO-82781、NEO-82920、NEO-83081、NEO-83096、NEO-83137、NEO-83143。

