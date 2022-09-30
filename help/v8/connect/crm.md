---
title: 使用Campaign和您的CRM
description: 了解如何使用Campaign和您的CRM
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

這些連接器可讓您快速輕鬆地進行資料整合：Adobe Campaign提供專屬助理，負責從CRM中可用的表格進行收集和選取。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

主要優點包括：

* 銷售與行銷之間的一致報文傳送：Adobe Campaign與您CRM的整合可讓系統同時存取客戶分析和電子郵件行銷記錄，讓所有傳送給客戶的訊息共用相同的一致訊息。

* 全面了解所有潛在客戶和客戶資料：將Adobe Campaign與您的CRM整合後，您就能從CRM系統內分享及存取每個連絡人的電子郵件行銷記錄。

* 在任何通道上啟動您的CRM資料：透過同步至Adobe Campaign的連絡人資料，可透過Campaign在任何線上或離線頻道上傳送通訊，包括行動推播、應用程式內、電子郵件或直接郵件。


>[!NOTE]
>
>此功能可在Adobe Campaign中透過 **CRM連接器** 專屬套件。

## 相容系統 {#compatible-crm-systems-and-limitations}

支援的CRM和版本在Campaign中詳細說明 [相容性矩陣](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campaign CRM連接器僅能搭配安全URL(https)運作。

## 實施步驟 {#crm-implementation-steps}

了解連結Campaign和Microsoft Dynamics的逐步程式，位於 [本頁](ac-ms-dyn.md).

了解連結Campaign和Salesforce.com的逐步程式，位於 [本頁](ac-sfdc.md).

Adobe Campaign和CRM之間的資料同步是透過專用的工作流程活動執行。 建置您的工作流程，以自動同步Campaign和CRM。 您可以建立工作流程，透過Microsoft Dynamics匯入聯絡人、與現有Adobe Campaign資料同步、刪除重複的聯絡人，然後更新Adobe Campaign資料庫。 在[本頁](crm-data-sync.md)中瞭解更多。
