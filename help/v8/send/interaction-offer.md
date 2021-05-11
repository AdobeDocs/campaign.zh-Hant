---
solution: Campaign
product: Adobe Campaign
title: 促銷活動互動選件
description: 瞭解如何建立優惠
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 3%

---

# 建立優惠方案

若要建立選件，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Campaigns]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Offers]**&#x200B;連結。

1. 按一下 **[!UICONTROL Create]** 按鈕。

1. 變更標籤並選取選件應屬於的類別。

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以建立選件。

   此選件可在平台中使用，其內容可加以設定。

## 資格設定

您現在可以使用&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤來定義：

* 優惠的資格期間。 [了解更多](#eligibility-period)
* 選件目標人口族群的篩選。 [了解更多](#filters-on-the-target)
* 選件重量。 [了解更多](#offer-weight)

### 優惠資格期間{#eligibility-period}

在選件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤中，定義選件的資格期間。 使用下拉式清單，在日曆中選取開始和結束日期。

![](assets/offer_eligibility_create_002.png)

在此期間之外，將不會選取選件。 如果您也設定了選件類別的資格日期，則會套用最嚴格的期間。

### 在目標{#filters-on-the-target}上新增篩選器

在選件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤中，將篩選器套用至選件目標。

若要這麼做，請按一下&#x200B;**[!UICONTROL Edit query]**&#x200B;連結，然後選取您要套用的篩選。

![](assets/offer_eligibility_create_003.png)

如果已建立預先定義的篩選，您可以從使用者篩選清單中選取這些篩選。 [了解更多](interaction-predefined-filters.md)。

![](assets/offer_eligibility_create_004.png)

### 設定選件重量{#offer-weight}

若要讓引擎在目標符合資格的數個選件之間做出決定，您必須為選件指派一或多個權重。 您也可以視需要將篩選套用至目標，或限制權重要套用的選件空間。 比較重量較輕的選件，更適合使用較重量的選件。

您可以為相同選件設定多個權重，例如，以區分支援期間、特定目標或甚至選件空間。

例如，對於年齡在18到25歲之間的接觸，選件可以具有A的重量，對於超過該範圍的接觸，選件可以具有B的重量。 如果選件在整個夏天都符合資格，則其7月份的重量可能為A,8月份的重量可能為B。

>[!NOTE]
>
>可根據選件所屬類別的參數暫時修改指派的權重。 [了解更多](interaction-offer-catalog.md#creating-offer-categories)。

若要在選件中建立權重，請套用下列步驟：

1. 在選件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Add]**。

   ![](assets/offer_weight_create_001.png)

1. 變更標籤並指派權重。 預設值為 1。

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >如果未輸入加權(0)，則目標將不會被視為符合選件資格。

1. 如果您希望權重適用於指定期間，請定義資格日期。

   ![](assets/offer_weight_create_002.png)

1. 如有必要，請將權重限制在特定選件空間。

   ![](assets/offer_weight_create_003.png)

1. 套用篩選至目標。

   ![](assets/offer_weight_create_004.png)

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以保存重量。

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >如果目標符合所選選件的多重權重，引擎會保留最佳（最高）權重。 在呼叫選件引擎時，每個連絡人最多會選取一次選件。

### 優惠資格規則摘要{#a-summary-of-offer-eligibility-rules}

設定完成後，資格規則的摘要將可在選件控制面板上取得。

若要檢視，請按一下&#x200B;**[!UICONTROL Schedule and eligibility rules]**&#x200B;連結。

![](assets/offer_eligibility_create_005.png)

## 建立選件內容{#creating-the-offer-content}

使用&#x200B;**[!UICONTROL Content]**&#x200B;標籤來定義選件內容。

![](assets/offer_content_create_001.png)

1. 定義選件內容的各種參數。

   * **[!UICONTROL Title]** :指定您想要在選件中顯示的標題。警告：這不是指選件的標籤，該標籤在&#x200B;**[!UICONTROL General]**&#x200B;標籤中定義。
   * **[!UICONTROL Destination URL]** :指定您選件的URL。它必須以&quot;http://&quot;或&quot;https://&quot;開頭。
   * **[!UICONTROL Image URL]** :指定選件影像的URL或存取路徑。
   * **[!UICONTROL HTML content]** /  **[!UICONTROL Text content]** :在您要的標籤中輸入選件的正文。若要產生追蹤，**[!UICONTROL HTML content]**&#x200B;必須由HTML元素組成，這些元素可封閉在`<div>`類型元素中。 例如，HTML頁面中`<table>`元素的結果如下：

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   瞭解如何在[本節](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted)中定義接受URL。

   ![](assets/offer_content_create_002.png)

   若要尋找在選件空間設定期間所定義的必填欄位，請按一下&#x200B;**[!UICONTROL Content definitions]**&#x200B;連結以顯示清單。 [了解更多](interaction-offer-spaces.md)。

   ![](assets/offer_content_create_003.png)

   在此範例中，選件必須包含標題、影像、HTML內容和目標URL。

## 預覽選件{#previewing-the-offer}

在設定選件內容後，您就可以預覽選件為其收件者所顯示的效果。

操作步驟：

1. 按一下&#x200B;**[!UICONTROL Preview]**&#x200B;頁籤。

   ![](assets/offer_preview_create_001.png)

1. 選取您要檢視之選件的表示法。

   ![](assets/offer_preview_create_002.png)

1. 如果您已個人化選件內容，請選取選件目標以檢視個人化。

   ![](assets/offer_preview_create_003.png)

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## 核准並啟用優惠方案{#approve-offers}

您現在可以核准並啟動選件，以便在&#x200B;**Live**&#x200B;環境中使用。

:arrow_upper_right:有關詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

## 管理優惠方案簡報

Campaign可讓您使用簡報規則來控制選件的流程。 這些規則是促銷活動互動專屬的類型學規則。 它們可讓您根據已向收件者提出之主張的歷史記錄，排除選件。 它們在環境中被引用。

:arrow_upper_right:有關詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=en#managing-offers)

## 選件模擬

模擬模組可讓您在將提案傳送給收件者之前，先測試屬於類別或環境的選件的分佈。

模擬會考慮先前套用至選件的上下文和資格規則及其呈現規則。 這可讓您測試和調整選件提案的各種版本，而不需實際使用選件或在請求／請求目標時，因為模擬對目標收件者沒有影響。

:arrow_upper_right:有關選件模擬的詳細資訊，請參閱[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.htm)
