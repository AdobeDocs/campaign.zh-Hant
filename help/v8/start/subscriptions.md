---
title: 在Campaign中管理訂閱和取消訂閱
description: 了解如何管理 Campaign v8 的訂閱和取消訂閱。
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 08e04f3642320df94d719a415e878e3a26d2e00f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 13%

---

# 管理訂閱和取消訂閱 {#optin-optout}

使用Adobe Campaign建立及監控您的資訊服務（例如電子報），並管理這些服務的訂閱/取消訂閱。 數個服務可並行定義，例如：特定產品類別、網站主題或區域的專業電子報、各種警報訊息型別的訂閱和即時通知。

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target="_blank"}中瞭解如何建立資訊服務、傳送Newsletter及管理選擇加入和選擇退出

若要訂閱（選擇加入）服務的設定檔，可用選項包括：

* 手動將服務新增至收件者設定檔：若要這麼做，請從其設定檔的&#x200B;**[!UICONTROL Subscriptions]**&#x200B;索引標籤，按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選取相關的資訊服務。

  ![](assets/subscribe-to-a-service.png)

  在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"} 中深入瞭解

* 自動為一組收件者訂閱服務。 收件者清單可能來自篩選操作、群組、資料夾、匯入或直接手動選擇。 若要訂閱這些收件者，請選取設定檔，然後按一下滑鼠右鍵。 選取 **[!UICONTROL Actions > Subscribe selection to a service...]**。

  ![](assets/subscribe-selection.png)

  選取相關的服務，然後啟動作業。

  ![](assets/subscribe-confirm.png)

  在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"} 中深入瞭解


* 匯入收件者並自動訂閱資訊服務。 若要這麼做，請選取匯入精靈最後一步中涉及的服務。

  在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html#step-5---additional-step-when-importing-recipients){target="_blank"}中進一步瞭解。

* 使用網路表單，讓收件者可以訂閱服務。

  ![](assets/opt-in-webapp.png)

  Campaign隨附預設網頁表單，可管理選擇加入。 您可以加以個人化，並對應設定檔資料。

  ![](assets/web-app.png)

  在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html#create-a-subscription--form-with-double-opt-in){target="_blank"}中進一步瞭解。


* 建立目標工作流程並使用&#x200B;**[!UICONTROL Subscription service]**&#x200B;活動。

  ![](assets/wf-subscription.png)

  在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html){target="_blank"}中瞭解更多。

若要取消訂閱（選擇退出）服務的設定檔，可用選項包括：

**手動取消訂閱**

* 個人化的取消訂閱連結或網頁表單
* 手動刪除資訊服務
* 從特定訂閱服務手動刪除收件者

**自動取消訂閱**

* 指定資訊服務的期間限制：當有效期間過期時，收件者會自動取消訂閱。 此期間在服務屬性的[編輯]索引標籤中指定。 以天為單位表示。
* 設定母體的取消訂閱工作流程。

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html#unsubscribing-a-recipient-from-a-service){target="_blank"}中進一步瞭解。


>[!CAUTION]
>
>在[企業(FFDA)部署](../architecture/enterprise-deployment.md)的內容中，訂閱和取消訂閱是&#x200B;**非同步**&#x200B;程式。 每小時都會處理選擇加入和選擇退出請求。 [了解更多](../architecture/new-apis.md#sub-apis)

<!--
You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html#viral-marketing--forward-to-a-friend){target="_blank"}
-->
