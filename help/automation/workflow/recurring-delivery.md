---
product: campaign
title: 重複傳送
description: 深入瞭解循環傳送工作流程活動
feature: Workflows
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 12%

---

# 重複傳送{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** 活動可讓您設定行銷活動特定的傳送範本發生次數。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#recurring-delivery-video)

此活動只能從 **[!UICONTROL Targeting and workflows]** 在行銷活動中找到的索引標籤。

操作步驟：

1. 選取活動將依據的傳遞範本。

   ![](assets/recurring_delivery_001.png)

1. 設定傳遞範本。

此活動的設定程式與根據可用選項建立傳遞範本的程式類似。

如需此活動使用方式的範例，請參閱以下內容 [區段](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## 如何設定循環傳遞

A **循環傳遞** 每次執行時都會建立新的傳遞執行個體。 例如，如果排程每週執行一次工作流程，則在一年後會產生 52 項傳遞。 這也表示廣泛的記錄檔和追蹤記錄檔會依每個傳送執行個體來區隔。

![循環傳遞](assets/delivery_recurring.jpg)

如果您想要停止執行循環傳送，您應完全取消行銷活動或停止執行它的工作流程。 從Campaign儀表板停止傳送只會停止傳送發生：循環傳送的下一個例項將繼續在每個工作流程執行時建立。

>[!NOTE]
>
>無法傳送來自 **[!UICONTROL Recurring delivery]** 型別活動。
> 
>若要透過行銷活動工作流程直接建立傳遞，請使用預先設定的管道特定活動(例如 **[!UICONTROL Email delivery]**)。

## 教學課程影片(#recurring-delivery-video)

此影片說明如何設定循環傳送和排程器活動。

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

有其他Campaign操作說明影片可供使用 [此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
