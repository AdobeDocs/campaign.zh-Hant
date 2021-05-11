---
solution: Campaign
product: Adobe Campaign
title: 促銷活動互動選件目錄
description: 瞭解如何建立選件目錄
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---

# 建立選件目錄

身為&#x200B;**選件管理員**，您負責建立選件目錄。

選件目錄會關聯至單一預先存在的環境。 此目錄中的選件只能與在此相同環境中指定的空間相關聯。

在建立選件之前，您必須先指定[environment](interaction-env.md)，其中包含一組選件的所有特性（資格、目標限制、呈現規則），並依類別分類，以及其空格清單。

## 建立優惠方案類別{#creating-offer-categories}

選件可分為類別／子類別。 類別是在&#x200B;**[!UICONTROL Design]**&#x200B;環境中建立，並在核准包含的選件時自動部署在&#x200B;**[!UICONTROL Live]**&#x200B;環境中（即可使用）。 **[!UICONTROL Design]**&#x200B;環境包含接收所有選件的預設類別。 可建立子類別，以新增階層至目錄選件。

對於每個類別，您可以定義&#x200B;**資格日期**，此期間是類別中包含的選件可呈現給其目標的期間。 您也可以調整類別的權重，以排定優惠簡報的優先順序。

若要建立新類別，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Offer catalog]**&#x200B;資料夾。

   ![](assets/offer_cat_create_001.png)

1. 按一下右鍵並從下拉清單中選擇&#x200B;**[!UICONTROL Create a new "Offer category" folder]**。

   ![](assets/offer_cat_create_002.png)

1. 重新命名類別。 您稍後可以使用&#x200B;**[!UICONTROL General]**&#x200B;標籤編輯標籤。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重複這些步驟，以視需要建立多個類別。

   之後，您可以視需要：

   * 從&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤指派資格日期。

      ![](assets/offer_cat_create_004.png)

   * 使用&#x200B;**[!UICONTROL Themes]**&#x200B;欄位，輸入可用於從此類別中選擇選件的關鍵字。

      ![](assets/offer_cat_create_005.png)

      >[!NOTE]
      >
      >呼叫選件引擎時，只會選取主題或類別符合參數的目錄部分。

   * 透過&#x200B;**[!UICONTROL Multiplier weight]**&#x200B;欄位，暫時「提升」特定期間類別的選件權重。

      ![](assets/offer_cat_create_006.png)

在類別所包含的選件儀表板中，可以重新檢視資格規則。 若要檢視，請按一下&#x200B;**[!UICONTROL Schedule and eligibility rules of the offer]**&#x200B;連結。

## 新增備援類別

為確保所有收件者都能收到選件提案，您可以在建議中系統地新增一或多個選件類別。

這些備援選件的重量必須較低（但非空值），因此只有在沒有較高重量的選件符合資格時，才會考慮這些選件。

此外，這些選件必須不套用簡報規則，以確保這些選件一律包含在建議中。 這表示，在提案期間，如果沒有較高權重的選件可供使用，收件者將至少收到此類別的選件。

若要在建議中包含備援類別，請遵循下列步驟：

1. 瀏覽至您的選件目錄。
1. 按一下&#x200B;**[!UICONTROL Eligibility]**&#x200B;頁籤並選擇&#x200B;**[!UICONTROL Always include this category in the recommendations]**&#x200B;選項。
1. 按一下 **[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)

