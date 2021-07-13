---
product: Adobe Campaign
title: 使用Campaign和您的CRM
description: '了解如何使用Campaign和您的CRM '
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 25%

---

# 將您的CRM與Campaign連線 {#gs-crm}

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的協力廠商系統。透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各協力廠商和企業應用程式輕鬆整合。

這些連接器可讓您快速輕鬆地進行資料整合：Adobe Campaign提供專屬助理，負責從CRM中可用的表格進行收集和選取。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

>[!NOTE]
>
>此功能可在Adobe Campaign中透過&#x200B;**CRM連接器**&#x200B;專用套件取得。

## 相容系統 {#compatible-crm-systems-and-limitations}

支援的CRM和版本在Campaign [相容性矩陣](../start/compatibility-matrix.md)中詳細說明。

??CRM連接器只能搭配安全URL(https)運作。

## 實施步驟 {#crm-implementation-steps}

↗️在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)中了解連接Campaign和Microsoft Dynamics的逐步程式

↗️在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)中了解連接Campaign和Salesforce的逐步程式


Adobe Campaign和CRM之間的資料同步是透過專用的工作流程活動執行。 建置您的工作流程，以自動同步Campaign和CRM。 您可以建立工作流程，該工作流程會透過Microsoft Dynamics匯入聯絡人、將其與現有的Adobe Campaign資料同步、刪除重複的聯絡人，然後更新Adobe Campaign資料庫。

↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started) 中深入瞭解

