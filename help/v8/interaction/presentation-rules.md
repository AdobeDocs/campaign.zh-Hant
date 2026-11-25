---
product: campaign
title: 簡報規則
description: 簡報規則
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---
# 簡報規則{#presentation-rules}



## 建立簡報規則 {#creating-a-presentation-rule}

在我們的資料庫中，有數種歐洲、非洲、美國和加拿大的旅行優惠方案。 我們想要傳送前往加拿大之旅的優惠方案，但如果收件者拒絕此類優惠方案，我們便不想再次傳送給他們。

我們將設定規則，每個收件者僅會提供一次加拿大行程，如果遭拒絕，則不會再次提供。

1. 在Adobe Campaign樹狀結構中，前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]**&#x200B;節點。
1. 建立新的&#x200B;**[!UICONTROL Offer presentation]**&#x200B;型別規則。

   ![已開啟規則型別清單且已選取優惠方案簡報的型別規則建立表單](assets/offer_typology_example_001.png)

1. 視需要變更其標籤和說明。

   ![型別規則「一般」標籤，其中包含標籤、優惠方案簡報型別、電子郵件頻道和已輸入的說明](assets/offer_typology_example_002.png)

1. 選擇&#x200B;**[!UICONTROL All channels]**&#x200B;選項，將規則擴充至所有管道。

   ![已選取「所有管道」之型別規則的管道清單](assets/offer_typology_example_003.png)

1. 按一下&#x200B;**[!UICONTROL Edit expression]**&#x200B;連結，並選擇&#x200B;**[!UICONTROL Category]**&#x200B;節點作為運算式。

   ![使用Select的查詢視窗，開啟運算式對話方塊以選擇類別欄位](assets/offer_typology_example_004.png)

1. 選擇符合您加拿大旅行優惠方案的類別，然後按一下&#x200B;**[!UICONTROL OK]**&#x200B;以關閉查詢視窗。

   ![在等於加拿大的類別上查詢，並在旅行優惠方案類別樹狀結構中選取加拿大資料夾](assets/offer_typology_example_005.png)

1. 在&#x200B;**[!UICONTROL Offer presentation]**&#x200B;索引標籤中，選擇與環境中設定的維度相同的維度。

   ![顯示目標維度和儲存維度且符合環境的優惠方案簡報標籤](assets/offer_typology_example_006.png)

1. 指定套用規則的期間。

   ![具有Sliding period， Period consistent欄位設定為10d](assets/offer_typology_example_007.png)的優惠方案簡報標籤

1. 將主張限製為一個，以便已拒絕加拿大之旅的收件者不會收到另一個類似優惠。

   ![主張數量上限欄位設為1](assets/offer_typology_example_008.png)的優惠方案簡報標籤

1. 選取&#x200B;**[!UICONTROL Offers for the same category]**&#x200B;篩選器，以從&#x200B;**加拿大**&#x200B;類別中排除所有優惠方案。

   建議中的![優惠方案下拉式清單，與選取之相同類別的優惠方案一起計算](assets/offer_typology_example_020.png)

1. 選取&#x200B;**[!UICONTROL Rejected propositions]**&#x200B;篩選器，僅考慮收件者拒絕的主張。

   建議中的![主張狀態下拉式清單，以選取已拒絕的建議來計數](assets/offer_typology_example_021.png)

1. 選擇要套用此規則的收件者。

   在我們的範例中，我們將選擇&#x200B;**頻繁旅行者**&#x200B;位收件者。

   ![編輯篩選查詢精靈，選取經常旅行者收件者資料夾作為規則目標](assets/offer_typology_example_009.png)

1. 參考優惠方案型別中的規則。

   ![規則的型別標籤，其中的「新增型別」對話方塊列出選取的優惠型別](assets/offer_typology_example_013.png)

1. 前往優惠方案環境（**環境 — 此案例中的收件者**），並參考使用&#x200B;**[!UICONTROL Eligibility]**&#x200B;索引標籤中的下拉式清單剛建立的新型別。

   ![優惠方案環境的適用性標籤，優惠方案呈現方式型別清單顯示優惠方案](assets/offer_typology_example_014.png)

## 套用簡報規則 {#applying-the-presentation-rule}

以下是先前建立之型別規則的應用程式範例。

我們想要傳送屬於加拿大類別的第一個優惠方案主張。 如果任何收件者拒絕過一次優惠，將無法再次向他們提供。

1. 在&#x200B;**常旅客名單**&#x200B;收件者資料夾中，選擇其中一個設定檔以檢查其符合資格的優惠方案：按一下「**[!UICONTROL Propositions]**」標籤，然後按「**[!UICONTROL Preview]**」標籤。

   在我們的範例中，**Tim Ramsey**&#x200B;符合優惠方案資格，該優惠方案屬於&#x200B;**Americas**&#x200B;類別。

   ![收件者主張標籤，預覽子標籤，列出適用於美洲類別的合格優惠方案](assets/offer_typology_example_015.png)

1. 首先，建立電子郵件傳遞，以您的&#x200B;**經常旅行者**&#x200B;位收件者為目標，並提供優惠。
1. 選取優惠方案引擎呼叫引數。

   在我們的範例中，已選取&#x200B;**Travel in America**&#x200B;類別，其中包含&#x200B;**Canada**&#x200B;和&#x200B;**United States**&#x200B;子類別。

   ![電子郵件傳遞的選件管理對話方塊，具有美洲類別和每則訊息2個主張](assets/offer_typology_example_016.png)

1. 在訊息內文中插入您的優惠方案並傳送傳遞。 如需詳細資訊，請參閱[關於傳出頻道](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} （Campaign v8檔案）。

   收件者已收到其符合資格的優惠。

1. 收件者已拒絕加拿大優惠，如主張歷程記錄所示。

   ![加拿大Snowmobile優惠方案的收件者主張歷程記錄處於已拒絕狀態](assets/offer_typology_example_018.png)

1. 檢查他們現在符合資格的優惠方案。

   我們發現沒有選擇加拿大的優惠方案。

   ![收件者預覽索引標籤顯示紐約和大峽谷的合格優惠，不含加拿大優惠](assets/offer_typology_example_019.png)
