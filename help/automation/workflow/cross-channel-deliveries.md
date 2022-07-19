---
product: campaign
title: 跨頻道傳遞
description: 瞭解有關跨渠道交付的更多資訊
feature: Workflows, Channels Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# 跨頻道傳遞{#cross-channel-deliveries}

在中提供跨渠道交付 **[!UICONTROL Deliveries]** 頁籤 [活動工作流](campaign-workflows.md) 活動。

選擇要作為交付基礎的模板並定義其內容。

您可以使用不同的目標活動為工作流上游的交付指定目標。

在下面的示例中，瞭解如何建立工作流以發送電子郵件或發送用於推送通知訂閱者的SMS，然後在一週後發送推送通知。 操作步驟：

1. 建立促銷活動.
1. 在 **[!UICONTROL Targeting and workflows]** 頁籤，添加 **[!UICONTROL Query]** 的子菜單。
1. 配置查詢：選擇訂閱推送通知的收件人作為目標維。

   >[!NOTE]
   >
   >對於推送通知，請使用 **訂戶應用程式** 目標維。

   ![](assets/cross_channel_delivery_1.png)

1. 將篩選條件添加到查詢。 在這種情況下，我們將選擇具有移動號碼或電子郵件地址的收件人。

   ![](assets/cross_channel_delivery_2.png)

1. 添加 **[!UICONTROL Split]** 活動到您的工作流，以劃分具有移動號碼的收件人和具有電子郵件地址的收件人。
1. 在 **[!UICONTROL Delivery]** 頁籤，為每個目標選擇交貨。

   通過按兩下工作流中的傳遞活動，以與傳統傳遞嚮導相同的方式建立傳遞。 有關此的詳細資訊，請參閱此。

   ![](assets/cross_channel_delivery_3.png)

1. 添加和配置 **[!UICONTROL Wait]** 活動，以便接收者不能同時接收太多交貨。
1. 添加 **[!UICONTROL Split]** 分配iOS或安卓移動應用的用戶。

   為每個作業系統選擇服務。 有關建立服務的詳細資訊，請參閱此。

   ![](assets/cross_channel_delivery_4.png)

1. 為每個作業系統選擇並配置移動應用程式交付。

   ![](assets/cross_channel_delivery_5.png)
