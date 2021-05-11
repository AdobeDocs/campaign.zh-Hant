---
solution: Campaign
product: Adobe Campaign
title: 促銷活動互動運算子
description: 建立選件管理運算子
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# 即時與設計環境{#live-design-environments}

互動可與兩種選件環境運作：

* **[!UICONTROL Design]** 包含正在編輯且可加以變更之選件的選件環境。這些優惠尚未經過核准週期，也未傳送給聯絡人。
* **[!UICONTROL Live]** 選件環境，當已核准的選件顯示給聯絡人時，這些選件環境便會包含在內。此環境中的選件為唯讀。

![](assets/offer_environments_overview_001.png)

每個&#x200B;**[!UICONTROL Design]**&#x200B;環境都與&#x200B;**[!UICONTROL Live]**&#x200B;環境連結。 當選件完成時，其內容和資格規則會受到核准週期的約束。 完成此循環後，相關選件會自動部署至&#x200B;**[!UICONTROL Live]**&#x200B;環境。 從現在開始，它將可供交付。

依預設，促銷活動會隨附&#x200B;**[!UICONTROL Design]**&#x200B;環境和&#x200B;**[!UICONTROL Live]**&#x200B;連結環境。 這兩個環境都已預先配置為針對[內置收件人表](../dev/datamodel.md#ootb-profiles)。

>[!NOTE]
>
>若要定位收件者表格，您必須使用目標對應助理來建立環境。 [了解更多](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

交付經理只能查看&#x200B;**[!UICONTROL Live]**&#x200B;環境，並利用優惠進行交付。 選件管理員可以檢視和使用&#x200B;**[!UICONTROL Design]**&#x200B;環境，並檢視&#x200B;**[!UICONTROL Live]**&#x200B;環境。 [了解更多](interaction-operators.md)。

## 建立選件環境{#creating-an-offer-environment}

依預設，Campaign會隨附內建環境，以定位收件者表格（已識別的選件）。 要定位另一個表，請執行以下步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Delivery mappings]**，以滑鼠右鍵按一下您要使用的傳送對應，然後選取&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**。

   ![](assets/offer_env_anonymous_001.png)

1. 按一下&#x200B;**[!UICONTROL Next]** ，選擇&#x200B;**[!UICONTROL Generate a storage schema for propositions]**&#x200B;選項，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果選項已勾選，請取消勾選，然後重新勾選。

1. Adobe Campaign建立了兩個環境- **[!UICONTROL Design]**&#x200B;和&#x200B;**[!UICONTROL Live]** —— 以及來自先前啟用的目標映射的目標資訊。 環境已預先配置了定位資訊。
