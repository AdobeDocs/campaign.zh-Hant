---
title: 變更資料來源
description: 深入了解變更資料來源活動
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 變更資料來源 {#change-data-source}

使用 **[!UICONTROL Change data source]** 變更資料來源的活動 [工作流工作表](use-workflow-data.md#workflow-temporary-work-table). 此活動提供更大彈性，可跨不同資料來源管理資料，例如同盟資料存取(FDA)、Campaign雲端資料庫(FFDA)和Campaign本機資料庫。

工作流程 **[!UICONTROL Working table]** 可用來處理資料並與工作流程活動共用。

依預設， **[!UICONTROL Working table]** 會在您需要查詢之資料的來源所在的相同資料庫中建立。
例如，查詢 **[!UICONTROL Recipients]** 表格，儲存在雲端資料庫上，工作流程會建立 **[!UICONTROL Working table]** 在同一個雲端資料庫上。

使用 **[!UICONTROL Change Data Source]** 活動來為您的 **[!UICONTROL Working table]**.

請注意，使用 **[!UICONTROL Change Data Source]** 活動中，您需要切換回雲端資料庫以繼續執行工作流程。

若要使用 **[!UICONTROL Change Data Source]** 活動，您必須：

1. 建立工作流程.

1. 使用 **[!UICONTROL Query]** 活動。

   如需 **[!UICONTROL Query]** 活動，請參閱 [頁面](query.md#create-a-query).

1. 新增 **[!UICONTROL Change data source]** 活動。

   ![](assets/change-data-source.png)

1. 編輯 **[!UICONTROL Change data source]** 選擇活動 **[!UICONTROL Default data source]**.

   接著，包含查詢結果的工作表會移至預設的Campaign Local資料庫。

   ![](assets/change-data-source_2.png)

1. 新增 **[!UICONTROL JavaScript code]** 在工作表上執行統一操作的活動。

   如需 **[!UICONTROL JavaScript code]** 活動，請參閱 [本頁](sql-code-and-javascript-code.md#javascript-code).

1. 添加其他 **[!UICONTROL Change data source]** 切換回雲端資料庫的活動。

1. 編輯此活動並選取 **[!UICONTROL Active FDA external account]**，以及對應的 **[!UICONTROL External database]** 外部帳戶。

   ![](assets/change-data-source_3.png)

1. 您現在可以開始工作流程。
