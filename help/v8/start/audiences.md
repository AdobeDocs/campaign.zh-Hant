---
title: 在Campaign中配合對象
description: 在Campaign中配合對象
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 16%

---

# 在Campaign中配合對象{#gs-ac-audiences}

設定檔是儲存在Campaign資料庫中的聯絡人。

在Adobe Campaign中， **收件者** 是用於傳送內容（電子郵件、簡訊等）的預設設定檔。 儲存在資料庫中的收件者資料可讓您篩選將接收任何指定傳遞的目標，並在傳遞內容中新增個人化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

瞭解如何匯入、更新及管理設定檔和對象 [在本節中](../audiences/gs-audiences.md).

## 建立清單{#create-lists}

清單是一組靜態的聯絡人，可在傳遞動作中定位，或在匯入或其他工作流程動作中更新。 例如，透過查詢從資料庫中擷取的母體可儲存為清單。

瞭解如何在中建立和管理清單 [此頁面](../audiences/create-audiences.md).

## 篩選資料庫{#filter-the-database}

篩選設定可讓您從清單中選取資料 **[!UICONTROL dynamically]**：修改資料時，會更新篩選的資料。 您可以建立自己的篩選器，或使用內建篩選器來定義目標對象。

瞭解如何在中建立和管理篩選器 [此頁面](../audiences/create-filters.md).

## 在工作流程中建立對象

可以透過工作流程中圖形順序的查詢組合來建立目標定位。 您可以建立根據需求定位的對象。 若要顯示工作流程編輯器，請按一下 **[!UICONTROL Targeting and workflows]** 索引標籤進行編輯。

瞭解如何在的行銷活動工作流程中建立受眾 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant)


## 使用中的設定檔案 {#active-profiles}

作用中設定檔是客戶在過去12個月嘗試透過任何通道與之通訊的設定檔。 授權量度以作用中設定檔為基礎。 進一步瞭解 [Adobe Campaign產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

您可以直接從Campaign「控制面板」監視執行個體上的作用中設定檔數目。 有關詳細資訊，請參閱 [控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.

>[!CAUTION]
>
>* 數個傳送所定位的設定檔只會計算一次。
>
>* 在X (Twitter)的社交行銷內容中定位的設定檔不會計為作用中設定檔。

## 隱私權與同意{#privacy-and-consent}

Adobe Campaign是一款強大的工具，用於收集和處理包括個人資訊及敏感資料在內的大量資料。 Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

瞭解如何在中管理隱私權和同意 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant){target="_blank"}.

**相關主題**

* [設計和執行行銷活動專屬工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [瞭解如何選取行銷活動的對象](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant)

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant)
