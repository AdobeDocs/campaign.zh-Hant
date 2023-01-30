---
product: campaign
title: 跨頻道傳遞
description: 進一步了解跨通道傳遞
feature: Workflows, Channels Activity
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 跨頻道傳遞{#cross-channel-deliveries}

在 **[!UICONTROL Deliveries]** 標籤 [行銷活動工作流程](campaign-workflows.md) 活動。

選取您要作為傳送基礎的範本，並定義其內容。

您可以使用不同的定位活動，為工作流程上游的傳送指定目標。

在以下範例中，了解如何建立工作流程，在一週後傳送電子郵件或簡訊給推播通知訂閱者，然後傳送推播通知。 操作步驟：

1. 建立促銷活動.
1. 在 **[!UICONTROL Targeting and workflows]** 標籤，新增 **[!UICONTROL Query]** 活動。
1. 配置查詢：選取訂閱推播通知的收件者作為目標維度。

   >[!NOTE]
   >
   >對於推播通知，請使用 **訂閱應用程式** 目標維度。

   ![](assets/cross_channel_delivery_1.png)

1. 將篩選條件新增至查詢。 在此情況下，我們將選取具有行動電話號碼或電子郵件地址的收件者。

   ![](assets/cross_channel_delivery_2.png)

1. 新增 **[!UICONTROL Split]** 活動來劃分具有行動號碼的收件者和具有電子郵件地址的收件者。
1. 在 **[!UICONTROL Delivery]** 索引標籤，選取每個目標的傳送。

   在工作流程中按兩下傳送活動，以傳統傳送精靈的相同方式建立您的傳送。

   ![](assets/cross_channel_delivery_3.png)

1. 新增及設定 **[!UICONTROL Wait]** 活動，讓收件者不會一次收到太多傳送。
1. 新增 **[!UICONTROL Split]** 活動來劃分iOS或Android行動應用程式的訂閱者。

   為每個作業系統選擇服務。

   ![](assets/cross_channel_delivery_4.png)

1. 為每個作業系統選取並設定行動應用程式傳送。

   ![](assets/cross_channel_delivery_5.png)
