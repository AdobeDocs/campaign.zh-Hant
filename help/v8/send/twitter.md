---
title: 透過Adobe Campaign在X (Twitter)上張貼訊息
description: 瞭解如何使用Adobe Campaign社交行銷模組在X (先前稱為Twitter)上發佈訊息，並傳送直接訊息給您的追隨者
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 2%

---


# 透過Adobe Campaign在X (Twitter)上張貼訊息 {#post-tw-messages}

Adobe Campaign隨附 **社交行銷** 可讓您透過X (先前稱為Twitter)與客戶和潛在客戶互動的模組。

設定整合後，您可以：

* 傳送直接訊息給您的追隨者
* 在您的X帳戶上發佈
* 透過恢復設定檔資料來收集新聯絡人，這可讓您執行目標定位行銷活動，並在可能時實施跨管道策略。 此動作需要使用者同意。


有關整合X帳戶與Adobe Campaign的設定步驟說明，請參閱 [此頁面](../connect/ac-tw.md).

## 建立並發佈X貼文 {#publish-on-tw}

請依照下列步驟，在您的X帳戶上張貼訊息：

1. 建立X傳遞

   根據以下專案建立新傳遞： **[!UICONTROL Tweet (twitter)]** 傳遞範本。

   ![](assets/tw-new-delivery.png)

1. 選取主要目標

   選取您要傳送貼文的帳戶。

   ![](assets/tw-define-target.png)

   1. 按一下&#x200B;**[!UICONTROL To]**&#x200B;連結。
   1. 按一下 **[!UICONTROL Add]** 按鈕。
   1. 選取 **[!UICONTROL A Twitter account]**。
   1. 在 **[!UICONTROL Folder]** 欄位中，選取包含X帳戶的服務資料夾。 然後選取您要傳送推文的X帳戶。

1. 選取校訂目標

   此 **[!UICONTROL Target of the proofs]** 索引標籤可讓您定義在最終傳送之前用於測試傳送的X帳戶。

   如 [設定步驟](../connect/ac-tw.md#tw-test-account)，您必須建立專用於傳送校樣的私人測試X帳戶。

   >[!NOTE]
   >
   >如果您的所有傳遞都使用相同的X測試帳戶，您可以將校樣目標儲存在 **[!UICONTROL Tweet]** 傳遞範本，可透過以下方式存取： **[!UICONTROL Resources > Templates > Delivery templates]** 節點。 之後，依預設會針對每個新傳遞輸入校樣目標。

1. 定義貼文的內容

   在「 」中輸入您貼文的內容 **[!UICONTROL Content]** 標籤。

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >在X上張貼時，會有下列限制：
   >
   >* 訊息不能超過140個字元。
   >* 不支援HTML格式。
   >

1. 預覽您的貼文

   瀏覽 **[!UICONTROL Preview]** 索引標籤以檢查貼文的轉譯。

   ![](assets/tw-delivery-preview.png)

   1. 按一下 **[!UICONTROL Preview]** 標籤。
   1. 按一下 **[!UICONTROL Test personalization]** 下拉式功能表並選取 **[!UICONTROL Service]**.
   1. 在 **[!UICONTROL Folder]** 欄位中，選取包含您X帳戶的服務資料夾。

1. 傳送證明

   在張貼推文之前，請務必傳送出版物的證明來驗證推文：您可以在私人X測試頁面上取得出版物的精確轉譯。

1. 張貼訊息

   1. 內容獲得核准後，按一下 **[!UICONTROL Send]** 按鈕。
   1. 選取 **[!UICONTROL Deliver as soon as possible]** 並按一下 **[!UICONTROL Analyze]** 按鈕。
   1. 分析完成後，檢查結果。
   1. 按一下 **[!UICONTROL Confirm delivery]**，然後按一下 **[!UICONTROL Yes]**.

## 傳送直接訊息給追隨者 {#direct-tw-messages}

此 **[!UICONTROL Synchronize Twitter accounts]** 技術工作流程會復原X位追隨者清單，因此您可以傳送直接訊息給他們。 [了解更多](../connect/ac-tw.md#synchro-tw-accounts)

若要傳送直接訊息給您的追隨者，請遵循下列步驟：

1. 建立X傳遞，根據 **[!UICONTROL Tweet (Direct Message)]** 內建傳遞範本。

1. 選取主要目標

   ![](assets/tw-dm-define-target.png)

   1. 選取 **[!UICONTROL To]** 連結和 **[!UICONTROL Add]** 按鈕。

   1. 選擇目標定位型別

      * 選取 **[!UICONTROL Twitter subscribers]** 傳送直接訊息給所有追隨者。

      * 選取 **[!UICONTROL Filter conditions]** 以定義查詢並檢視其結果。 瞭解如何在中建立篩選器 [本節](../audiences/create-filters.md#advanced-filters).

1. 從中選擇校訂目標 **[!UICONTROL Target of the proofs]** 標籤：此帳戶將收到您直接訊息的證明。

   如 [設定步驟](../connect/ac-tw.md#tw-test-account)，您必須建立專用於傳送校樣的私人測試X帳戶。


   >[!NOTE]
   >
   >如果您想要將所有直接訊息校樣傳送至相同的X帳戶，可以將校樣目標儲存在 **[!UICONTROL Tweet (Direct Message)]** 傳遞範本，可透過以下方式存取： **[!UICONTROL Resources > Templates > Delivery templates]** 節點。

1. 請在以下位置輸入訊息的內容： **[!UICONTROL Content]** 標籤。

   ![](assets/tw-dm-content.png)

   個人化欄位的使用方式與電子郵件傳遞相同，例如，在訊息本文中新增追隨者的名稱。 若要了解詳細資訊，請參閱[本章節](../send/personalize.md)。

1. 預覽您的訊息

   瀏覽 **[!UICONTROL Preview]** 索引標籤以檢查貼文的轉譯。

   ![](assets/tw-dm-preview.png)

   1. 按一下 **[!UICONTROL Preview]** 標籤。
   1. 按一下 **[!UICONTROL Test personalization]** 下拉式功能表並選取 **[!UICONTROL Visitor Subscription]**.
   1. 選擇您要用來測試預覽的X帳戶。

1. 傳送證明

   在傳送訊息之前，請務必透過以下方式驗證訊息 [傳送證明至測試帳戶](../send/preview-and-proof.md)：接著，您就可以在私人X帳戶上取得郵件的精確轉譯，並檢查內容與個人化。

1. 傳送直接訊息

   1. 內容獲得核准後，按一下 **[!UICONTROL Send]** 按鈕。
   1. 選取 **[!UICONTROL Deliver as soon as possible]** 並按一下 **[!UICONTROL Analyze]** 按鈕。
   1. 分析完成後，檢查結果。
   1. 按一下 **[!UICONTROL Confirm delivery]**，然後按一下 **[!UICONTROL Yes]**.

>[!CAUTION]
>
>您無法每天傳送超過250則直接訊息。 為避免超過此臨界值，您可以分階段傳送。 有關詳細資訊，請參閱 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## 存取追蹤資料 {#tw-tracking}

內建 **[!UICONTROL Tweet]** 傳遞範本，預設為啟用追蹤。

追蹤資料可在傳遞報表中檢視，也可在 **[!UICONTROL Edit > Tracking]** 傳遞與服務的標籤。

追蹤設定與電子郵件傳遞的設定相同。 進一步瞭解 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hant){target="_blank"}.

