---
product: campaign
title: 傳出頻道上的產品建議
description: 傳出頻道上的產品建議
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-wordcount: '831'
ht-degree: 1%
---
# 傳出頻道上的產品建議{#offers-on-an-outbound-channel}



## 電子郵件選件傳遞 {#email-offer-delivery}

在我們的資料庫中，有一個前往非洲的旅行優惠方案類別。 已設定每個優惠方案的適用性、內容與表示方式。 我們現在想要建立行銷活動，透過電子郵件呈現我們的優惠方案。

1. 建立行銷活動和目標定位工作流程。

   ![Trips to Africa行銷活動的目標工作流程：資料夾、傳遞、重複資料刪除和兩個清單更新活動](assets/offer_delivery_example_001.png)

1. 編輯電子郵件傳遞並按一下&#x200B;**[!UICONTROL Offers]**&#x200B;圖示。

   ![電子郵件傳遞，其優惠方案圖示會開啟優惠方案管理視窗、優惠方案選擇選項和優惠方案空間欄位](assets/offer_delivery_example_002.png)

1. 為您的優惠方案環境選擇符合假日的電子郵件空間。

   ![優惠方案管理視窗，其中優惠方案空間清單顯示可用的電子郵件空間，包括訂閱者歷程](assets/offer_delivery_example_003.png)

1. 選擇包含非洲旅行優惠方案的類別。

   ![優惠方案管理視窗，類別樹狀結構展開於優惠方案目錄和歷程下，非洲類別醒目提示](assets/offer_delivery_example_004.png)

1. 將傳送中的選件數量設定為兩個。

   ![類別為「非洲」的優惠方案管理視窗，且每則訊息的建議數量設為2](assets/offer_delivery_example_005.png)

1. 關閉Offer Management視窗，並建立您的傳遞內容。

   ![使用預設包含檢視的電子郵件傳遞HTML內容編輯器，準備好提出優惠方案](assets/offer_delivery_example_006.png)

1. 使用功能表插入第一個優惠方案主張，並選擇HTML演算函式。

   ![HTML內容工具列功能表：主張，然後主張1、轉譯函式和HTML轉譯](assets/offer_delivery_example_007.png)

1. 插入第二個優惠方案主張。

   ![在取消訂閱連結之前，透過使用轉譯/HTML檢視傳送電子郵件HTML內容（包含兩個主張）](assets/offer_delivery_example_008.png)

1. 按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以預覽傳遞中的優惠，然後選取收件者以預覽他們將會收到的優惠。

   ![傳遞預覽索引標籤，顯示所選收件者的電子郵件，其標題為Crossing the Sahara，文字和影像為](assets/offer_delivery_example_009.png)

1. 儲存您的傳送並啟動目標定位工作流程。
1. 開啟您的傳遞，然後按一下傳遞的&#x200B;**[!UICONTROL Audit]**&#x200B;標籤：您可以看到優惠方案引擎已選取要從目錄中的各種優惠方案提出的主張。

   ![傳遞稽核索引標籤記錄列出每個選件產生的主張，例如Pyramids和Sahara選件](assets/offer_delivery_example_010.png)

## 執行優惠方案模擬 {#perform-an-offer-simulation}

1. 在&#x200B;**[!UICONTROL Profiles and Targets]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Simulations]**&#x200B;連結，然後按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

   ![使用[建立]按鈕的模擬清單，開啟包含範本、標籤和資料夾的[新增優惠方案模擬]對話方塊](assets/offer_simulation_001.png)

1. 選擇標籤，並視需要指定執行設定。

   ![新優惠方案模擬對話方塊，包含標籤1年訂閱者、Simulations資料夾及執行設定](assets/offer_simulation_example_002.png)

1. 儲存模擬。 然後會在新標籤中開啟。

   ![具有[編輯]索引標籤和[開始]模擬按鈕之1年訂閱者的模擬儀表板](assets/offer_simulation_example_003.png)

1. 按一下「**[!UICONTROL Edit]**」標籤，然後按&#x200B;**[!UICONTROL Scope]**。

   ![模擬編輯標籤、範圍區段，包含環境或類別、優惠方案空間、主題、聯絡日期和主張](assets/offer_simulation_example_004.png)

1. 選擇要模擬優惠方案的類別。

   ![在優惠方案 — 設計和優惠方案目錄下展開的環境或類別清單，並選取旅行類別](assets/offer_simulation_example_005.png)

1. 選擇要用於模擬的優惠方案空間。

   ![旅行類別下的優惠方案空間清單，提供直接郵件和電子郵件（環境 — 收件者）](assets/offer_simulation_example_006.png)

1. 輸入有效日期。 您至少必須輸入開始日期。 這可讓優惠方案引擎篩選優惠方案，並選擇在指定日期有效的優惠方案。
1. 如有必要，請指定一或多個主題，將選件數量限製為設定中包含此關鍵字的選件數量。

   在我們的範例中，**旅遊**&#x200B;類別包含兩個子類別和兩個不同的主題。 我們想要針對具有&#x200B;**客戶>1年**&#x200B;主題的優惠方案執行模擬。

   ![在旅行類別的[主題]欄位中輸入客戶> 1年主題的範圍區段](assets/offer_simulation_example_007.png)

1. 選擇您要鎖定的收件者。

   ![目標選擇篩選精靈選擇收件者清單，然後選擇頻繁旅行者清單](assets/offer_simulation_example_008.png)

1. 設定要傳送給每個收件者的優惠方案數量。

   在我們的範例中，優惠方案引擎會為每個收件者選擇權重最高的3個優惠方案。

   ![主張數設為3的範圍區段，以及特殊優惠傳遞清單上的目標查詢](assets/offer_simulation_example_009.png)

1. 儲存您的設定，然後按一下「**[!UICONTROL Dashboard]**」標籤中的「**[!UICONTROL Start]**」以執行模擬。

   ![儀表板開始模擬對話方塊要求確認，並反白顯示[確定]按鈕](assets/offer_simulation_example_010.png)

1. 模擬完成後，請參閱&#x200B;**[!UICONTROL Results]**&#x200B;以取得每個選件的主張詳細劃分。

   在我們的範例中，優惠方案引擎是根據3個主張進行優惠方案劃分。

   ![模擬結果索引標籤，依選件劃分主張：母體大小30、主張數量30](assets/offer_simulation_example_011.png)

1. 顯示&#x200B;**[!UICONTROL Breakdown of offers by rank]**&#x200B;以檢視優惠方案引擎所選取的優惠方案清單。

   ![依等級列出的優惠方案劃分報告，內含「到美國旅行和探索法國」的優惠方案等級表，以及圓形圖](assets/offer_simulation_example_012.png)

1. 如有需要，您可以按一下&#x200B;**[!UICONTROL Start simulation]**&#x200B;來變更範圍設定並重新執行模擬。

   ![儀表板開始模擬對話方塊要求確認，並反白顯示[確定]按鈕](assets/offer_simulation_example_010.png)

1. 若要儲存模擬資料，請使用報表中可用的歷史記錄或匯出函式。

   ![使用「匯出」功能表及醒目提示儲存圖示依排名劃分優惠方案報表](assets/offer_simulation_example_013.png)
