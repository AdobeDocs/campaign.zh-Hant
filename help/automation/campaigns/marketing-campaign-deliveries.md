---
product: campaign
title: 行銷活動傳遞
description: 深入了解行銷活動傳遞
feature: Campaigns, Resource Management, Cross Channel Orchestration
exl-id: 1d9638cb-0fc9-4d04-a9c5-bcab8f4ebe95
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# 行銷活動傳遞 {#marketing-campaign-deliveries}

在行銷活動中協調您的跨管道傳送：透過個人化電子郵件、簡訊、推播通知和應用程式內訊息，簡化您與Adobe Campaign的通訊。 您可以使用多媒體，例如視訊、表情符號或GIF，並直接加以整合。

傳遞可透過促銷活動控制面板、促銷活動工作流程或直接透過傳遞的概觀來建立。 從促銷活動建立傳遞時，傳遞將連結至此促銷活動，並在促銷活動層級進行整合。

## 建立傳遞 {#create-deliveries}

您有兩種方式可將傳送新增至行銷活動：

* 從 **[!UICONTROL Add a delivery]** 在促銷活動控制面板中的連結。

![](assets/campaign_op_add_delivery.png)

儲存後，傳遞會新增至促銷活動控制面板。

* 在促銷活動工作流程中， **[!UICONTROL Targeting and workflows]** 標籤，方法是新增傳送。

   ![](assets/campaign-wf-delivery.png)

   工作流程開始後，傳遞會新增至促銷活動控制面板。

了解如何設定及執行傳遞核准流程 [在本頁](marketing-campaign-approval.md).

## 開始傳送 {#start-a-delivery}

一旦所有核准都獲得授權，即可傳送。 傳送執行程式取決於通道。

* 如需電子郵件或行動通道傳送，請參閱 [本節](#start-an-online-delivery)

* 如需直接郵件傳送，請參閱 [本節](#start-an-offline-delivery)

### 開始電子郵件或行動傳送 {#start-an-online-delivery}

所有核准請求一經授與，傳送狀態會變更為 **[!UICONTROL Pending confirmation]** 和即可開始。 可以開始傳送的審核者會收到傳送已準備好開始的通知。

![](assets/confirm-delivery.png)

資訊也會顯示在促銷活動控制面板上。 此 **[!UICONTROL Confirm delivery]** 連結可讓您開始傳送。

![](assets/confirm-delivery-from-dashboard.png)

確認傳送僅限於「管理員」，以及傳送或促銷活動屬性中明確提及的運算子或運算子群組。 如果未設計運算子，管理員和促銷活動擁有者即可核准。

![](assets/select-delivery-reviewers.png)

不過，您也可以允許行銷活動擁有者確認傳送，即使已在傳送或行銷活動屬性中定義特定審核者亦然。 若要這麼做，請以管理員身分，建立 **NmsCampaign_Activate_OwnerConfirmation** 選項，並將其設為 **1**. 選項可從 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]** Campaign檔案總管的資料夾。


### 開始直接郵件傳送 {#start-an-offline-delivery}

一旦所有核准均獲得授權，傳送狀態會變更為 **[!UICONTROL Pending extraction]**. 解壓縮檔案會透過專用 [技術工作流程](../workflow/technical-workflows.md) 在預設設定中，當直接郵件傳送擱置提取時自動啟動。 進程進行中時，會顯示在控制面板中，並可透過其連結編輯。

擷取工作流程成功執行後，必須核准擷取檔案（前提是已在傳送設定中選取擷取檔案核准）。 [了解更多資訊](marketing-campaign-approval.md#approving-an-extraction-file)。

請依照下列步驟驗證內容，並將檔案傳送至提供者：

1. 提取檔案獲得批准後，您就可以生成路由器通知電子郵件的證明。 此電子郵件訊息是根據傳遞範本所建構。 必須獲得批准。

   此步驟僅在 **[!UICONTROL Enable the sending and validation of proofs (Direct mail)]** 選項 **[!UICONTROL Approvals]** 進階促銷活動參數的標籤。

   ![](assets/enable-proof-validation.png)

1. 按一下 **[!UICONTROL Send a proof]** 按鈕來建立校樣。

   必須預先定義校樣目標。

   您可以視需要建立任意數量的校樣。 這些項目可透過 **[!UICONTROL Direct mail...]** 傳送詳細資料的連結。

1. 傳送狀態變更為 **[!UICONTROL To submit]**. 按一下 **[!UICONTROL Submit proofs]** 按鈕，以啟動核准流程。

1. 傳送狀態變更為 **[!UICONTROL Proof to validate]** 按鈕可讓您接受或拒絕核准。

   您可以接受或拒絕此批准，或返回提取步驟。

1. 校樣獲得批准後，解壓檔案將發送到路由器並完成傳送。

### 預算和成本計算 {#compute-costs-and-stocks}

檔案擷取會啟動兩個程式：預算計算和庫存計算。 預算條目會更新。

* 此 **[!UICONTROL Budget]** 索引標籤可讓您管理促銷活動的預算。 成本分錄的合計顯示在 **[!UICONTROL Calculated cost]** 行銷活動主要標籤的欄位及其所屬方案。 這些金額也會反映在促銷活動預算中。

   ![](assets/campaign-budget-tab.png)

   實際成本最終將根據路由器提供的資訊計算。 只有實際發送的郵件才會開具發票。

* 股票定義於 **[!UICONTROL Administration > Campaign management > Stocks]** 樹的節點。

   ![](assets/campaign-stocks.png)

   成本結構 **[!UICONTROL Administration > Campaign management > Service providers]** 節點。

   ![](assets/campaign-service-providers.png)

   庫存行在庫存區中。 要定義初始庫存，請開啟一條庫存線。 每次發生交貨時庫存都會減少。 您可以定義警報級別和通知。


   >[!NOTE]
   >
   >深入了解預算 [在本節](providers--stocks-and-budgets.md).
