---
title: 使用市場活動交互環境
description: 瞭解如何為市場活動交互建立環境
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# 使用環境{#work-with-environments}

## 即時和設計環境{#live-design-environments}

交互操作與兩種類型的服務環境一起操作：

* **[!UICONTROL Design]** 包括正在編輯且可以更改的優惠的優惠環境。 這些優惠尚未通過審批週期，也未交付給聯繫人。
* **[!UICONTROL Live]** 提供環境，其中包括向聯繫人提供的已批准的優惠。 此環境中的服務是只讀的。

![](assets/offer_environments_overview_001.png)

每個 **[!UICONTROL Design]** 環境與 **[!UICONTROL Live]** 環境。 當優惠完成時，其內容和資格規則將受到批准週期的約束。 完成此週期後，相關服務將自動部署到 **[!UICONTROL Live]** 環境。 從這一刻起，它將可供遞送。

預設情況下，活動附帶 **[!UICONTROL Design]** 環境 **[!UICONTROL Live]** 環境。 兩個環境都已預配置為針對 [內置收件人表](../dev/datamodel.md#ootb-profiles)。

>[!NOTE]
>
>要建立目標收件人表，您需要使用目標映射助理來建立環境。 [了解更多資訊](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

交貨經理只能查看 **[!UICONTROL Live]** 提供環境和利用服務。 服務經理可以查看和使用 **[!UICONTROL Design]** 環境，並查看 **[!UICONTROL Live]** 環境。 [了解更多](interaction-operators.md)

## 為匿名交互建立環境{#create-an-offer-environment}

預設情況下，市場活動附帶一個內置環境，以針對收件人表（已標識的優惠）。 要瞄準另一個表，例如訪問網站進行入站交互的匿名配置檔案，您需要更新配置。

請遵循以下步驟：

1. 瀏覽到 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，按一下右鍵要使用的目標映射並選擇 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**。

   ![](assets/offer_env_anonymous_001.png)

1. 按一下 **[!UICONTROL Next]**，選擇 **[!UICONTROL Generate a storage schema for propositions]** 選項 **[!UICONTROL Save]**。

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果選中了該選項，請取消選中它，然後重新選中它。

1. Adobe Campaign創造了兩個環境。 **[!UICONTROL Design]** 和 **[!UICONTROL Live]**  — 使用先前啟用的目標映射中的目標資訊。 環境預配置了目標資訊。

如果已激活 **[!UICONTROL Visitor]** 映射， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框中 **[!UICONTROL General]** 頁籤。

此選項允許您激活匿名交互特定的函式，特別是在配置環境提供空格時。 您還可以配置選項，使您能夠從「已識別」環境切換到「匿名」環境。

例如，您可以將收件人環境的服務空間（已標識的聯繫人）與與訪問者環境（未標識的聯繫人）匹配的服務空間連結起來。 這樣，根據是否識別了此聯繫人，將向聯繫人提供不同的優惠。 有關此內容的詳細資訊，請參閱 [建立聘用空間](interaction-offer-spaces.md)。

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>有關入站通道上匿名交互的詳細資訊，請參閱 [匿名交互](anonymous-interactions.md)。
