---
title: 在Campaign中管理訂閱和取消訂閱
description: 了解如何管理 Campaign v8 的訂閱和取消訂閱
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 11%

---

# 管理訂閱和取消訂閱{#optin-optout}

使用Adobe Campaign建立並監視電子報等資訊服務，並管理這些服務的訂閱/取消訂閱。 可同時定義多個服務，例如：特定產品類別、網站主題或區域的專家通訊、各種警報訊息的訂閱及即時通知。 請參閱管理訂閱。

![](../assets/do-not-localize/book.png) 了解如何建立資訊服務、傳送電子報，以及管理選擇加入和選擇退出 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot;}

若要訂閱（選擇加入）服務的設定檔，可用的選項有：

* 手動將服務新增至收件者設定檔：要做到這一點，從 **[!UICONTROL Subscriptions]** 標籤，按一下 **[!UICONTROL Add]** 選擇相關資訊服務。

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;} 

* 自動為服務訂閱一組收件者。 收件者清單可來自篩選操作、群組、資料夾、匯入或直接手動選取。 若要訂閱這些收件者，請選取設定檔並按一下滑鼠右鍵。 選取 **[!UICONTROL Actions > Subscribe selection to a service...]**。

   ![](assets/subscribe-selection.png)

   選擇相關服務，然後開始操作。

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;} 


* 將收件者自動匯入並訂閱至資訊服務。 要執行此操作，請選取匯入精靈最後一個步驟中相關的服務。

   ![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;} 

* 使用Web表單，讓收件者可以訂閱服務。

   ![](assets/opt-in-webapp.png)

   Campaign隨附管理選擇加入的預設網頁表單。 您可以個人化它，並對應設定檔資料。

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;} 


* 建立目標工作流程並使用 **[!UICONTROL Subscription service]** 活動。

   ![](assets/wf-subscription.png)

   在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html)中瞭解更多。

若要取消訂閱（選擇退出）服務的設定檔，可用的選項有：

**手動取消訂閱**

* 個人化取消訂閱連結或網路表單
* 手動刪除資訊服務
* 從特定訂閱服務手動刪除收件者

**自動取消訂閱**

* 指定資訊服務的持續時間限制：有效期屆滿時，收件者會自動取消訂閱。 此期間在服務屬性的「編輯」頁簽中指定。 以天表示。
* 設定母體的取消訂閱工作流程。

![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;} 


>[!CAUTION]
>
>在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，訂閱與取消訂閱 **非同步** 程式。 每小時都會處理加入和退出請求。 [了解更多](../architecture/new-apis.md#sub-apis)

您也可以讓傳遞收件者將訊息轉送給朋友。 若要這麼做，請將相關連結插入您的傳送中。 然後，您就可以追蹤此共用程式以及相關頁面的造訪次數。

![](../assets/do-not-localize/book.png) 有關此功能的詳細資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target=&quot;_blank&quot;}
