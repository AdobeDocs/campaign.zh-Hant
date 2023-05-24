---
title: 使用Campaign和您的CRM
description: 瞭解如何使用Campaign和您的CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# 將您的CRM與Campaign連線 {#gs-crm}

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的協力廠商系統。透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各協力廠商和企業應用程式輕鬆整合。

這些聯結器可讓您快速輕鬆地整合資料： Adobe Campaign提供專用的助理，可從CRM提供的表格中收集和選取。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

主要優點包括：

* 銷售與行銷之間的一致性傳訊：Adobe Campaign與您的CRM整合，讓兩個系統都能存取客戶分析和電子郵件行銷記錄，讓所有傳送給客戶的訊息都可共用相同的一致性傳訊。

* 所有潛在客戶和客戶資料的整體檢視：透過將Adobe Campaign與您的CRM整合，可以從CRM系統內共用和存取每個連絡人的電子郵件行銷記錄。

* 在任何頻道上啟用您的CRM資料：有了同步至Adobe Campaign的連絡人資料，您就可以透過Campaign在任何線上或離線頻道上傳送通訊，包括行動推播、應用程式內、電子郵件或直接郵件。


>[!NOTE]
>
>此功能可在Adobe Campaign中透過 **CRM聯結器** 專用套件。

## 相容系統 {#compatible-crm-systems-and-limitations}

支援的CRM和版本會在Campaign中詳細說明 [相容性矩陣](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campaign CRM聯結器僅適用於安全URL (https)。

## 實施步驟 {#crm-implementation-steps}

瞭解在中連線Campaign和Microsoft Dynamics的逐步程式 [此頁面](ac-ms-dyn.md).

瞭解在中連線Campaign和Salesforce.com的逐步程式 [此頁面](ac-sfdc.md).

Adobe Campaign與CRM之間的資料同步會透過專用的工作流程活動執行。 建立您的工作流程，以自動化Campaign與您的CRM之間的同步。 您可以建立工作流程，透過Microsoft Dynamics匯入連絡人、將其與現有Adobe Campaign資料同步、刪除重複的連絡人，然後更新Adobe Campaign資料庫。 在[本頁](crm-data-sync.md)中瞭解更多。
