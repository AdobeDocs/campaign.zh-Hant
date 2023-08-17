---
product: campaign
title: 更新彙總
description: 深入瞭解更新彙總工作流程活動
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

中定義的彙總 [立方體](../../v8/reporting/gs-cubes.md) 如需報表，可透過特定活動進行更新。 A **[!UICONTROL Workflow]** 標籤在設定彙總時可供使用。

進一步瞭解中的立方結構和彙總 [本節](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

若要更新彙總，請編輯 **[!UICONTROL Update aggregate]** 活動，並選取要更新的立方結構和聚總。

您可以設定 **完整更新** 或 **部分更新**.

![](assets/update-aggregate-details.png)

依預設，每次計算期間都會執行完整更新。 若要啟用部分更新，請選取選項並定義更新條件。

![](assets/update-aggregate-partial.png)

好的做法是新增 **[!UICONTROL Scheduler]** 活動以設定計算更新的頻率。
