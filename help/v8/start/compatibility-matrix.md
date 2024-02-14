---
title: Campaign v8 相容性比較表
description: 發現與 Campaign v8 相容的系統及版本
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 374c0df2cd95e656cfbaa1fb355bf1f48828dfee
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 63%

---

# Campaign v8 相容性比較表 {#compat-matrix}

本檔案列出最新建置版本支援的所有系統和元件 **Adobe Campaign v8** 使用者端主控台。 除非另有提及，否則支援所有次要版本。此清單上未列出的產品和版本即與 Adobe Campaign 不相容。

這些協力廠商系統和工具的特定版本生命週期結束 (EOL) 時，Adobe Campaign 將不再與那些版本相容；我們將不再使用這些系統和功能，後續的產品發行版本亦會將這些系統和功能從我們的相容性對照表中移除。請確保您使用的是相容性對照表所列出的任一系統支援版本，以避免出現任何問題。

>[!NOTE]
>
>Adobe Campaign伺服器和Campaign使用者端主控台必須使用相同版本。 [瞭解如何檢查您的版本](upgrades.md#version)。

## 用戶端主控台 {#ClientConsoleoperatingsystems}

使用Campaign使用者端主控台時，需要使用下列作業系統和瀏覽器。 [深入瞭解](connect.md)。

### 作業系統{#op-systems}

* **Microsoft Windows Server** 2019、2016
* **Microsoft Windows** 11， 10

>[!NOTE]
>
>請注意，使用者端主控台的32位元版本自8.5版本以來已過時。 從8.6版本開始，使用者端主控台僅提供64位元版本。 有關如何升級系統的詳細資訊，請參閱此 [技術備註](../../technotes/upgrades/console.md).

### 網頁瀏覽器 {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。 從 [Microsoft 開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}下載。

## CRM 連接器 {#CRMconnectors}

與 Adobe Campaign 相容的客戶關係管理 (CRM) 系統列於下方。 [深入瞭解](../connect/crm.md)。

* **Salesforce** 連接器 API 49 版本
* **Microsoft Dynamics** 連接器、Web API：Dynamics 365 內部部署與線上

## 同盟資料存取 (FDA){#FederatedDataAccessFDA}

與 Adobe Campaign 同盟資料存取 (FDA) 模組相容的外部資料庫列於下方。 [深入瞭解](../connect/fda.md)。

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**，自Campaign v8.5開始
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 行動 SDK {#MobileSDK}

若要透過 Campaign 傳送[推播通知](../send/push.md)，請在資料收集 UI 設定 Adobe Campaign Classic 擴充功能，以使用 Adobe Experience Platform Mobile SDK。

iOS和Android的相容版本詳見 [Adobe Developer檔案](https://developer.adobe.com/client-sdks/home/)

## 網路存取 {#web-access}

下列瀏覽器與 Campaign for [Web Access](connect.md#web-access) 相容。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** (最新版本)


## 額外資源 {#support}

* [Campaign版本更新](upgrades.md)
* [檢查您的Campaign版本](upgrades.md#version)
* [安裝Campaign使用者端主控台](connect.md)
* [控制面板發行版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hant){target="_blank"}.

若要接收最新Experience Cloud解決方案發行版本的通知，請訂閱 [Adobe優先順序產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target="_blank"}.