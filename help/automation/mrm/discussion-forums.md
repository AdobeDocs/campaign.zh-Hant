---
product: campaign
title: 論壇
description: 瞭解如何使用活動討論論壇
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 論壇{#discussion-forums}

Adobe Campaign運營商可以利用論壇來共用資訊。 以下各要素有各自的論壇：計畫、計畫、活動、營銷資源、模擬、庫存。 每家運營商還設有私人論壇。 所有討論都是公開的，甚至是在個人論壇上。

操作員可以訂閱論壇，以在每次發佈消息時接收通知電子郵件。

## 訪問論壇 {#accessing-a-forum}

要訪問論壇，請瀏覽到儀表板，然後按一下 **[!UICONTROL Forum]** 連結。

![](assets/mrm-forum-icon.png)

消息及其響應從最新到最舊。

要啟動新線程，請按一下 **[!UICONTROL Add a discussion]** 按鈕。 的 **[!UICONTROL Discussion forum]** 框（請參閱下面）。

![](assets/mrm-forum-new-thread.png)


在 **[!UICONTROL Message]** 欄位和討論標題 **[!UICONTROL Subject]** 的子菜單。

預設情況下，已在此論壇中發佈消息的操作員會收到通知。 可以選擇要通知的附加運算子。 要通知多個運算子，請選擇一組運算子。

您可以使用  **[!UICONTROL Browse...]** 按鈕 附件也將包含在通知電子郵件中。 附件只能單獨發送：若要發送多個檔案，您需要將其壓縮到.zip檔案中。

>[!CAUTION]
>
>一旦將郵件發佈到論壇，就無法再更改或刪除它。

## 發佈到操作員的個人論壇 {#posting-to-the-personal-forum-of-an-operator}

您可以向操作員的論壇發佈消息。 個人論壇是公共的，所有操作員都可以看到您的消息。 操作員每次有人向其個人論壇發帖時都會收到電子郵件通知。

要訪問操作員的論壇，您可以：

* 瀏覽到 **[!UICONTROL Administration > Access management > Operators]** 市場活動瀏覽器的資料夾，選擇操作員以開啟其儀表板，然後按一下 **[!UICONTROL Forum]** 連結。
* 在Adobe CampaignUI中查找操作員的名稱（通過此操作員發佈到論壇的消息，指派給他們的任務），然後按一下該名稱以訪問操作員儀表板。

## 訂閱論壇 {#subscribing-to-a-forum}

訂閱論壇可讓您跟蹤所有討論。 訂閱後，每次將郵件發佈到論壇時，您都會收到電子郵件通知。

要應答消息，請按一下電子郵件正文，然後登錄Adobe CampaignWeb介面。

* 要訂閱論壇，請按一下 **[!UICONTROL Follow discussions]** 按鈕。

   該部分呈藍色，顯示您已訂閱論壇。

* 要取消訂閱論壇，請按一下 **[!UICONTROL Unsubscribe]** 按鈕

* 您的個人儀表板會列出您訂閱的論壇。 按一下 **[!UICONTROL Subscription to discussion forums]** 連結以顯示清單，然後按一下您感興趣的項目以訪問其論壇。

   ![](assets/forum-subscribed.png)


## 疑難解答通知傳遞 {#checking-notification-delivery}

如果訂閱論壇的操作員未按預期接收通知：

* 檢查是否在操作員的配置檔案中輸入了電子郵件地址。
* 瀏覽到 **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** 市場活動瀏覽器的資料夾，並檢查 **[!UICONTROL Jobs in discussion forums]** 工作流啟動時沒有錯誤。
* 檢查交貨日誌：

   * 在Adobe Campaign首頁上，瀏覽到 **[!UICONTROL Campaigns > Navigation > Deliveries]**，然後開啟 **[!UICONTROL Discussion forum notification]** 交貨。
   * 在市場活動瀏覽器中，瀏覽到 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然後按一下 **[!UICONTROL Discussion forum notifications]**。
   在 **[!UICONTROL Discussion forum notifications]** 框中，在 **[!UICONTROL Edit > Delivery]** 頁籤。 您還可以查看 **[!UICONTROL Tracking > Log]** 和 **[!UICONTROL Exclusion causes]** 頁籤。
