---
product: campaign
title: 更新彙總
description: 瞭解有關更新聚合工作流活動的詳細資訊
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# 更新彙總{#update-aggregate}

在中定義的聚合 [立方](../../v8/reporting/gs-cubes.md) 為了報告目的，可以使用特定活動進行更新。 A **[!UICONTROL Workflow]** 頁籤在配置聚合時可用。

瞭解有關中的立方和聚合的詳細資訊 [此部分](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates)。

要更新聚合，請編輯 **[!UICONTROL Update aggregate]** 並選擇要更新的多維資料集和聚合。

可以配置 **完整更新** 或 **部分更新**。

![](assets/update-aggregate-details.png)

預設情況下，在每次計算期間執行完整更新。 要啟用部分更新，請選擇該選項並定義更新條件。

![](assets/update-aggregate-partial.png)

一個好的做法是 **[!UICONTROL Scheduler]** 設定計算更新頻率的活動。
