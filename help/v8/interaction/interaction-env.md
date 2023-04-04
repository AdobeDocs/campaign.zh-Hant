---
title: 使用Campaign互動環境
description: 了解如何建立Campaign互動環境
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# 使用環境{#work-with-environments}

## 即時和設計環境{#live-design-environments}

互動會與兩種選件環境搭配運作：

* **[!UICONTROL Design]** 包含正在編輯且可以變更之選件的選件環境。 這些優惠尚未通過審批週期，也未傳遞給聯繫人。
* **[!UICONTROL Live]** 將已核准的優惠方案呈現給聯絡人的優惠方案環境。 此環境中的選件為唯讀。

![](assets/offer_environments_overview_001.png)

每個 **[!UICONTROL Design]** 環境連結至 **[!UICONTROL Live]** 環境。 優惠方案完成後，其內容和資格規則會受到核准週期的約束。 完成此週期後，相關選件會自動部署至 **[!UICONTROL Live]** 環境。 從現在開始，它將可供交付。

依預設，Campaign會隨附 **[!UICONTROL Design]** 環境與 **[!UICONTROL Live]** 環境。 兩個環境皆已預先設定，以鎖定 [內置收件者表](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>若要定位收件者表格，您需要使用目標對應助理來建立環境。 [了解更多資訊](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

傳送管理員只能檢視 **[!UICONTROL Live]** 環境，並運用優惠方案來提供。 優惠方案管理員可檢視並使用 **[!UICONTROL Design]** 環境，並檢視 **[!UICONTROL Live]** 環境。 [了解更多](interaction-operators.md)

## 為匿名互動建立環境{#create-an-offer-environment}

依預設，Campaign隨附內建環境，以鎖定收件者表格（已識別的選件）。 若要鎖定另一個表格，例如針對傳入互動造訪您網站的匿名設定檔，您需要更新您的設定。

請遵循以下步驟：

1. 瀏覽至 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，請以滑鼠右鍵按一下您要使用的目標對應，然後選取 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. 按一下 **[!UICONTROL Next]**，請選取 **[!UICONTROL Generate a storage schema for propositions]** 選項，然後按一下 **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果已核取選項，請取消勾選，然後重新勾選。

1. Adobe Campaign建立兩個環境： **[!UICONTROL Design]** 和 **[!UICONTROL Live]**  — 包含先前啟用之目標對應的目標資訊。 環境已預先設定目標資訊。

如果已激活 **[!UICONTROL Visitor]** 映射， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框中的 **[!UICONTROL General]** 標籤。

此選項可讓您啟用匿名互動的特定功能，尤其是在設定環境提供空間時。 您也可以配置選項，讓您從「已識別」環境切換至「匿名」環境。

例如，您可以將收件者環境選件空間（已識別的連絡人）與符合訪客環境（未識別的連絡人）的選件空間連結。 如此一來，根據是否識別此連絡人，聯絡人將可使用不同的優惠方案。 有關詳細資訊，請參閱 [建立優惠方案空間](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>如需傳入頻道上匿名互動的詳細資訊，請參閱 [匿名互動](anonymous-interactions.md).
