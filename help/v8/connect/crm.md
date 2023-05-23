---
title: 使用市場活動和您的CRM
description: 瞭解如何與活動和您的CRM協作
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# 將您的CRM與市場活動連接 {#gs-crm}

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的協力廠商系統。透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各協力廠商和企業應用程式輕鬆整合。

這些連接器可實現快速而輕鬆的資料整合：Adobe Campaign提供專門助理，負責從CRM中可用的表格中收集和選擇。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

主要好處是：

* 銷售和營銷之間的一致訊息：Adobe Campaign與您的CRM的整合使系統能夠訪問客戶洞察力和電子郵件營銷歷史，使所有發給客戶的郵件能夠共用相同的一致消息。

* 所有潛在客戶和客戶資料的整體視圖：通過將Adobe Campaign與您的CRM整合，您可以在CRM系統內的每個聯繫人上共用和訪問電子郵件營銷歷史記錄。

* 在任何渠道上激活CRM資料：如果聯繫人資料與Adobe Campaign同步，則可以通過活動（包括移動推送、應用內、電子郵件或直郵）的任何線上或離線渠道發送通信。


>[!NOTE]
>
>此功能可在Adobe Campaign通過 **CRM連接器** 專用包。

## 相容系統 {#compatible-crm-systems-and-limitations}

市場活動中詳細介紹了支援的CRM和版本 [相容性矩陣](../start/compatibility-matrix.md)。

>[!CAUTION]
>
> 市場活動CRM連接器僅使用安全URL(https)。

## 實施步驟 {#crm-implementation-steps}

瞭解將市場活動和Microsoft動態聯繫到 [此頁](ac-ms-dyn.md)。

瞭解將Campaign和Salesforce.com連接到的逐步過程 [此頁](ac-sfdc.md)。

Adobe Campaign和CRM之間的資料同步通過專用工作流活動執行。 構建您的工作流以自動同步市場活動和您的CRM。 您可以建立一個工作流，該工作流通過Microsoft動態導入聯繫人，將其與現有Adobe Campaign資料同步，刪除重複的聯繫人，然後更新Adobe Campaign資料庫。 在[本頁](crm-data-sync.md)中瞭解更多。
