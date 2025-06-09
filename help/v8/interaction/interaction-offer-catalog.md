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

# 建立產品建議目錄

作為&#x200B;**優惠方案管理員**，您負責建立優惠方案目錄。

優惠方案目錄與單一預先存在的環境相關聯。 此目錄中的選件只能與此相同環境中指定的空間相關聯。

建立優惠方案之前，您必須先指定一個[環境](interaction-env.md)，其中包含一組優惠方案的所有特性（適用性、目標限制、簡報規則），並依類別排序，以及其空格清單。

## 建立產品建議類別{#creating-offer-categories}

選件會整理成類別/子類別。 類別是在&#x200B;**[!UICONTROL Design]**&#x200B;環境中建立，並在其包含的優惠方案獲得核準時自動部署在&#x200B;**[!UICONTROL Live]**&#x200B;環境中（亦即可供使用）。 **[!UICONTROL Design]**&#x200B;環境包含接收所有優惠方案的預設類別。 可以建立子類別以將階層新增至目錄優惠方案。

對於每個類別，您可以定義&#x200B;**適用日期**，這是類別中包含的優惠方案可以呈現給其目標的期間。 您也可以調整類別的權重，以排定優惠方案簡報的優先順序。

若要建立新類別，請遵循下列步驟：

1. 瀏覽器至&#x200B;**[!UICONTROL Offer catalog]**&#x200B;資料夾。

   ![](assets/offer_cat_create_001.png)

1. 按一下滑鼠右鍵並從下拉式清單中選取&#x200B;**[!UICONTROL Create a new "Offer category" folder]**。

   ![](assets/offer_cat_create_002.png)

1. 重新命名類別。 您稍後可以使用&#x200B;**[!UICONTROL General]**&#x200B;索引標籤來編輯標籤。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重複這些步驟，視需要建立儘可能多的類別。

   此後，您可以視需要：

   * 從&#x200B;**[!UICONTROL Eligibility]**&#x200B;索引標籤指派適用日期。

     ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]**&#x200B;將篩選器套用至優惠目標。

   * 資格規則的回顧。若要檢視，請按一下&#x200B;**[!UICONTROL Schedule and eligibility rules of the offer]**&#x200B;連結。

## 新增遞補類別

為了確保所有收件者都會收到優惠方案主張，您可以在建議中系統地新增一或多個優惠方案類別。

這些遞補優惠方案的權重必須較低（但非空值），因此只有在沒有較高權重優惠方案符合資格時，才會將其列入考量。

此外，這些選件不得套用簡報規則，以確保建議中一律包含這些選件。 這表示，在主張期間，如果沒有更高的權重優惠可用，收件者將至少收到此類別的一個優惠。

若要在建議中包含遞補類別，請遵循下列步驟：

1. 瀏覽至優惠方案目錄。
1. 按一下「**[!UICONTROL Eligibility]**」索引標籤並選取&#x200B;**[!UICONTROL Always include this category in the recommendations]**&#x200B;選項。
1. 按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)
