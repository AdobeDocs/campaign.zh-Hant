---
product: campaign
title: 核准和啟用優惠方案
description: 核准和啟用優惠方案
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: managing-an-offer-catalog
exl-id: cf7649fe-f62a-4dfa-a19e-9c1ca545e3e3
TQID: 'https://experienceleague.adobe.com/f0zYxpc5-71Ci-4Q485v4rRdD1xHs6tKLkl7vrITMP0'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%
---
# 核准和啟用優惠方案{#approving-and-activating-an-offer}



選件內容完成後，您需要核准它以複製到即時環境中並傳送。 核准與優惠方案內容及其資格有關。

優惠方案控制面板上的橫幅會告訴您優惠方案是否需要通過核准週期。

![優惠儀表板橫幅指出優惠正在等待核准，並附上核准按鈕。](assets/offer_validate_001.png)

## 核准優惠內容 {#approving-offer-content}

核准優惠方案內容表示選取您要在即時環境中提供的表現。

優惠內容的每個空間各有一個表示法。 由於每個優惠方案空間都有其自己的結構和演算功能，因此優惠方案表示可能會有所不同。

您可以選擇在某些可用空間上核准優惠方案內容，而在其他空間上拒絕優惠方案內容。

>[!IMPORTANT]
>
>一旦優惠方案的內容和資格獲得核准，發佈工作流程（優惠方案通知）就會自動執行，優惠方案就會上線並在所有已啟用的空間中使用。

若要核准優惠方案內容，請套用下列步驟：

1. 按一下&#x200B;**[!UICONTROL Approval]**&#x200B;按鈕，然後在快顯視窗中選取&#x200B;**[!UICONTROL Approve content]**。

   ![已選取[核准]內容的[核准]功能表，在選件對話方塊中開啟[動作]。](assets/offer_validate_002.png)

1. 使用下拉式清單，選取您要繼續編輯的表示或您要發佈至即時環境的表示，然後按一下&#x200B;**[!UICONTROL Content approval]**。

   ![優惠方案對話方塊上的動作：選擇[繼續編輯]或[啟用]、新增註解、按一下[內容核准]。](assets/offer_validate_003.png)

   一旦核准優惠方案內容，就會更新優惠方案控制面板表格上的資訊。

   ![核准後的優惠儀表板：代表顯示已啟用，而核准區段顯示已核准的內容。](assets/offer_validate_004.png)

   >[!NOTE]
   >
   >**[!UICONTROL Content approved]**&#x200B;提及並不表示所有優惠宣告皆已啟用且已核准。 這表示內容核准流程已完成，無論所有優惠方案是否已啟用/核准。

## 核准優惠資格 {#approving-offer-eligibility}

核准優惠方案資格表示接受或拒絕優惠方案權重，且適用性規則也在優惠方案中設定，或繼承自父類別中建立的規則。

>[!IMPORTANT]
>
>一旦優惠方案的內容和資格獲得核准，發佈工作流程（優惠方案通知）就會自動執行，優惠方案就會上線並在所有已啟用的空間中使用。

* 按一下&#x200B;**[!UICONTROL Schedule and eligibility rules]**&#x200B;即可檢視規則的完整清單。

  ![從核准對話方塊開啟具有權重和日期範圍的排程和適用性規則清單。](assets/offer_validate_005.png)

* 若要變更適用性規則，請按一下&#x200B;**[!UICONTROL Reject]**，然後按一下&#x200B;**[!UICONTROL Eligibility approval]**。

  ![資格核准對話方塊，其中已選取[拒絕]、註解及[資格核准]按鈕。](assets/offer_validate_007.png)

  優惠方案控制面板上的各種狀態都會更新。

  ![拒絕後的儀表板：資格核准被拒絕橫幅、提交資格按鈕、資格被拒絕。](assets/offer_validate_006.png)

* 若要接受優惠資格，請按一下&#x200B;**[!UICONTROL Approve eligibility]**。

  ![提交資格按鈕在優惠方案對話方塊中開啟動作，並有核准和拒絕選項。](assets/offer_validate_008.png)

  核准資格，視需要新增註解，然後按一下&#x200B;**[!UICONTROL Eligibility approval]**。

  ![資格核准對話方塊，其中包含核准選取的專案、輸入的註解以及資格核准按鈕。](assets/offer_validate_009.png)

  優惠方案控制面板上的各種狀態都會更新。

  ![顯示優惠方案擱置部署至上線環境的儀表板，其資格已核准，內容已核准。](assets/offer_validate_010.png)

## 核准追蹤 {#approval-tracking}

核准追蹤可在優惠方案控制面板上使用。 按一下&#x200B;**[!UICONTROL Hide/display logs]**&#x200B;以存取它。

![按一下[隱藏/顯示記錄]，列出動作、型別和核准者之後，顯示核准記錄的優惠儀表板。](assets/offer_validate_012.png)

>[!NOTE]
>
>選件的&#x200B;**[!UICONTROL Audit]**&#x200B;標籤中也有追蹤功能，其中包含稽核者意見的詳細資料。

## 重新開始核准 {#restart-the-approval}

啟動核准後，即可重新啟動。 要執行此操作，請遵循下列指示：

1. 按一下優惠儀表板上的&#x200B;**[!UICONTROL Content approved]**。
1. 在出現的&#x200B;**[!UICONTROL Edit]**&#x200B;視窗中，選取要重新啟動的核准，然後按一下&#x200B;**[!UICONTROL Re-initialize approval to submit it again]**。
1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;確認。

![在[編輯]視窗中核准分錄，並具有[重新初始化]核准以再次提交該分錄連結。](assets/offer_validate_013.png)

## 發佈優惠方案 {#publishing-the-offer}

一旦優惠方案的內容和資格都獲得核准，優惠方案就會由工作流程發佈，該工作流程會針對每個核准週期結束的優惠方案自動執行。 **[!UICONTROL Offer notification]**&#x200B;工作流程也會每小時執行一次，以同步（如有必要）優惠方案目錄中所包含的空間和類別，從設計環境移至即時環境。

設計環境中可用選件的控制面板包含有關發佈的資訊，包括即時環境中相符選件的名稱。

![設計優惠儀表板：部署日期橫幅、具有已發佈狀態的優惠方案線上連結、即時代表線上。](assets/offer_golive_001.png)

若要顯示即時環境中可用的優惠方案，請按一下優惠方案標籤：即時優惠方案有一個包含其所有相關資訊的控制面板。

![連結至即時優惠儀表板，其中顯示線上狀態、環境、排程和適用性規則。](assets/offer_golive_002.png)

## 停用優惠方案 {#disabling-an-offer}

一旦核准優惠方案，您就可以加以停用。

若要這麼做，請移至儀表板，以取得線上優惠或等待上線的優惠，然後按一下&#x200B;**[!UICONTROL Disable offer]**。

您也可以前往「**[!UICONTROL Eligibility]**」標籤並勾選「**[!UICONTROL Enabled]**」方塊，直接停用類別。

>[!NOTE]
>
>在設計環境中刪除優惠方案時，它會在連結的線上環境中自動停用。 主張保留期過後，停用的優惠方案會從線上環境中刪除。

![優惠儀表板擱置部署，且停用優惠按鈕已用來停用優惠。](assets/offer_preview_deactivate.png)
