---
solution: Campaign
product: Adobe Campaign
title: Campaign v8相容性矩陣
description: 瞭解與Campaign v8相容的系統和版本
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 1ac6b58e1d5731d4df4d6d7c6a9b25f0f41ff563
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 24%

---

# Campaign v8相容性矩陣

本檔案列出&#x200B;**Adobe Campaignv8**&#x200B;最新版本支援的所有系統和元件。 不屬於此清單的產品和版本與 Adobe Campaign 不相容。

>[!CAUTION]
>
>* 除非另有提及，否則支援所有次要版本。
>* 由於這些協力廠商系統和工具的特定版本已到期(EOL),Adobe Campaign將不再與這些版本相容，而且將從此相容性矩陣中移除。 請確保您使用相容性矩陣列出的任何系統的支援版本，以避免出現任何問題。


## 相容系統

### 客戶端控制台{#ClientConsoleoperatingsystems}

:warning:使用「促銷活動用戶端主控台」時，需要下列作業系統和瀏覽器。

**作業系統**

* **Microsoft Windows Server**  2016、2012
* **Microsoft Windows** 8、10（建議用於日文例項）

**瀏覽器**

**Microsoft Internet Explorer** 11

### CRM 連接器{#CRMconnectors}

* **** Salesforcconnector API 49版
* **Microsoft** Dynamicsconnector、Web API:Dynamics 365內部部署與線上

### 同盟資料存取 (FDA){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c、18c、12c、11G
* **PostgreSQL** 12.x、11.x、10.x、9.6.x、9.5.x、9.4.x
* **Microsoft SQL Server**  2019、2017、2016、2014、2012 SP1和SP2
* **MySQL**  5.7
* **Teradata** 16.20、16、15.10、15.0
* **Netezza** 7.2
* **sybase IQ** 16,ASE 15.7
* **SAP** HANA第1版SPS 12
* **透過 HiveSQL 提供的 Hadoop**
   * HortonWorks HDP 2.4.X、2.5.x、2.6.x
   * HDInsight 3.4 (HDP 2.4)、3.5 (HDP 2.5)、3.6 (HDP 2.6
   * Cloudera CDH6.x

### 行動 SDK{#MobileSDK}

* **Android** 7.x、8.x、9.0（含行動SDK組建版本1.0.27）。
* **Apple iOS**  9 - 14含行動SDK組建版本1.0.26，與32和64位元版本相容。

### 支援的瀏覽器{#Browsers}

下列瀏覽器與Campaign for Web Access相容。

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome**、 **Safari** （最新版本）

* **Internet Explorer** 11

## 如何檢查您的促銷活動版本

**說明>關於……**&#x200B;功能表可讓您存取下列資訊：

* 促銷活動用戶端主控台及應用程式伺服器的版本號碼
* 促銷活動用戶端主控台和應用程式伺服器的組建編號
* 連絡Adobe客戶服務
* Adobe隱私權政策、使用條款與Cookie政策的連結
