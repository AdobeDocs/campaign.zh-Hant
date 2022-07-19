---
product: campaign
title: 重複傳送
description: 瞭解有關「定期交貨」工作流活動的詳細資訊
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 14%

---

# 重複傳送{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** 活動，您可以配置特定於市場活動的交貨模板事件。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#recurring-delivery-video)

此活動僅可從 **[!UICONTROL Targeting and workflows]** 頁籤。

操作步驟：

1. 選擇活動將基於的交貨模板。

   ![](assets/recurring_delivery_001.png)

1. 配置傳遞模板。

此活動的配置過程與在可用選項方面建立交付模板的過程類似。 有關此的詳細資訊，請參閱此。

有關使用此活動的示例，請參閱此 [節](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow)。

## 如何設定循環交貨

A **循環交付** 將在每次執行時建立新的傳遞實例。 例如，如果排程每週執行一次工作流程，則在一年後會產生 52 項傳遞。 這還意味著，廣義日誌和跟蹤日誌將由每個傳遞實例分開。

![循環傳遞](assets/delivery_recurring.jpg)

如果要停止定期交貨的運行，則應完全取消市場活動或停止工作流執行該市場活動。 從「市場活動」控制面板中停止交貨將只停止交貨發生：每次執行工作流時，將繼續建立循環傳遞的下一個實例。

>[!NOTE]
>
>無法從 **[!UICONTROL Recurring delivery]** 鍵入活動。
> 
>要通過市場活動工作流直接建立交付，請使用預配置的渠道特定活動(例如 **[!UICONTROL Email delivery]**)。

## 教程視頻(#recurring-delivery-video)

此視頻說明了如何配置循環傳遞和調度程式活動。

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

可提供其他Campaign Classic操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hant)。
