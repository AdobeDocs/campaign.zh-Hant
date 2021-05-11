---
solution: Campaign
product: Adobe Campaign
title: 促銷活動互動選件目錄
description: 瞭解如何建立選件目錄
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: fcc0165aeba4347a53d33bed95aa7fbb5fa27005
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 2%

---

# 傳送選件

為了讓選件由選件引擎選取，選件已經核准，並可在&#x200B;**即時**&#x200B;環境中使用。 [了解更多](interaction-offer.md#approve-offers)

透過對外通訊頻道提供簡報，透過直效郵件、電子郵件或行動傳送進行。 您還可以將統一模式與事務性消息傳遞（消息中心）一起使用。

## 在傳送{#offer-into-a-delivery}中插入選件

要將優惠方案插入交付中，請執行以下步驟：

1. 在傳送視窗中，按一下&#x200B;**選件**&#x200B;圖示。

   ![](assets/offer_delivery_001.png)

1. 選取符合您選件環境的空間。

   ![](assets/offer_delivery_002.png)

1. 若要調整引擎選擇的選件，請選取要呈現的選件所屬類別，或選取一／多個主題。 我們建議一次只使用其中一個欄位，以避免超出限制。

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. 指定要插入傳送內文的選件數目。

   ![](assets/offer_delivery_005.png)

1. 如有必要，請選擇&#x200B;**[!UICONTROL Exclude non-eligible recipients]**&#x200B;選項。 [了解更多](#parameters-for-calling-offer-engine)。

   ![](assets/offer_delivery_006.png)

1. 如果需要，請選擇&#x200B;**[!UICONTROL Do not display anything if no offers are selected]**&#x200B;選項。 [了解更多](#parameters-for-calling-offer-engine)。

   ![](assets/offer_delivery_007.png)

1. 使用合併欄位將屬性插入傳送內容。 可用的主張數取決於引擎調用的配置方式，其順序取決於選件的優先順序。

   ![](assets/offer_delivery_008.png)

1. 完成內容、測試並傳送您的內容。

   ![](assets/offer_delivery_010.png)


### 選件引擎{#parameters-for-calling-offer-engine}的參數

* **[!UICONTROL Space]** :必須選取以啟用選件引擎的選件環境空間。
* **[!UICONTROL Category]** :選件排序的特定資料夾。如果未指定類別，除非選取主題，否則選件引擎會考量環境中包含的所有選件。
* **[!UICONTROL Themes]** :關鍵字。這些選件可當成篩選，讓您透過在一組類別中選取選件來調整要呈現的選件數量。
* **[!UICONTROL Number of propositions]** :引擎傳回的可插入傳送主體的選件數。如果未將選件插入訊息中，選件仍會產生，但不會顯示。
* **[!UICONTROL Exclude non-eligible recipients]** :此選項可讓您啟用或停用排除不符合資格選件的收件者。合格命題的數目可能低於所請求的命題數目。 如果勾選此方塊，則沒有足夠建議的收件者將會從傳送中排除。 如果您未選取此選項，這些收件者將不會被排除，但是他們將沒有要求數目的建議。
* **[!UICONTROL Do not display anything if no offer is selected]** :此選項可讓您選擇在其中一個陳述式不存在時如何處理訊息。選中此框後，不顯示缺少命題的表示，並且不會在此命題的消息中顯示任何內容。 如果未勾選此方塊，則訊息本身會在傳送期間取消，而收件者將不再收到任何訊息。

## 在工作流程中傳送選件

數個工作流程活動可讓您定義選件的呈現方式：

* 擴充
* 優惠方案引擎
* 依儲存格列出的優惠方案

### 擴充 {#enrichment}

**Enrichment**&#x200B;活動可讓您新增選件或連結至傳送收件者的選件。

:arrow_upper_right:有關Enrichment活動的詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/enrichment.html)

例如，您可以在傳送前豐富收件者查詢的資料。

![](assets/int_enrichment_offer1.png)

指定選件主張的方法有兩種。

* 指定選件或選件引擎呼叫。
* 參考選件的連結。

#### 指定選件或對選件引擎的呼叫{#specifying-an-offer-or-a-call-to-the-offer-engine}

配置&#x200B;**Query**&#x200B;活動後：

1. 添加並開啟&#x200B;**Enrichment**&#x200B;活動。
1. 在 **[!UICONTROL Enrichment]** 索引標籤中，選取 **[!UICONTROL Add data]**。
1. 在要添加的資料類型中選擇&#x200B;**[!UICONTROL An offer proposition]**。

   ![](assets/int_enrichment_offer2.png)

1. 指定要新增之提案的識別碼和標籤。
1. 指定選件選擇。 這有兩個可能的選項：

   * **[!UICONTROL Search for the best offer in a category]** :勾選此選項並指定選件引擎呼叫參數（選件空間、類別或主題、連絡日期、要保留的選件數）。引擎會根據這些參數自動計算要新增的選件。 我們建議您填寫&#x200B;**[!UICONTROL Category]**&#x200B;或&#x200B;**[!UICONTROL Theme]**&#x200B;欄位，而不是同時填妥兩者。

      ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A predefined offer]** :勾選此選項並指定選件空間、特定選件和連絡日期，以直接設定您要新增的選件，毋需呼叫選件引擎。

      ![](assets/int_enrichment_offer4.png)

1. 然後設定與您所選渠道對應的傳送活動。 [了解更多](#offer-into-a-delivery)。

   >[!NOTE]
   >
   >預覽可用的建議數取決於在濃縮活動中執行的配置，而不是直接在交付中執行的任何可能的配置。

#### 參考選件{#referencing-a-link-to-an-offer}的連結

您也可以參考&#x200B;**Enrichment**&#x200B;活動中選件的連結。

要執行此操作，請遵循下列步驟：

1. 在活動的&#x200B;**[!UICONTROL Enrichment]**&#x200B;標籤中選擇&#x200B;**[!UICONTROL Add data]**。
1. 在您選擇要添加的資料類型的窗口中，選擇&#x200B;**[!UICONTROL A link]**。
1. 選擇要建立的連結類型及其目標。 在此情況下，目標是選件結構。

   ![](assets/int_enrichment_link1.png)

1. 指定擴充活動（在此收件者表格）中的傳入表格資料與選件表格之間的連結。 例如，您可以將選件代碼連結至收件者。

   ![](assets/int_enrichment_link2.png)

1. 然後設定與您所選渠道對應的傳送活動。 [了解更多](#offer-into-a-delivery)。

   >[!NOTE]
   >
   >預覽可用的建議數取決於交付中執行的配置。

#### 儲存選件排名和權重{#storing-offer-rankings-and-weights}

依預設，當使用&#x200B;**Enrichment**&#x200B;活動來傳送選件時，其排名和權重不會儲存在命題表格中。

>[!NOTE]
>
>預設情況下，**[!UICONTROL Offer engine]**&#x200B;活動會儲存此資訊。

但是，您可以按如下方式儲存此資訊：

1. 在查詢之後和傳送活動之前放置的擴充活動中，建立對選件引擎的呼叫。 [了解更多](#specifying-an-offer-or-a-call-to-the-offer-engine)。
1. 在活動的主窗口中，選擇&#x200B;**[!UICONTROL Edit additional data...]**。

   ![](assets/ita_enrichment_rankweight_1.png)

1. 新增排名的&#x200B;**[!UICONTROL @rank]**&#x200B;欄，以及選件權重的&#x200B;**[!UICONTROL @weight]**&#x200B;欄。

   ![](assets/ita_enrichment_rankweight_2.png)

1. 確認您的新增功能並儲存您的工作流程。

傳送會自動儲存選件的排名和權重。 此資訊會顯示在傳送的&#x200B;**[!UICONTROL Offers]**&#x200B;標籤中。

### 優惠方案引擎 {#offer-engine}

**[!UICONTROL Offer engine]**&#x200B;活動也可讓您在傳送前指定對選件引擎的呼叫。

:arrow_upper_right:有關&#x200B;**選件引擎**&#x200B;活動的更多資訊，請參閱[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offer-engine.html)

此活動與引擎呼叫的&#x200B;**Enrichment**&#x200B;活動運作在相同的原則上，方法是在傳送前，使用引擎計算的選件來豐富傳入人口資料。

![](assets/int_offerengine_activity2.png)

配置&#x200B;**Query**&#x200B;活動後：

1. 新增並開啟&#x200B;**[!UICONTROL Offer engine]**&#x200B;活動。
1. 填寫各種可用欄位，以指定對選件引擎參數（選件空間、類別或主題、連絡日期、要保留的選件數）的呼叫。 引擎會根據這些參數自動計算要新增的選件。

   >[!CAUTION]
   >
   >如果您使用本活動，則只會儲存傳送中使用的選件主張。

   ![](assets/int_offerengine_activity1.png)

1. 然後設定與您所選渠道對應的傳送活動。 [了解更多](#inserting-an-offer-proposition-into-a-delivery)。

### 依儲存格列出的優惠方案 {#offers-by-cell}

**[!UICONTROL Offers by cell]**&#x200B;活動可讓您將傳入人口（例如從查詢）分發到數個區段，並指定要針對每個區段顯示的選件。

:arrow_upper_right:有關&#x200B;**Offer by cell**&#x200B;活動的詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offers-by-cell.html)

若要這麼做，請使用下列程式：

1. 指定目標人口後，新增&#x200B;**[!UICONTROL Offers by cell]**&#x200B;活動，然後開啟它。
1. 在&#x200B;**[!UICONTROL General]**&#x200B;標籤中，選取您要在其中呈現選件的選件空間。
1. 在&#x200B;**[!UICONTROL Cells]**&#x200B;標籤中，使用&#x200B;**[!UICONTROL Add]**&#x200B;按鈕指定不同的子集：

   * 使用可用的篩選和限制規則指定子集填入。
   * 然後選取您要呈現給子集的選件。 可用的選件是符合在上一步驟中選取之選件環境的選件。

      ![](assets/int_offer_per_cell1.png)

1. 然後設定與您所選渠道對應的傳送活動。

<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
