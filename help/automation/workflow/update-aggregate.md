---
product: campaign
title: 更新彙總
description: 深入瞭解更新彙總工作流程活動
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: 'https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%
---
# 更新彙總{#update-aggregate}

[多維度資料集](../../v8/reporting/gs-cubes.md)中定義用於報告的彙總可隨特定活動更新。 設定彙總時可使用&#x200B;**[!UICONTROL Workflow]**&#x200B;標籤。

在[本節](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates)中進一步瞭解多維度資料集與彙總。

若要更新彙總，請編輯&#x200B;**[!UICONTROL Update aggregate]**&#x200B;活動並選取要更新的Cube和彙總。

您可以設定&#x200B;**完整更新**&#x200B;或&#x200B;**部分更新**。

![](assets/update-aggregate-details.png)

依預設，每次計算期間都會執行完整更新。 若要啟用部分更新，請選取選項並定義更新條件。

![](assets/update-aggregate-partial.png)

良好的作法是新增&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動以設定計算更新的頻率。
