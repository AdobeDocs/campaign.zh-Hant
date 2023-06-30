---
title: Campaign v8 相容性比較表
description: 發現與 Campaign v8 相容的系統及版本
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 89%

---

# Campaign v8 相容性對照表

本文件列出最新建置版本的 **Adobe Campaign v8** 所支援的所有系統及元件。除非另有提及，否則支援所有次要版本。此清單上未列出的產品和版本即與 Adobe Campaign 不相容。

這些協力廠商系統和工具的特定版本生命週期結束 (EOL) 時，Adobe Campaign 將不再與那些版本相容；我們將不再使用這些系統和功能，後續的產品發行版本亦會將這些系統和功能從我們的相容性對照表中移除。請確保您使用的是相容性對照表所列出的任一系統支援版本，以避免出現任何問題。

>[!NOTE]
>
>Adobe Campaign 伺服器和用戶端主控台必須使用相同版本。 [瞭解如何檢查您的版本](#version)。

## 用戶端主控台{#ClientConsoleoperatingsystems}

使用 Campaign 用戶端主控台時，需要下列作業系統和瀏覽器。[深入瞭解](connect.md)。

### 作業系統{#op-systems}

* **Microsoft Windows 伺服器** 2019、2016、2012
* **Microsoft Windows** 11、10、8

>[!NOTE]
>
>請注意，從8.5版開始，32位元版本的使用者端主控台已過時。 從 8.6 版本開始，用戶端主控台將僅以 64 位元提供。深入了解如何升級作業系統，請參閱此[技術說明](../../technotes/upgrades/console.md)。

### 網頁瀏覽器{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。 從 [Microsoft 開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}下載。

## CRM 連接器{#CRMconnectors}

與 Adobe Campaign 相容的客戶關係管理 (CRM) 系統列於下方。 [深入瞭解](../connect/crm.md)。

* **Salesforce** 連接器 API 49 版本
* **Microsoft Dynamics** 連接器、Web API：Dynamics 365 內部部署與線上

## 同盟資料存取 (FDA){#FederatedDataAccessFDA}

與 Adobe Campaign 同盟資料存取 (FDA) 模組相容的外部資料庫列於下方。 [深入瞭解](../connect/fda.md)。

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, 自 Campaign v8.5 起
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 行動 SDK{#MobileSDK}

若要透過 Campaign 傳送[推播通知](../send/push.md)，請在資料收集 UI 設定 Adobe Campaign Classic 擴充功能，以使用 Adobe Experience Platform Mobile SDK。


## 網路存取{#web-access}

下列瀏覽器與 Campaign for [Web Access](connect.md#web-access) 相容。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** (最新版本)

## 如何檢查您的 Campaign 版本與版本編號{#version}

使用 **說明 > 關於…** 選單檢查您的版本。

![](assets/ac-version.png)

您可存取下列資訊：

* 此 **版本** 使用者端主控台和應用程式伺服器的數目。 在上述範例中，使用者端主控台和應用程式伺服器的版本為8.1.5。
* 括弧之間的 SHA 編號。
* 聯絡 Adobe 客戶服務的連結.
* 導覽至 Adobe 隱私權政策、使用條款與 Cookie 政策的連結.
