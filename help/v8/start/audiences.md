---
title: 在Campaign中配合對象
description: 在Campaign中配合對象
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
version: Campaign v8, Campaign Classic v7
source-git-commit: b24e05f152bc299ea7953856bfa71950b5cc9837
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 11%

---


# 在Campaign中配合對象{#gs-ac-audiences}

設定檔代表儲存在Adobe Campaign資料庫中的聯絡人。 依預設，**收件者**&#x200B;是傳送電子郵件、簡訊或直接郵件等傳遞時使用的主要設定檔。 儲存在資料庫中的收件者資料可讓您定義和篩選目標對象，以及個人化傳送內容。 除了收件者之外，還有其他用於特定目的的設定檔型別。 例如，種子設定檔可讓您在傳送給實際對象之前測試傳送。

在本節[中瞭解如何匯入、更新及管理設定檔與對象](../audiences/gs-audiences.md)。

## 建立清單{#create-lists}

清單是一組靜態的聯絡人，可在傳遞動作中定位，或在匯入或其他工作流程動作中更新。 例如，透過查詢從資料庫中擷取的母體可儲存為清單。

瞭解如何在[此頁面](../audiences/create-audiences.md)中建立和管理清單。

## 篩選資料庫{#filter-the-database}

篩選設定可讓您從清單&#x200B;**[!UICONTROL dynamically]**&#x200B;中選取資料：修改資料時，會更新篩選的資料。 您可以建立自己的篩選器，或使用內建篩選器來定義目標對象。

瞭解如何在[此頁面](../audiences/create-filters.md)中建立和管理篩選器。

## 在工作流程中建立對象

可以透過工作流程中圖形順序的查詢組合來建立目標定位。 您可以建立根據需求定位的對象。 若要顯示工作流程編輯器，請按一下行銷活動控制面板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;標籤。

在[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant){target="_blank"}中瞭解如何在行銷活動工作流程中建立對象。


## 活躍輪廓 {#active-profiles}

作用中設定檔是客戶在過去12個月嘗試透過任何通道與之通訊的設定檔。

根據您的合約，您的每個 Campaign 執行個體都已佈建特定數量的活躍輪廓，而且會計算這些輪廓數量以結算費用。請參閱您的最新合約，以參考已購買作用中設定檔數目。 深入瞭解[Adobe Campaign產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}。

您可以直接從Campaign「控制面板」監視執行個體上的作用中設定檔數目。 如需詳細資訊，請參閱[控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}。


以下護欄和限制在此適用：

* 數個傳送所定位的設定檔只會計算一次。
* 在X (Twitter)上的社交行銷內容中鎖定的設定檔不會計為作用中設定檔。
* 計數是以收件者主索引鍵為基礎。 因此，如果設定檔存在於兩個不同的收件者表格中，則可將其計算為作用中設定檔兩次。

## 隱私權與同意{#privacy-and-consent}

Adobe Campaign是一款強大的工具，用於收集和處理包括個人資訊及敏感資料在內的大量資料。 Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant){target="_blank"}中瞭解如何管理隱私權和同意。

