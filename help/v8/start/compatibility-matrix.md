---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8相容性矩陣
description: 了解與Campaign v8相容的系統和版本
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: ffdfc9a2e1bec191b5a3cc7f7b40683b2456bf3e
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---

# Campaign v8相容性矩陣

本檔案列出&#x200B;**Adobe Campaign v8**&#x200B;最新建置支援的所有系統和元件。 不屬於此清單的產品和版本與 Adobe Campaign 不相容。

>[!CAUTION]
>
>* 除非另有提及，否則支援所有次要版本。
>* 由於這些協力廠商系統和工具的特定版本即將終止(EOL),Adobe Campaign將不再與這些版本相容，並將從此相容性矩陣中移除。 請確保您使用相容性矩陣列出的任何系統的支援版本，以避免出現任何問題。


## 相容系統

### 用戶端主控台{#ClientConsoleoperatingsystems}

:warning: 使用「Campaign 用戶端主控台」時，需要下列作業系統和瀏覽器。

**作業系統**

* **Microsoft Windows Server**  2016、2012
* **Microsoft Windows**  8、10（建議用於日文執行個體）

**瀏覽器**

**Microsoft Internet Explorer** 11

### CRM 連接器{#CRMconnectors}

* **** Salesforcconnector API 49版
* **Microsoft** Dynamicsconnector, Web API:內部部署和線上Dynamics 365

### 同盟資料存取 (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### 行動 SDK{#MobileSDK}

* **Android**  7.x、8.x、9.0（含行動SDK版本編號1.0.27）。
* **Apple iOS**  9 - 14搭配行動SDK版本編號1.0.26，與32和64位元版本相容。

### 受支援的瀏覽器 {#Browsers}

下列瀏覽器與 Campaign for Web Access 相容。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** （最新版本）

* **Internet Explorer** 11

## 如何檢查您的Campaign版本

使用&#x200B;**Help > About...**&#x200B;功能表檢查您的版本。

![](assets/ac-version.png)

您可存取下列資訊：

* 客戶端控制台和應用程式伺服器的&#x200B;**版本**&#x200B;編號。 在上例中，客戶端控制台和應用程式伺服器的版本為8.1.5。
* 括弧之間的SHA號。
* 連絡Adobe客戶服務的連結。
* Adobe隱私權原則、使用條款和Cookie原則的連結。
