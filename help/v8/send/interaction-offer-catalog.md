---
solution: Campaign v8
product: Adobe Campaign
title: 促銷活動互動優惠方案目錄
description: 了解如何建立優惠方案目錄
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: 58f294b3d17de5eca64c82fdf7720b2734320bad
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# 建立優惠方案目錄

身為&#x200B;**優惠方案管理員**，您負責建立優惠方案目錄。

優惠方案目錄與單一預先存在的環境相關聯。 此目錄中的選件只能與在此相同環境中指定的空格相關聯。

建立優惠方案之前，您必須先指定[environment](interaction-env.md)，其中包含一組優惠方案的所有特性（適用性、目標限制、展示規則），並分類，以及其空格清單。

## 建立優惠方案類別{#creating-offer-categories}

優惠方案會組織為類別/子類別。 類別會在&#x200B;**[!UICONTROL Design]**&#x200B;環境中建立，並在核准包含的選件時自動部署在&#x200B;**[!UICONTROL Live]**&#x200B;環境中（即可供使用）。 **[!UICONTROL Design]**&#x200B;環境包含接收所有選件的預設類別。 可以建立子類別，將階層新增至目錄選件。

對於每個類別，您可以定義&#x200B;**適用性日期**，這是可向其目標顯示類別中包含選件的期間。 您也可以調整類別的權重，以排定優惠方案簡報的優先順序。

若要建立新類別，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Offer catalog]**&#x200B;資料夾。

   ![](assets/offer_cat_create_001.png)

1. 按一下右鍵，然後從下拉清單中選擇&#x200B;**[!UICONTROL Create a new "Offer category" folder]**。

   ![](assets/offer_cat_create_002.png)

1. 重新命名類別。 您稍後可以使用&#x200B;**[!UICONTROL General]**&#x200B;標籤來編輯標籤。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重複這些步驟，視需要建立任意數量的類別。

   之後，您可視需要：

   * 從&#x200B;**[!UICONTROL Eligibility]**&#x200B;索引標籤指派資格日期。

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** 將篩選器套用至選件目標。

   * 適用性規則的重述。若要查看這些規則，請按一下&#x200B;**[!UICONTROL Schedule and eligibility rules of the offer]**&#x200B;連結。

## 新增備援類別

為確保所有收件者都收到優惠方案主張，您可以在建議中系統地新增一或多個優惠方案類別。

這些備援優惠方案的權重必須較低（但非空值），因此只有在沒有較高權重優惠方案符合資格時，才會考慮這些優惠方案。

此外，這些選件不得套用簡報規則，以確保建議一律包含這些選件。 這表示在主張期間，如果沒有較高權重的優惠方案可供使用，收件者將至少接收來自此類別的優惠方案。

若要在建議中納入備援類別，請遵循下列步驟：

1. 瀏覽至優惠方案目錄。
1. 按一下&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤並選取&#x200B;**[!UICONTROL Always include this category in the recommendations]**&#x200B;選項。
1. 按一下 **[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)

