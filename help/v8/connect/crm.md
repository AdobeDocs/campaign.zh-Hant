---
solution: Campaign
product: Adobe Campaign
title: 使用Campaign和您的CRM
description: '瞭解如何使用Campaign和您的CRM '
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 21%

---

# 將您的CRM與Campaign {#gs-crm}連結

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的協力廠商系統。透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各協力廠商和企業應用程式輕鬆整合。

這些連接器可讓您快速輕鬆地整合資料：Adobe Campaign提供專屬的助理，負責從CRM的表格中收集和選擇。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

>[!NOTE]
>
>此功能可透過&#x200B;**CRM連接器**&#x200B;專用套件在Adobe Campaign提供。

## 相容系統{#compatible-crm-systems-and-limitations}

支援的CRM和版本詳見Campaign [相容性矩陣](../start/compatibility-matrix.md)。

**注意** - CRM連接器僅能搭配安全的URL(https)運作。

## 實施步驟 {#crm-implementation-steps}

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)中瞭解連接Campaign和Microsoft Dynamics的逐步程式

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)中瞭解連接Campaign和Salesforce的逐步程式


Adobe Campaign與CRM之間的資料同步是通過專用的工作流活動進行的。 建立您的工作流程，以自動化Campaign和CRM之間的同步化。 您可以建立工作流程，透過Microsoft Dynamics匯入連絡人、將連絡人與現有的Adobe Campaign資料同步、刪除重複的連絡人，然後更新Adobe Campaign資料庫。

:arrow_upper_right:進一步瞭解[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

