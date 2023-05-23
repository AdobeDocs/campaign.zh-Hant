---
title: 在Twitter與Adobe Campaign發帖
description: 瞭解如何使用Adobe Campaign社會營銷模組在Twitter上發佈消息，並向您的追隨者發送直接消息
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 4%

---


# 在Twitter與Adobe Campaign發帖 {#post-tw-messages}

Adobe Campaign **社會營銷** 模組，讓您通過Twitter與客戶和潛在客戶進行互動。

配置整合後，您可以：

* 將直接消息發送給您的關注者
* 在你的Twitter帳戶上發帖
* 通過恢復配置檔案資料來收集新聯繫人，這使您能夠實施針對性市場活動，並在可能的情況下實施跨渠道策略。 此操作需要用戶同意。


有關將您的Twitter帳戶與Adobe Campaign整合的配置步驟，請參見 [此頁](../connect/ac-tw.md)。

## 建立和發佈Twitter帖子 {#publish-on-tw}

按照以下步驟在您的Twitter帳戶上發佈消息：

1. 建立Twitter交貨

   根據 **[!UICONTROL Tweet (twitter)]** 交貨模板。

   ![](assets/tw-new-delivery.png)

1. 選擇主目標

   選擇要向其發送推文的帳戶。

   ![](assets/tw-define-target.png)

   1. 按一下&#x200B;**[!UICONTROL To]**&#x200B;連結。
   1. 按一下 **[!UICONTROL Add]** 按鈕。
   1. 選取 **[!UICONTROL A Twitter account]**。
   1. 在 **[!UICONTROL Folder]** 欄位，選擇包含Twitter帳戶的服務資料夾。 然後選擇要將Twitter發送給的Twitter帳戶。

1. 選擇校樣目標

   的 **[!UICONTROL Target of the proofs]** 頁籤，用於定義在最終交貨之前用於test交貨的Twitter帳戶。

   如 [配置步驟](../connect/ac-tw.md#tw-test-account)，必須建立專用於發送校樣的testTwitter專用帳戶。

   >[!NOTE]
   >
   >如果您對所有交貨使用相同的Twittertest帳戶，則可以在 **[!UICONTROL Tweet]** 交付模板，通過 **[!UICONTROL Resources > Templates > Delivery templates]** 的下界。 然後，將預設為每個新交貨輸入證明目標。

1. 定義帖子的內容

   在 **[!UICONTROL Content]** 頁籤。

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >在Twitter上發帖時，限制適用：
   >
   >* 消息不能超過140個字元。
   >* HTML格式不受支援。


1. 預覽帖子

   瀏覽 **[!UICONTROL Preview]** 頁籤

   ![](assets/tw-delivery-preview.png)

   1. 按一下 **[!UICONTROL Preview]** 頁籤。
   1. 按一下 **[!UICONTROL Test personalization]** 下拉菜單並選擇 **[!UICONTROL Service]**。
   1. 在 **[!UICONTROL Folder]** 欄位中，選擇包含您的Twitter帳戶的服務資料夾。

1. 傳送證明

   在發佈推文之前，請確保通過發送發佈證明來驗證它：然後，您可以在私人Twittertest頁上獲得該出版物的準確呈現。

1. 發佈消息

   1. 內容獲得批准後，按一下 **[!UICONTROL Send]** 按鈕
   1. 選擇 **[!UICONTROL Deliver as soon as possible]** 並按一下 **[!UICONTROL Analyze]** 按鈕
   1. 分析完成後，檢查結果。
   1. 按一下 **[!UICONTROL Confirm delivery]**，然後按一下 **[!UICONTROL Yes]**。

## 向關注者發送直接消息 {#direct-tw-messages}

的 **[!UICONTROL Synchronize Twitter accounts]** 技術工作流恢復了Twitter關注者的清單，以便您可以直接向他們發送消息。 [了解更多](../connect/ac-tw.md#synchro-tw-accounts)

要將直接消息發送給您的追隨者，請執行以下步驟：

1. 根據 **[!UICONTROL Tweet (Direct Message)]** 內置交付模板。

1. 選擇主目標

   ![](assets/tw-dm-define-target.png)

   1. 選擇 **[!UICONTROL To]** 連結和 **[!UICONTROL Add]** 按鈕

   1. 選擇目標類型

      * 選擇 **[!UICONTROL Twitter subscribers]** 向你的所有追隨者發送直接資訊。

      * 選擇 **[!UICONTROL Filter conditions]** 定義查詢並查看其結果。 瞭解如何在中建立篩選器 [此部分](../audiences/create-filters.md#advanced-filters)。

1. 從 **[!UICONTROL Target of the proofs]** 頁籤：此帳戶將收到您直接發送的證明。

   如 [配置步驟](../connect/ac-tw.md#tw-test-account)，必須建立專用於發送校樣的testTwitter專用帳戶。


   >[!NOTE]
   >
   >如果要將所有直接消息憑證發送到同一個Twitter帳戶，可以將證明目標保存到 **[!UICONTROL Tweet (Direct Message)]** 交付模板，通過 **[!UICONTROL Resources > Templates > Delivery templates]** 的下界。

1. 在 **[!UICONTROL Content]** 頁籤。

   ![](assets/tw-dm-content.png)

   個性化欄位的使用方式與電子郵件遞送的使用方式相同，例如，在郵件正文中添加從機名稱。 在[本章節](../send/personalize.md)了解更多資訊。

1. 預覽您的郵件

   瀏覽 **[!UICONTROL Preview]** 頁籤

   ![](assets/tw-dm-preview.png)

   1. 按一下 **[!UICONTROL Preview]** 頁籤。
   1. 按一下 **[!UICONTROL Test personalization]** 下拉菜單並選擇 **[!UICONTROL Visitor Subscription]**。
   1. 選擇要test預覽的Twitter帳戶。

1. 傳送證明

   在發送郵件之前，請確保通過 [向一個test帳戶發送證據](../send/preview-and-proof.md):然後，您可以在Twitter的私人帳戶上獲得郵件的準確呈現，並檢查內容和個性化。

1. 發送直接消息

   1. 內容獲得批准後，按一下 **[!UICONTROL Send]** 按鈕
   1. 選擇 **[!UICONTROL Deliver as soon as possible]** 並按一下 **[!UICONTROL Analyze]** 按鈕
   1. 分析完成後，檢查結果。
   1. 按一下 **[!UICONTROL Confirm delivery]**，然後按一下 **[!UICONTROL Yes]**。

>[!CAUTION]
>
>每天不能發送250條以上的直接消息。 為避免超過此閾值，您可以以波形傳送。 如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## 訪問跟蹤資料 {#tw-tracking}

內置 **[!UICONTROL Tweet]** 交貨模板，預設情況下啟用跟蹤。

跟蹤資料可在交付報告和 **[!UICONTROL Edit > Tracking]** 的子菜單。

跟蹤配置與電子郵件傳遞相同。 瞭解詳情 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hant){target="_blank"}。

