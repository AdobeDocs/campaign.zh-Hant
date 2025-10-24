---
title: 變更資料來源
description: 進一步瞭解變更資料來源活動
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 26829656f8e06434ca3207c0c7b62ba907765972
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# 變更資料來源 {#change-data-source}

使用&#x200B;**[!UICONTROL Change data source]**&#x200B;活動變更[工作流程工作表](use-workflow-data.md#workflow-temporary-work-table)的資料來源。 此活動可提供更大的彈性，用於管理不同資料來源(例如同盟資料存取(FDA)、Campaign Cloud資料庫(FFDA)和Campaign本機資料庫)的資料。

工作流程&#x200B;**[!UICONTROL Working table]**&#x200B;用於處理與工作流程活動共用資料。

根據預設，**[!UICONTROL Working table]**會建立在與您查詢所需資料來源相同的資料庫中。
例如，當查詢儲存在雲端資料庫上的**[!UICONTROL Recipients]**&#x200B;資料表時，工作流程會在相同的雲端資料庫上建立&#x200B;**[!UICONTROL Working table]**。

使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動以使用您&#x200B;**[!UICONTROL Working table]**&#x200B;的不同資料來源。

請注意，使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動時，您需要切換回雲端資料庫以繼續執行工作流程。

>[!IMPORTANT]
>
>請注意，不應將&#x200B;**[!UICONTROL Change Dimension]**&#x200B;和&#x200B;**[!UICONTROL Change Data source]**&#x200B;活動新增到一列。 如果您需要連續使用兩個活動，請務必在它們之間包含&#x200B;**[!UICONTROL Enrichement]**&#x200B;活動。 這可確保正確執行並防止潛在的衝突或錯誤。

>[!NOTE]
>
>**變更資料Source**&#x200B;活動最多可以在每次執行時處理一百萬筆記錄。 如果您需要提高此上限，請聯絡您的Adobe代表。

若要使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動，您必須：

1. 建立工作流程。

1. 查詢具有&#x200B;**[!UICONTROL Query]**&#x200B;活動的目標收件者。

   如需&#x200B;**[!UICONTROL Query]**&#x200B;活動的詳細資訊，請參閱此[頁面](query.md#create-a-query)。

1. 新增&#x200B;**[!UICONTROL Change data source]**&#x200B;活動。

   ![](assets/change-data-source.png)

1. 編輯您的&#x200B;**[!UICONTROL Change data source]**&#x200B;活動以選取&#x200B;**[!UICONTROL Default data source]**。

   接著會將包含查詢結果的工作表移至預設的Campaign本機資料庫。

   ![](assets/change-data-source_2.png)

1. 新增&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動以在工作表格上執行單一作業。

   如需&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動的詳細資訊，請參閱[此頁面](sql-code-and-javascript-code.md#javascript-code)。

1. 新增其他&#x200B;**[!UICONTROL Change data source]**&#x200B;活動以切換回雲端資料庫。

1. 編輯此活動並選取&#x200B;**[!UICONTROL Active FDA external account]**&#x200B;以及對應的&#x200B;**[!UICONTROL External database]**&#x200B;外部帳戶。

   ![](assets/change-data-source_3.png)

1. 您現在可以開始工作流程。
