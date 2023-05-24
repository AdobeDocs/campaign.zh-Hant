---
title: 在Campaign中使用對象
description: 在Campaign中使用對象
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 22%

---

# 在Campaign中使用對象{#gs-ac-audiences}

設定檔是儲存在Campaign資料庫中的連絡人。

在Adobe Campaign中， **收件者** 是用於傳送傳遞（電子郵件、簡訊等）的預設設定檔。 資料庫中儲存的收件者資料可讓您篩選將接收任何指定傳遞的目標，並在傳遞內容中新增個人化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

瞭解如何匯入、更新及管理設定檔和對象 [在本節中](../audiences/gs-audiences.md).

## 建立清單{#create-lists}

清單是一組靜態的聯絡人，可在傳遞動作中定位，或在匯入或其他工作流程動作中更新。 例如，透過查詢從資料庫中擷取的母體可以儲存為清單。

![](../assets/do-not-localize/glass.png) 瞭解如何在中建立和管理清單 [此頁面](../audiences/create-audiences.md).

## 篩選資料庫{#filter-the-database}

篩選設定可讓您從清單中選取資料 **[!UICONTROL dynamically]**：修改資料時，會更新篩選的資料。 您可以建立自己的篩選器，或使用內建篩選器來定義目標對象。

![](../assets/do-not-localize/glass.png) 瞭解如何在中建立和管理篩選器 [此頁面](../audiences/create-filters.md).

## 在工作流程中建立對象

目標定位可透過工作流程中圖形順序的查詢組合來建立。 您可以建立受眾，並根據您的需求鎖定這些受眾。 若要顯示工作流程編輯器，請按一下 **[!UICONTROL Targeting and workflows]** 索引標籤進行標籤。

瞭解如何在的行銷活動工作流程中建立對象 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant)


## 使用中的設定檔案{#active-profiles}

根據您的合約，您的每個Campaign執行個體都會布建特定數量的作用中設定檔，且會計算這些設定檔數量以結算費用。 請參閱您的最新合約，以參考已購買作用中設定檔數目。

**設定檔** 表示資訊記錄(例如： [收件者表格](../dev/datamodel.md) 或包含Cookie ID、客戶ID、行動識別碼或與特定管道相關的其他資訊的外部表格)，代表最終客戶、潛在客戶或潛在客戶。 如果設定檔在過去12個月內透過任何管道被定位或通訊，則會視為作用中。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## 隱私權與同意{#privacy-and-consent}

Adobe Campaign是一款強大的工具，用於收集和處理包括個人資訊及敏感資料在內的大量資料。 Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

![](../assets/do-not-localize/book.png) 瞭解如何在中管理隱私權與同意 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant){target="_blank"}.

**相關主題**

* [設計和執行行銷活動專屬的工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [瞭解如何選取行銷活動的對象](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant)

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant)
