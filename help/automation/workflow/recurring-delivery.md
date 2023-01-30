---
product: campaign
title: 重複傳送
description: 深入了解循環傳送工作流程活動
feature: Workflows
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 15%

---

# 重複傳送{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** 活動可讓您設定行銷活動專屬的傳送範本發生次數。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#recurring-delivery-video)

此活動僅可從 **[!UICONTROL Targeting and workflows]** 標籤。

操作步驟：

1. 選取活動將根據的傳送範本。

   ![](assets/recurring_delivery_001.png)

1. 設定傳送範本。

此活動的設定程式與根據可用選項建立傳送範本的程式類似。

如需所使用此活動的範例，請參閱 [節](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## 如何設定循環傳送

A **循環傳遞** 會在每次執行時建立新的傳送例項。 例如，如果排程每週執行一次工作流程，則在一年後會產生 52 項傳遞。 這也表示廣泛的記錄檔和追蹤記錄檔將依每個傳送例項加以區隔。

![循環傳遞](assets/delivery_recurring.jpg)

如果您想要停止循環傳送，應完全取消促銷活動或停止工作流程執行。 從Campaign控制面板停止傳送只會停止傳送發生：循環傳送的下一個例項將在每次工作流程執行時繼續建立。

>[!NOTE]
>
>無法從 **[!UICONTROL Recurring delivery]** 類型活動。
> 
>若要直接透過促銷活動工作流程建立傳送，請使用預先設定的通道特定活動(例如 **[!UICONTROL Email delivery]**)。

## 教學課程影片(#recurring-delivery-video)

此影片說明如何設定循環傳送和排程器活動。

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

提供其他Campaign Classic作法影片 [此處](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hant).
