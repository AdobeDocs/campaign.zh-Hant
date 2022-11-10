---
product: campaign
title: 論壇
description: 了解如何使用Campaign論壇
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 論壇{#discussion-forums}

Adobe Campaign運營商可使用論壇來共用資訊。 以下各元素有各自的論壇：計畫、方案、行銷活動、行銷資源、模擬、股票。 每家運營商還有個人論壇。 所有討論都是公開的，甚至在個人論壇上。

操作員可以訂閱論壇，以在每次發送郵件時接收通知電子郵件。

## 存取論壇 {#accessing-a-forum}

若要存取論壇，請瀏覽至控制面板，然後按一下 **[!UICONTROL Forum]** 連結。

![](assets/mrm-forum-icon.png)

訊息及其回應會從最新到最舊顯示。

要啟動新線程，請按一下 **[!UICONTROL Add a discussion]** 按鈕。 此 **[!UICONTROL Discussion forum]** 框（請參閱下面）。

![](assets/mrm-forum-new-thread.png)


在 **[!UICONTROL Message]** 欄位與討論標題 **[!UICONTROL Subject]** 欄位。

預設情況下，已在此論壇中發佈消息的操作員會收到通知。 您可以選取要通知的其他運算子。 要通知多個運算子，請選擇一組運算子。

您可以使用  **[!UICONTROL Browse...]** 按鈕。 通知電子郵件也會包含附件。 附件只能單獨發送：若要傳送數個檔案，您需要將其壓縮為.zip檔案。

>[!CAUTION]
>
>將訊息張貼至論壇後，就無法再變更或刪除訊息。

## 發佈至操作員的個人論壇 {#posting-to-the-personal-forum-of-an-operator}

您可以將訊息張貼至運算子的論壇。 個人論壇是公開的，所有操作者都能看到您的訊息。 每當有人貼文至其個人論壇時，運算子都會收到電子郵件通知。

若要存取運算子的論壇，您可以：

* 瀏覽至 **[!UICONTROL Administration > Access management > Operators]** 行銷活動總管的資料夾，選取運算子以開啟其控制面板，然後按一下 **[!UICONTROL Forum]** 連結。
* 在Adobe Campaign UI中尋找運算子的名稱（透過此運算子張貼至論壇的訊息，指派給他們的任務），然後按一下它以存取運算子控制面板。

## 訂閱論壇 {#subscribing-to-a-forum}

訂閱論壇可讓您關注所有討論。 訂閱後，您會在每次將訊息張貼至論壇時收到電子郵件通知。

若要回答訊息，請按一下電子郵件內文，然後登入Adobe Campaign網頁介面。

* 若要訂閱論壇，請按一下 **[!UICONTROL Follow discussions]** 按鈕（位於消息清單的右上角）。

   區段顯示為藍色，顯示您已訂閱論壇。

* 若要取消訂閱論壇，請按一下 **[!UICONTROL Unsubscribe]** 按鈕。

* 您的個人儀表板會列出您訂閱的論壇。 按一下 **[!UICONTROL Subscription to discussion forums]** 連結以顯示清單，然後按一下您感興趣的項目以存取其論壇。

   ![](assets/forum-subscribed.png)


## 疑難排解通知傳送 {#checking-notification-delivery}

如果訂閱論壇的運算子未如預期般收到通知：

* 檢查是否在運算子的設定檔中輸入電子郵件地址。
* 瀏覽至 **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** 行銷活動檔案總管的資料夾，並檢查 **[!UICONTROL Jobs in discussion forums]** 工作流程啟動時沒有錯誤。
* 檢查傳送記錄：

   * 在Adobe Campaign首頁上，瀏覽至 **[!UICONTROL Campaigns > Navigation > Deliveries]**，然後開啟 **[!UICONTROL Discussion forum notification]** 傳遞。
   * 在Campaign總管中，瀏覽至 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然後按一下 **[!UICONTROL Discussion forum notifications]**.
   在 **[!UICONTROL Discussion forum notifications]** 框中，則在 **[!UICONTROL Edit > Delivery]** 標籤。 您也可以檢視 **[!UICONTROL Tracking > Log]** 和 **[!UICONTROL Exclusion causes]** 標籤。
