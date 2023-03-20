---
title: 個人化資料來源
description: 了解可用於個人化的來源
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---


# 個人化資料來源{#personalization-data}

個人化資料可從各種來源類型中擷取：Campaign資料庫資料來源、外部檔案資料來源或外部資料庫資料來源。

## Campaign資料庫資料來源

在最常見的情況下，個人化資料會儲存在資料庫中。 例如，「收件者個人化欄位」是收件者表格、標準欄位中定義的所有欄位(通常：姓氏、名字、地址、城市、出生日期等) 或自訂欄位。

![電子郵件中的行銷活動個人化欄位](assets/perso-campaign-datasource.png)


## 外部檔案資料源

您可以使用包含欄中定義之所有欄位的外部檔案。 此檔案在消息傳遞定義期間用作輸入。 您可以選擇在資料庫中插入這些配置檔案。

要選擇要用作資料源的檔案，請瀏覽到消息建立窗口中的「要」連結，然後選擇 **在外部檔案中定義** 選項。 載入檔案後，從 **檔案中的欄位** 的下界。

![來自檔案的個人化資料](assets/perso-from-file.png)


## FDA資料來源

個人化資料可透過 [同盟資料存取](../connect/fda.md).  如果您想要使用外部資料庫的資料在傳送中進行個人化，請收集要在工作流程中使用的資料，以便在暫時表格中使用。

若要執行此動作，請新增 **查詢** 活動，並使用 **添加資料……** 連結以選取外部資料庫。 詳細程式可在 [本節](../../automation/workflow/query.md#adding-data).

然後使用臨時表格中的資料來個人化您的傳送。 設定查詢活動後，從 **Target擴充功能** 的下界。

![來自外部資料庫的個人化資料](assets/perso-external-db.png)

使用FDA中存取的外部資料時，建議使用 **使用工作流程準備個人化資料** 選項，如下所述。

### 最佳化個人化 {#optimize-personalization}

您可以使用專用選項來最佳化個人化： **[!UICONTROL Prepare the personalization data with a workflow]**，可在 **[!UICONTROL Analysis]** 標籤。

在傳遞分析期間，此選項會自動建立並執行工作流程，將連結至目標的所有資料儲存在臨時表格中，包括來自FDA中連結之表格的資料。

核取此選項可在處理大量資料時，尤其是當個人化資料來自外部表格（透過FDA）時，大幅改善傳送分析效能。 [了解更多資訊](../connect/fda.md)。

若要使用此選項，請遵循下列步驟：

1. 建立促銷活動.
1. 在 **[!UICONTROL Targeting and workflows]** 標籤，新增 **查詢** 活動。
1. 新增 **[!UICONTROL Email delivery]** 活動並開啟它。
1. 前往 **[!UICONTROL Analysis]** 的 **[!UICONTROL Delivery properties]** ，然後選取 **[!UICONTROL Prepare the personalization data with a workflow]** 選項。
1. 設定傳送並啟動工作流程以啟動分析。

分析完成後，個人化資料會透過分析期間即時建立的臨時技術工作流程儲存在臨時表格中。

此工作流程在Adobe Campaign介面中看不到。 這只是快速儲存及處理個人化資料的技術手段。

分析完成後，前往工作流程 **[!UICONTROL Properties]** ，然後選取 **[!UICONTROL Variables]** 標籤。 您可以在此處查看臨時表的名稱，該表可用於進行SQL調用，以顯示它包含的ID。

## 工作流程中的個人化資料

在工作流程內容中建立傳送時，您可以使用暫時工作流程表格中的資料。 儲存在工作流臨時工作表中的資料可用於個人化任務。 資料可用於個人化欄位。

此資料會分組於 **[!UICONTROL Target extension]** 功能表。 如需詳細資訊，請參閱[本章節](../../automation/workflow/use-workflow-data.md#target-data)。




