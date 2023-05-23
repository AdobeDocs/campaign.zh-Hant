---
title: 變更資料來源
description: 瞭解有關更改資料源活動的詳細資訊
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 變更資料來源 {#change-data-source}

使用 **[!UICONTROL Change data source]** 更改資料源的活動 [工作流工作表](use-workflow-data.md#workflow-temporary-work-table)。 本練習為跨不同資料源(如聯合資料存取(FDA)、活動雲資料庫(FFDA)和活動本地資料庫)管理資料提供了更大的靈活性。

工作流 **[!UICONTROL Working table]** 用於處理和共用與工作流活動的資料。

預設情況下， **[!UICONTROL Working table]** 建立的資料庫與要查詢的資料的源資料庫相同。
例如，查詢 **[!UICONTROL Recipients]** 表，儲存在雲資料庫上，工作流將建立 **[!UICONTROL Working table]** 在同一雲資料庫上。

使用 **[!UICONTROL Change Data Source]** 活動：為 **[!UICONTROL Working table]**。

請注意，當使用 **[!UICONTROL Change Data Source]** 活動，您需要切換回雲資料庫以繼續執行工作流。

使用 **[!UICONTROL Change Data Source]** 活動：

1. 建立工作流程.

1. 使用 **[!UICONTROL Query]** 的子菜單。

   有關 **[!UICONTROL Query]** 活動，請參閱 [頁](query.md#create-a-query)。

1. 添加 **[!UICONTROL Change data source]** 的子菜單。

   ![](assets/change-data-source.png)

1. 編輯 **[!UICONTROL Change data source]** 活動，選擇 **[!UICONTROL Default data source]**。

   包含查詢結果的工作表隨後將移到預設的市場活動本地資料庫。

   ![](assets/change-data-source_2.png)

1. 添加 **[!UICONTROL JavaScript code]** 活動，以在工作表上執行單一操作。

   有關 **[!UICONTROL JavaScript code]** 活動，請參閱 [此頁](sql-code-and-javascript-code.md#javascript-code)。

1. 添加其他 **[!UICONTROL Change data source]** 活動以切換回雲資料庫。

1. 編輯此活動並選擇 **[!UICONTROL Active FDA external account]**，以及相應 **[!UICONTROL External database]** 外部帳戶。

   ![](assets/change-data-source_3.png)

1. 現在可以啟動工作流。
