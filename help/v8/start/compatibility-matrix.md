---
title: Campaign v8 相容性矩陣
description: 發現與 Campaign v8 相容的系統及版本
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: ba27d1e56f7354e500e747f01a27412f8d553e2b
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 97%

---

# Campaign v8 相容性矩陣 {#compat-matrix}

本文件列出最新建置版本的 **Adobe Campaign v8** 用戶端主控台所支援的所有系統及元件。除非另有提及，否則支援所有次要版本。此清單上未列出的產品和版本即與 Adobe Campaign 不相容。

這些協力廠商系統和工具的特定版本生命週期結束 (EOL) 時，Adobe Campaign 將不再與那些版本相容；我們將不再使用這些系統和功能，後續的產品發行版本亦會將這些系統和功能從我們的相容性對照表中移除。請確保您使用的是相容性對照表所列出的任一系統支援版本，以避免出現任何問題。

>[!NOTE]
>
>Adobe Campaign 伺服器和 Campaign 用戶端主控台必須使用相同版本。 [瞭解如何檢查您的版本](upgrades.md#version)。

## 用戶端主控台 {#ClientConsoleoperatingsystems}

使用 Campaign 用戶端主控台時，需要使用下列作業系統和瀏覽器。 [深入瞭解](connect.md)。

### 作業系統 {#op-systems}

* **Microsoft Windows Server** 2019、2016
* **Microsoft Windows** 11、10

>[!NOTE]
>自 8.5 版本發行之後，已淘汰 32 位元版本的用戶端主控台。從 8.6 版本開始，用戶端主控台將僅以 64 位元提供。深入了解如何升級系統，請參閱此[技術說明](../../technotes/upgrades/console.md)。

### 網頁瀏覽器 {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。 從 [Microsoft 開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}下載。

## CRM 連接器 {#CRMconnectors}

與 Adobe Campaign 相容的客戶關係管理 (CRM) 系統列於下方。 在[本頁面](../connect/crm.md)中進一步瞭解 CRM 連接器。

* **Salesforce** 連接器 API 49 版本
* **Microsoft Dynamics** 連接器、Web API：Dynamics 365 內部部署與線上

## 同盟資料存取 (FDA){#FederatedDataAccessFDA}

與 Adobe Campaign 同盟資料存取 (FDA) 模組相容的外部資料庫列於下方。 在[本頁面](../connect/fda.md)中深入了解 FDA。

* **[!DNL Amazon Redshift]** ODBC聯結器，從Campaign v8.6.4開始
* **[!DNL Amazon Redshift]**&#x200B;舊聯結器
* **[!DNL Azure Synapse]** (自 Campaign v8.5 起)
* **[!DNL Databricks]**，從Campaign v8.6.4 / v8.7開始
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**


>[!AVAILABILITY]
>此外，使用[增強式安全性附加元件](../config/enhanced-security.md#secure-vpn-tunneling)，您可以透過安全 VPN 通道存取內部部署資料庫。 [了解更多](../config/enhanced-security.md#vpn-callouts)

## 行動 SDK {#MobileSDK}

若要透過 Campaign 傳送[推播通知](../send/push.md)，請在資料收集 UI 設定 Adobe Campaign Classic 擴充功能，以使用 Adobe Experience Platform Mobile SDK。

iOS 與 Android 的相容版本詳見 [Adobe Developer 文件](https://developer.adobe.com/client-sdks/home/){target="_blank"}。

## 網頁使用者介面 {#web-ui}

下列瀏覽器與 Campaign Web 使用者介面相容。在[本頁面](campaign-ui.md#ac-web-ui)中進一步瞭解 Campaign Web UI。

* **Microsoft Edge**、**Google Chrome**、**Safari** (最新版本)

## 網路存取 {#web-access}

下列瀏覽器與 Campaign for Web Access 相容。在[本頁面](connect.md#web-access)中進一步瞭解 Campaign Web Access。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** (最新版本)

## 額外資源 {#support}

* [Campaign 發布內容更新](upgrades.md)
* [查看您的 Campaign 版本](upgrades.md#version)
* [安裝 Campaign 用戶端控制台](connect.md)
* [控制面板發行版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hant){target="_blank"}

若要接收最新 Experience Cloud 解決方案發行版本的通知，請訂閱 [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target="_blank"}。