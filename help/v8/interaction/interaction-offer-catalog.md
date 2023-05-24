---
title: 行銷活動互動優惠方案目錄
description: 瞭解如何建立優惠方案目錄
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# 建立優惠方案目錄

作為 **優惠方案管理員**，即由您負責建立優惠方案目錄。

優惠方案目錄與單一預先存在的環境相關聯。 此目錄中的選件只能與此同一環境中指定的空間相關聯。

在建立優惠方案之前，您必須先指定 [環境](interaction-env.md) 包含一組優惠方案的所有特性（適用性、目標限制、呈現規則），並依類別以及其空間清單排序。

## 建立優惠類別{#creating-offer-categories}

選件會組織成類別/子類別。 類別建立於 **[!UICONTROL Design]** 環境，並自動部署於 **[!UICONTROL Live]** 環境（亦即可供使用）。 此 **[!UICONTROL Design]** 環境包含接收所有優惠方案的預設類別。 可以建立子類別以將階層新增至目錄選件。

對於每個類別，您都可以定義 **適用日期**，即可將類別中包含的優惠方案顯示給其目標的期間。 您也可以調整類別的權重，以優先處理優惠方案簡報。

若要建立新類別，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Offer catalog]** 資料夾。

   ![](assets/offer_cat_create_001.png)

1. 按一下右鍵並選取 **[!UICONTROL Create a new "Offer category" folder]** 下拉式清單中的。

   ![](assets/offer_cat_create_002.png)

1. 重新命名類別。 您稍後可以使用編輯標籤 **[!UICONTROL General]** 標籤。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重複這些步驟，視需要建立儘可能多的類別。

   此後，您可以視需要：

   * 從以下日期指派適用日期： **[!UICONTROL Eligibility]** 標籤。

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** 將篩選器套用至優惠方案目標。

   * 適用性規則的回顧。若要檢視適用性規則，請按一下 **[!UICONTROL Schedule and eligibility rules of the offer]** 連結。

## 新增遞補類別

為確保所有收件者都能收到優惠方案主張，您可以在建議中系統地新增一或多個優惠方案類別。

這些遞補優惠方案的權重必須較低（但非空值），因此只有在沒有較高權重優惠方案符合資格時，才會將其考慮在內。

此外，這些選件不得套用任何簡報規則，以確保建議中一律包含這些選件。 這表示在主張期間，如果沒有可用的較高權重優惠，收件者將至少收到此類別的一個優惠。

若要在建議中包含遞補類別，請遵循下列步驟：

1. 瀏覽至優惠方案目錄。
1. 按一下 **[!UICONTROL Eligibility]** 標籤並選取 **[!UICONTROL Always include this category in the recommendations]** 選項。
1. 按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)
