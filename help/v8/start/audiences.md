---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用受眾
description: 開始使用受眾
feature: 閱聽眾
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 24%

---

# 開始使用對象{#gs-ac-audiences}

## 使用設定檔{#gs-ac-profiles}

設定檔是儲存在Campaign資料庫中的聯絡人，包括客戶、訂閱者和潛在客戶。 要獲取用戶檔案，並建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。透過Adobe Campaign，您可以將行銷記錄、購買資訊、偏好、CRM資料和任何相關PI資料整合在整合檢視中，以進行分析並採取行動。 設定檔包含鎖定目標、確認和追蹤個人所需的所有資訊。

配置檔案是&#x200B;**nmsRecipient**&#x200B;表或外部表中的記錄，該表儲存所有配置檔案屬性，如名字、姓氏、電子郵件地址、Cookie ID、客戶ID、移動標識符或與特定通道相關的其他資訊。 連結至收件者表格的其他表格包含與設定檔相關的資料，例如傳送記錄表，其中包含所有傳送至收件者之傳送的記錄。 在[此小節](../dev/datamodel.md#ootb-profiles)中進一步了解內建設定檔和收件者表格。

在Adobe Campaign中，**收件者**&#x200B;是用於傳送傳遞（電子郵件、簡訊等）的預設設定檔。 資料庫中儲存的收件者資料可讓您篩選將接收任何指定傳送的目標，並在您的傳送內容中新增個人化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

設定檔可分組在清單中，或透過查詢資料庫來收集。


若要將設定檔資料填入Campaign，您可以：

* [從外部](import.md) 資料源（如CRM系統）匯入資料檔案
* [建立Web](../dev/webapps.md) 表單，讓客戶輸入自己的資訊並建立自己的設定檔
* [映射至外部資料](../connect/fda.md) 庫，其中儲存配置檔案
* 使用用戶端主控台手動輸入設定檔，如下所示：

![](assets/create-profile.png)


[!DNL :[!DNL :arrow_upper_right:]:]了解如何在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html)中管理設定檔。


## 隱私權與同意

Adobe Campaign是收集和處理大量資料（包括個人資訊和敏感資料）的強大工具。 Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

:[!DNL :arrow_upper_right:]:在[Adobe Campaign Classic v7檔案](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)中了解如何管理隱私權和同意。

## 建立清單

清單 (list) 是一組靜態的用戶檔案，在傳遞作業期間可用於提供目標，或在匯入作業或工作流程執行期間可對其進行更新。例如，透過查詢而從資料庫中摘取出的母體可形成一個清單。

:[!DNL :arrow_upper_right:]:了解如何在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html)中建立及管理清單。

## 查詢資料庫

在工作流程中使用&#x200B;**Query**&#x200B;活動來查詢您的資料庫、劃分資料並建立複雜的對象。

:[!DNL :arrow_upper_right:]:在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html)中深入了解Campaign查詢。

:[!DNL :arrow_upper_right:]:所有鎖定目標活動都列在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)中

## 在工作流程中建立對象

鎖定目標可透過工作流程中圖形順序的查詢組合來建立。 您可以建立將根據您的需求鎖定的對象。 若要顯示工作流程編輯器，請按一下促銷活動控制面板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;標籤。

:[!DNL :arrow_upper_right:]:在[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)中了解如何在行銷活動工作流程中建立受眾


## 使用中的設定檔案{#active-profiles}

根據您的合約，您的每個 Campaign 執行個體都已佈建特定數量的作用中設定檔，而且會計算這些設定檔數量以結算費用。請參閱您的最新合約，以參考已購買作用中設定檔數目。

**** 設定檔是指資訊記錄(例如：收件者表格中 [的記](../dev/datamodel.md) 錄，或外部表格，其中包含代表最終客戶、潛在客戶或潛在客戶的Cookie ID、客戶ID、行動識別碼或與特定管道相關的其他資訊。如果設定檔在過去12個月內透過任何通道被定位或通訊，則會視為作用中。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

:[!DNL :arrow_upper_right:]: For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**相關主題**

:[!DNL :arrow_upper_right:]:[設計並執行促銷活動專屬工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:[!DNL :arrow_upper_right:]:[了解如何選取行銷活動的對象](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:[!DNL :arrow_upper_right:]: [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
