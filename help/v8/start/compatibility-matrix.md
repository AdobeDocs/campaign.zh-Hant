---
title: Campaign v8 相容性對照表
description: 瞭解與 Campaign v8 相容的系統和版本
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '274'
ht-degree: 100%

---

# Campaign v8 相容性對照表

本文件列出最新建置版本的 **Adobe Campaign v8** 所支援的所有系統及元件。除非另有提及，否則支援所有次要版本。此清單上未列出的產品和版本即與 Adobe Campaign 不相容。

這些協力廠商系統和工具的特定版本生命週期結束 (EOL) 時，Adobe Campaign 將不再與那些版本相容；我們將不再使用這些系統和功能，後續的產品發行版本亦會將這些系統和功能從我們的相容性對照表中移除。請確保您使用的是相容性對照表所列出的任一系統支援版本，以避免出現任何問題。

## 用戶端主控台{#ClientConsoleoperatingsystems}

>[!CAUTION]
>
> 使用 Campaign 用戶端主控台時，需要使用下列作業系統和瀏覽器。

### 作業系統

* **Microsoft Windows Server** 2016、2012
* **Microsoft Windows** 8、10 (建議日文執行個體使用))

### 瀏覽器

**Microsoft Internet Explorer** 11

## CRM 連接器{#CRMconnectors}

* **Salesforce** 連接器 API 49 版本
* **Microsoft Dynamics** 連接器、Web API：Dynamics 365 內部部署與線上

## 同盟資料存取 (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 行動 SDK{#MobileSDK}

* **Android** 7.x、8.x、9.0 (含 Campaign Android SDK 版本編號 1.1.1)。
* **Apple iOS** 9 - 14 與 Campaign iOS SDK 版本編號 1.0.26 (32 位元 及 64 位元) 版本相容。

## 網路存取

下列瀏覽器與 Campaign for Web Access 相容。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** (最新版本)

* **Internet Explorer** 11

## 如何檢查您的 Campaign 版本及版本編號

使用 **說明 > 關於…** 選單檢查您的版本。

![](assets/ac-version.png)

您可存取下列資訊：

* Campaign 用戶端控制台及應用程式伺服器的&#x200B;**版本**&#x200B;號碼。在上述例子中，客戶端主控台和應用程式伺服器的版本為 8.1.5。
* 括弧之間的 SHA 編號。
* 聯絡 Adobe 客戶服務的連結.
* 導覽至 Adobe 隱私權政策、使用條款與 Cookie 政策的連結.
