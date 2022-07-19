---
product: campaign
title: 更新彙總
description: 瞭解有關更新聚合工作流活動的詳細資訊
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---

# 更新彙總{#update-aggregate}

聚合在多維資料集級別定義以用於報告目的。 A **[!UICONTROL Workflow]** 頁籤在配置聚合時可用。

有關在Adobe Campaign使用立方和聚合的詳細資訊，請參閱 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}。


要更新聚合，請編輯 **[!UICONTROL Update aggregate]** 活動，然後選擇要更新的多維資料集和聚合。

您可以執行 **完整更新** 或&#x200B;**部分更新**。

預設情況下，在每次計算期間執行完整更新。 要啟用部分更新，請選擇相關選項並定義更新條件。

**良好做法**:a **[!UICONTROL Scheduler]** 活動可用於指定計算更新的頻率。

![](assets/scheduler-and-cube-aggregate.png)
