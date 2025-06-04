---
product: campaign
title: 排程器
description: 深入瞭解排程器工作流程活動
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 8%

---

# 排程器 {#scheduler}



**排程器**&#x200B;是持續性工作，會在排程所指定的時間啟動其轉換。

**[!UICONTROL Scheduler]** 活動應視為已排程的開始。圖表中的活動定位規則與活動 **[!UICONTROL Start]** 的定位規則相同。此活動不得具有入站轉變。

## 最佳實務 {#best-practices}

**在變更排程器時間後重新啟動工作流程** — 變更&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動的排程時間時，請務必重新啟動工作流程。 這可確保工作流程將在更新時執行。 如果不重新啟動，工作流程將繼續根據舊排程執行。

**限制排程器頻率** — 避免排程工作流程的執行頻率超過每15分鐘一次。 更頻繁地執行它們可能會降低系統效能並導致資料庫阻塞。

**每個分支使用一個排程器** — 工作流程的每個分支應該只能有一個&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動。 如需在工作流程中使用活動的最佳實務的詳細資訊，請參閱[工作流程最佳實務頁面](workflow-best-practices.md#using-activities)。

**防止工作流程並行執行** — 如果工作流程是由排程器觸發，請注意工作流程的多個執行個體可能同時執行。 例如，如果排程器每小時觸發工作流程，但工作流程執行超過一小時，您最終可能會遇到重複執行。為避免這種情況，請考慮設定檢查以防止多個同時執行。 [瞭解如何防止同時執行多個工作流程](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)。

**解決延遲的轉換** — 如果工作流程正在執行長時間執行的工作（如匯入），或如果wfserver模組已暫時停止，排程器所觸發的轉換可能會延遲。 若要緩解此問題，請限制排程器的啟動時間，以確保工作會在定義的時間範圍內執行。

## 設定排程器活動 {#configuring-scheduler-activity}

排程器會定義轉變的啟動排程。 若要進行設定，請按兩下圖形物件，然後按一下&#x200B;**[!UICONTROL Change...]**

![](assets/s_user_segmentation_scheduler.png)

精靈可讓您定義活動的頻率和有效期間。 設定步驟如下：

1. 選取啟動頻率，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/s_user_segmentation_scheduler2.png)

1. 提供啟用時間和天數。 此步驟的引數取決於上一步驟中所選的頻率。 如果您選擇一天啟動活動數次，設定選項如下：

   ![](assets/s_user_segmentation_scheduler3.png)

1. 定義排程的有效期，或指定要執行的次數。

   ![](assets/s_user_segmentation_scheduler4.png)

1. 檢查設定，然後按一下&#x200B;**[!UICONTROL Finish]**&#x200B;儲存。

   ![](assets/s_user_segmentation_scheduler5.png)
