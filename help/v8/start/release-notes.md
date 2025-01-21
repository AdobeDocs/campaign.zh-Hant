---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a4bcb0b540d6e8a426839e77bf81ad30eb93653
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 51%

---

# 最新版本 {#latest-release}

本頁面列出Campaign v8 （主控台） **最新發行版本**&#x200B;的新功能、改善和修正。 在[本頁面](upgrades.md)中進一步瞭解Campaign的發行、版本和升級。 本檔案的先前版本區段將列出其他版本。

## 發行版本 8.6.4 {#release-8-6-4}

_2025年1月15日_

### 一般改善 {#improvements-8-6-4}

* 在[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)內容中的傳遞分析期間，已改善行銷活動應用程式穩定性。
* 此版本隨附改善及增強的FFDA架構機制，包括金鑰管理、測試和資料複製。
* 已為[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。 這些工作流程會集中對應表格上的平行復寫請求，以復寫傳遞和相關資料。 這些工作流程以`Replicate nms`開始。 [閱讀更多](../architecture/replication.md)
* 新的&#x200B;**啟用監督員以保持工作流程永久執行**&#x200B;選項現在可在工作流程屬性中使用。 啟用此選項後，工作流程會在發生錯誤時自動重新啟動。 如果工作流程仍然錯誤，預設會每30秒重新啟動一次。 若要調整此間隔，您可以建立新的`XtkWorkflow_WatchdogTimerTimeout`選項，並設定Integer資料型別以指定新的延遲。 此選項只應在技術工作流程中啟用。 [閱讀更多](../../automation/workflow/workflow-properties.md#execution)

### 安全性改善 {#security-8-6-4}

已更新透過&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帳戶與Adobe解決方案和應用程式的連線，以強化安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。 在[本頁](compatibility-matrix.md#FederatedDataAccessFDA)中深入瞭解。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512 NEO-81520， NEO-81566， NEO-81704， NEO-81908， NEO-82195， NEO-82591， NEO-82592， NEO-82640， NEO-82665， NEO-82781， NEO-82920， NEO-83081 83096 83137 83143。

## 發行版本 8.7.2 {#release-8-7-2}

_2024 年 9 月 3 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-2}

* **新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充連接器。[閱讀全文](../send/sms/sms.md)。

* **豐富推播通知 (GA)** - 您現在可以傳送豐富推播通知。豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* **品牌化** - 品牌化選項現在可供所有管道使用，包括 SMS 和直接郵件。[閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hant){target="_blank"}

### 修正 {#fixes-8-7-2}

此版本已修正下列問題：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。