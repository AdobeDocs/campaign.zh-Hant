---
title: 管理市場活動中的訂閱和取消訂閱
description: 了解如何管理 Campaign v8 的訂閱和取消訂閱。
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 11%

---

# 管理訂閱和取消訂閱{#optin-optout}

使用Adobe Campaign建立和監視新聞通訊等資訊服務，並管理對這些服務的訂閱/取消訂閱。 可以並行定義多個服務，例如：特定產品類別、網站主題或區域的專業通訊、各種類型的警報消息的訂閱和即時通知。 請參閱管理訂閱。

![](../assets/do-not-localize/book.png) 瞭解如何建立資訊服務、發送新聞稿以及管理選擇加入和選擇退出 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target="_blank"}

要預訂（選擇）服務的配置檔案，可用選項包括：

* 手動將服務添加到收件人配置檔案：來做這個， **[!UICONTROL Subscriptions]** 頁籤，按一下 **[!UICONTROL Add]** 選擇相關資訊服務。

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"}

* 自動將一組收件人訂閱到服務。 收件人清單可以來自篩選操作、組、資料夾、導入或直接手動選擇。 要訂閱這些收件人，請選擇配置檔案並按一下右鍵。 選取 **[!UICONTROL Actions > Subscribe selection to a service...]**。

   ![](assets/subscribe-selection.png)

   選擇相關服務，然後啟動該操作。

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"}


* 導入收件人並自動將其訂閱到資訊服務。 為此，請在導入嚮導的最後一步中選擇相關服務。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html#step-5---additional-step-when-importing-recipients){target="_blank"}

* 使用Web表單，以便收件人可以訂閱服務。

   ![](assets/opt-in-webapp.png)

   市場活動附帶了一個預設的Web表單來管理選擇加入。 您可以個性化它並映射配置檔案資料。

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html#create-a-subscription--form-with-double-opt-in){target="_blank"}


* 建立目標工作流並使用 **[!UICONTROL Subscription service]** 的子菜單。

   ![](assets/wf-subscription.png)

   在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html)中瞭解更多。

要取消訂閱（選擇退出）服務中的配置檔案，可用選項包括：

**手動取消訂閱**

* 個性化取消訂閱連結或Web表單
* 手動刪除資訊服務
* 從特定訂閱服務手動刪除收件人

**自動取消訂閱**

* 指定資訊服務的持續時間限制：有效期過後，收件人將自動取消訂閱。 此期間在服務屬性的「編輯」頁籤中指定。 它以天數表示。
* 為填充設定未訂閱工作流。

![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html#unsubscribing-a-recipient-from-a-service){target="_blank"}


>[!CAUTION]
>
>在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，訂閱和取消訂閱 **非同步** 進程。 每小時處理選擇加入和選擇退出請求。 [了解更多](../architecture/new-apis.md#sub-apis)

<!--
You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

![](../assets/do-not-localize/book.png) For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html#viral-marketing--forward-to-a-friend){target="_blank"}
-->
