---
title: 使用Campaign和您的CRM
description: 瞭解如何使用Campaign和您的CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/gYGdySWZC1j2VkvAkL9rVBes7iQvRkRjNjm-dvFsHBM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: beb7a3c1-66ab-4786-b879-7621375b3c40id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 20%

---

# 將您的CRM與Campaign連線 {#gs-crm}

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的第三方系統。 透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各第三方和企業應用程式輕鬆整合。

這些聯結器可讓您快速輕鬆地整合資料：Adobe Campaign提供專用的助理，可從CRM提供的表格中進行收集和選取。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

主要優點包括：

* 銷售與行銷之間有一致性的訊息：Adobe Campaign與您的CRM整合，讓系統都能存取客戶insight，並透過電子郵件行銷記錄，讓所有傳送給客戶的訊息能夠共用相同的一致性訊息。

* 所有潛在客戶和客戶資料的整體檢視：透過將Adobe Campaign與您的CRM整合，您可以在CRM系統中共用和存取每個連絡人的電子郵件行銷記錄。

* 在任何頻道上啟用您的CRM資料：有了同步至Adobe Campaign的連絡人資料，您便可以在任何使用Campaign的線上或離線頻道上傳送通訊，包括行動推播、應用程式內、電子郵件或直接郵件。


>[!NOTE]
>
>此功能可透過&#x200B;**CRM聯結器**&#x200B;專用套件在Adobe Campaign中使用。

## 相容系統 {#compatible-crm-systems-and-limitations}

支援的CRM和版本在Campaign [相容性矩陣](../start/compatibility-matrix.md)中詳細說明。

>[!CAUTION]
>
> Campaign CRM聯結器僅適用於安全URL (https)。

## 實施步驟 {#crm-implementation-steps}

瞭解在[此頁面](ac-ms-dyn.md)中連線Campaign和Microsoft Dynamics的逐步程式。

在[此頁面](ac-sfdc.md)中瞭解連線Campaign和Salesforce.com的逐步程式。

Adobe Campaign與CRM之間的資料同步會透過專用的工作流程活動執行。 建置您的工作流程以自動化Campaign與您的CRM之間的同步。 您可以建立工作流程，透過Microsoft Dynamics匯入連絡人、將其與現有的Adobe Campaign資料同步、刪除重複的連絡人，然後更新Adobe Campaign資料庫。 在[本頁](crm-data-sync.md)中瞭解更多。
