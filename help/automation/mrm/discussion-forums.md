---
product: campaign
title: 論壇
description: 瞭解如何使用Campaign論壇
feature: Campaigns, Resource Management
role: User
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 論壇{#discussion-forums}

Adobe Campaign操作人員可使用討論區來共用資訊。 下列各元素有各自的論壇：計畫、方案、行銷活動、行銷資源、模擬、庫存。 每個操作員也有一個個人論壇。 所有討論都是公開的，甚至在個人論壇中也是如此。

操作員可以訂閱論壇，以便在每次張貼訊息時收到通知電子郵件。

## 存取論壇 {#accessing-a-forum}

若要存取論壇，請瀏覽到儀表板並按一下右上角的&#x200B;**[!UICONTROL Forum]**&#x200B;連結。

![](assets/mrm-forum-icon.png)

訊息及其回應會以從最新到最舊的順序顯示。

若要啟動新執行緒，請按一下右上角的&#x200B;**[!UICONTROL Add a discussion]**&#x200B;按鈕。 會出現&#x200B;**[!UICONTROL Discussion forum]**&#x200B;方塊（請參閱下文）。

![](assets/mrm-forum-new-thread.png)


在&#x200B;**[!UICONTROL Message]**&#x200B;欄位中輸入您的文字，並在&#x200B;**[!UICONTROL Subject]**&#x200B;欄位中輸入討論標題。

預設會通知已在此論壇中張貼訊息的操作者。 您可以選取要通知的其他運運算元。 若要通知數個運運算元，請選取一組運運算元。

您可以使用&#x200B;**[!UICONTROL Browse...]**&#x200B;按鈕將附件新增至郵件。 附件也會包含在通知電子郵件中。 附件只能個別傳送：若要傳送多個檔案，必須將其壓縮為.zip檔案。

>[!CAUTION]
>
>訊息一旦張貼至論壇，就無法再變更或刪除。

## 張貼至操作員的個人論壇 {#posting-to-the-personal-forum-of-an-operator}

您可以張貼訊息至運運算元的論壇。 個人論壇是公開的，所有操作員都可以看到您的訊息。 操作員在每次有人張貼到他們的個人論壇時都會收到電子郵件通知。

若要存取運運算元的論壇，您可以：

* 瀏覽至Campaign檔案總管的&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;資料夾，選取運運算元以開啟其儀表板，然後按一下右上角的&#x200B;**[!UICONTROL Forum]**&#x200B;連結。
* 在Adobe Campaign UI中尋找運運算元的名稱（透過此運運算元張貼至論壇的訊息、指派給他們的任務），然後按一下以存取運運算元控制面板。

## 訂閱論壇 {#subscribing-to-a-forum}

訂閱論壇可讓您關注所有討論。 訂閱後，每次在論壇中張貼訊息時，您都會收到電子郵件通知。

若要回複訊息，請按一下電子郵件內文，然後登入Adobe Campaign網路介面。

* 若要訂閱論壇，請按一下訊息清單上方右上角的&#x200B;**[!UICONTROL Follow discussions]**&#x200B;按鈕。

  區段變為藍色，並顯示您已訂閱論壇。

* 若要取消訂閱論壇，請按一下&#x200B;**[!UICONTROL Unsubscribe]**&#x200B;按鈕。

* 您的個人儀表板會列出您訂閱的論壇。 按一下&#x200B;**[!UICONTROL Subscription to discussion forums]**&#x200B;連結以顯示清單，然後按一下您感興趣的專案以存取其論壇。

  ![](assets/forum-subscribed.png)


## 疑難排解通知傳送 {#checking-notification-delivery}

如果訂閱論壇的運運算元沒有如預期收到通知：

* 檢查是否在操作員的設定檔中輸入電子郵件地址。
* 瀏覽至Campaign檔案總管的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Campaign processes]**&#x200B;資料夾，並檢查&#x200B;**[!UICONTROL Jobs in discussion forums]**&#x200B;工作流程是否啟動且沒有錯誤。
* 檢查傳送記錄檔：

   * 在Adobe Campaign首頁上，瀏覽至&#x200B;**[!UICONTROL Campaigns > Navigation > Deliveries]**，然後開啟&#x200B;**[!UICONTROL Discussion forum notification]**&#x200B;傳遞。
   * 在Campaign總管中，瀏覽至&#x200B;**[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然後按一下&#x200B;**[!UICONTROL Discussion forum notifications]**。

  在&#x200B;**[!UICONTROL Discussion forum notifications]**&#x200B;方塊中，在&#x200B;**[!UICONTROL Edit > Delivery]**&#x200B;索引標籤中找到傳遞記錄。 您也可以檢視&#x200B;**[!UICONTROL Tracking > Log]**&#x200B;和&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;標籤。
