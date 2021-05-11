---
solution: Campaign
product: Adobe Campaign
title: 開始接觸受眾
description: 開始接觸受眾
feature: 受眾
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 878badaa696e11771388d3a37658f75cca756543
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 29%

---

# 開始使用觀眾{#gs-ac-audiences}

配置檔案可以分組到清單中，或通過查詢資料庫來收集。

## 使用配置式{#gs-ac-profiles}

設定檔集中在雲端資料庫中。 要獲取用戶檔案，並建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。有了Adobe Campaign，您可以將行銷記錄、購買資訊、偏好設定、CRM資料和任何相關PI資料整合在整合的檢視中，以進行分析並採取行動。

&quot;**描述檔**&quot;系指代表客戶、潛在客戶、電子報訂閱者等的資訊記錄。
**nmsRecipient**&#x200B;表或外部表中的記錄包含Cookie ID、客戶ID、移動標識符或與特定通道相關的其他資訊。 進一步瞭解[本節](../dev/datamodel.md#ootb-profiles)中的內建描述檔和收件者表格。

在 Adobe　Campaign 中，收件者是用於傳送內容 (電子郵件、SMS 等) 的預設用戶檔案。儲存在資料庫中的收件者資料可讓您篩選將接收任何指定傳送的目標，並在傳送內容中新增個人化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

:arrow_forward:[瞭解視訊中的描述檔](https://video.tv.adobe.com/v/35611?quality=12)

:arrow_upper_right:瞭解如何在[本指南](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html{:target=&quot;_blank&quot;})中管理配置式。

## 隱私權與同意

Adobe Campaign 是一款強大的工具，用於收集和處理包括個人資訊及敏感資料在內的超大資料。Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

:arrow_upper_right:在[本指南](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)中瞭解如何管理隱私權和同意。


## 建立清單

清單 (list) 是一組靜態的用戶檔案，在傳遞作業期間可用於提供目標，或在匯入作業或工作流程執行期間可對其進行更新。例如，透過查詢而從資料庫中摘取出的母體可形成一個清單。

:arrow_upper_right:瞭解如何在[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html)中建立和管理清單。

## 查詢資料庫

在工作流程中使用&#x200B;**Query**&#x200B;活動來查詢您的資料庫、區隔資料並建立複雜的觀眾。

:arrow_upper_right:進一步瞭解[本指南](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html)中的促銷活動查詢。

:arrow_upper_right:所有定位活動列在[此頁面](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)中

## 在工作流程中建立觀眾

定位可透過工作流程中圖形順序的查詢組合來建立。 您可以建立受眾，並根據您的需求進行定位。 若要顯示工作流程編輯器，請按一下促銷活動控制面板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;標籤。

:arrow_upper_right:瞭解如何在[本頁]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow的促銷活動工作流程中建立對象)


## 使用中的設定檔案{#active-profiles}

根據您的合約，您的每個 Campaign 執行個體都已佈建特定數量的作用中設定檔，而且會計算這些設定檔數量以結算費用。請參閱您的最新合約，以參考已購買作用中設定檔數目。

「設定檔」系指資訊記錄(例如：[收件者表格](../dev/datamodel.md)中的記錄，或包含Cookie ID、客戶ID、行動識別碼或與特定頻道相關的其他資訊的外部表格，代表最終客戶、潛在客戶或潛在客戶。 如果設定檔在過去12個月內透過任何通道被鎖定或傳達，則會視為作用中。

您可以直接從「促銷活動控制面板」監視執行個體上使用的作用中描述檔數目。

:arrow_upper_right:有關詳細資訊，請參閱[控制面板文檔](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。


**相關主題**

:arrow_upper_right:[設計並執行促銷活動特定的工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_upper_right:[瞭解如何選取促銷活動的對象](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:arrow_upper_right:[開始使用工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
