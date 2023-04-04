---
product: campaign
title: 更新彙總
description: 深入了解更新匯總工作流程活動
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

中定義的匯總 [立方體](../../v8/reporting/gs-cubes.md) 可更新特定活動以用於報告用途。 A **[!UICONTROL Workflow]** 標籤。

進一步了解中的立方體和匯總 [本節](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

若要更新匯總，請編輯 **[!UICONTROL Update aggregate]** 活動，然後選取要更新的多維資料集和匯總。

您可以設定 **完整更新** 或 **部分更新**.

![](assets/update-aggregate-details.png)

預設情況下，每次計算期間都會執行完整更新。 要啟用部分更新，請選擇選項並定義更新條件。

![](assets/update-aggregate-partial.png)

最佳作法是新增 **[!UICONTROL Scheduler]** 設定計算更新頻率的活動。
