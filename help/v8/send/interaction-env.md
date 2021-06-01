---
product: Adobe Campaign
title: 促銷活動互動運算子
description: 建立優惠方案管理運算子
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# 即時和設計環境{#live-design-environments}

互動會與兩種選件環境搭配運作：

* **[!UICONTROL Design]** 包含正在編輯且可以變更之選件的選件環境。這些優惠尚未通過審批週期，也未傳遞給聯繫人。
* **[!UICONTROL Live]** 將已核准的優惠方案呈現給聯絡人的優惠方案環境。此環境中的選件為唯讀。

![](assets/offer_environments_overview_001.png)

每個&#x200B;**[!UICONTROL Design]**&#x200B;環境都連結到&#x200B;**[!UICONTROL Live]**&#x200B;環境。 優惠方案完成後，其內容和資格規則會受到核准週期的約束。 完成此週期後，相關選件會自動部署至&#x200B;**[!UICONTROL Live]**&#x200B;環境。 從現在開始，它將可供交付。

依預設，Campaign會隨&#x200B;**[!UICONTROL Design]**&#x200B;環境和連結至的&#x200B;**[!UICONTROL Live]**&#x200B;環境一起提供。 這兩個環境都已預先設定為鎖定[內建收件者表格](../dev/datamodel.md#ootb-profiles)。

>[!NOTE]
>
>若要定位收件者表格，您需要使用目標對應助理來建立環境。 [瞭解更多](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

傳遞管理員只能檢視&#x200B;**[!UICONTROL Live]**&#x200B;環境，並運用選件來傳遞。 選件管理員可以檢視和使用&#x200B;**[!UICONTROL Design]**&#x200B;環境，以及檢視&#x200B;**[!UICONTROL Live]**&#x200B;環境。 [瞭解更多](interaction-operators.md)。

## 建立優惠方案環境{#creating-an-offer-environment}

依預設，Campaign隨附內建環境，以鎖定收件者表格（已識別的選件）。 若要鎖定另一個表格，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，以滑鼠右鍵按一下您要使用的目標對應，然後選取&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**。

   ![](assets/offer_env_anonymous_001.png)

1. 按一下&#x200B;**[!UICONTROL Next]**，選擇&#x200B;**[!UICONTROL Generate a storage schema for propositions]**&#x200B;選項，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果已核取選項，請取消勾選，然後重新勾選。

1. Adobe Campaign會建立兩個環境 — **[!UICONTROL Design]**&#x200B;和&#x200B;**[!UICONTROL Live]** — 搭配先前啟用之目標對應的目標資訊。 環境已預先設定目標資訊。
