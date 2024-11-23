---
product: campaign
title: 週期性傳遞
description: 深入瞭解循環傳送工作流程活動
feature: Workflows
role: User, Data Engineer
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 13%

---

# 週期性傳遞{#recurring-delivery}



**[!UICONTROL Recurring delivery]**&#x200B;活動可讓您設定行銷活動特定的傳遞範本發生次數。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#recurring-delivery-video)

此活動只能從行銷活動中找到的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;索引標籤中使用。

操作步驟：

1. 選取活動將依據的傳遞範本。

   ![](assets/recurring_delivery_001.png)

1. 設定傳遞範本。

此活動的設定程式與根據可用選項建立傳遞範本的程式類似。

如需此活動使用中的範例，請參閱此[區段](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow)。

## 如何設定循環傳遞

**循環傳遞**&#x200B;每次執行時都會建立新的傳遞執行個體。 例如，如果排程每週執行一次工作流程，則在一年後會產生 52 項傳遞。 這也表示廣泛的記錄檔和追蹤記錄檔會依每個傳送執行個體區隔。

![循環傳遞](assets/delivery_recurring.jpg)

如果您想要停止執行週期性傳送，您應該完全取消行銷活動或停止執行它的工作流程。 從Campaign控制面板停止傳送只會停止傳送發生：循環傳送的下一個例項將繼續在每個工作流程執行時建立。

>[!NOTE]
>
>無法從&#x200B;**[!UICONTROL Recurring delivery]**&#x200B;型別活動傳送校樣。
> 
>若要透過行銷活動工作流程直接建立傳遞，請使用預先設定的通道特定活動（例如&#x200B;**[!UICONTROL Email delivery]**）。

## 教學課程影片(#recurring-delivery-video)

此影片說明如何設定循環傳遞和排程器活動。

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}提供其他Campaign操作說明影片。
