---
title: Personalization資料來源
description: 瞭解哪些來源可用於個人化
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Personalization資料來源{#personalization-data}

Personalization資料可從各種型別的來源擷取：Campaign資料庫資料來源、外部檔案資料來源或外部資料庫資料來源。

## Campaign資料庫資料來源

在最常見的情況下，個人化資料會儲存在資料庫中。 例如，「收件者個人化欄位」是所有在收件者表格中定義的欄位、標準欄位（通常是：姓氏、名字、地址、城市、出生日期等）或自訂欄位。

![電子郵件中的行銷活動個人化欄位](assets/perso-campaign-datasource.png)


## 外部檔案資料來源

您可以使用包含欄中定義的所有欄位的外部檔案。 此檔案在訊息傳遞定義期間用作輸入。 您可以選擇是否在資料庫中插入這些設定檔。

若要選取要做為資料來源的檔案，請瀏覽至訊息建立視窗中的[收件者]連結，並選取&#x200B;**在外部檔案中定義**&#x200B;選項。 載入檔案後，從檔案&#x200B;**專案的**&#x200B;欄位存取個人化選項中的收件者資料。

![來自檔案的Personalization資料](assets/perso-from-file.png)


## FDA資料來源

可透過[同盟資料存取](../connect/fda.md)，從外部資料表提取Personalization資料。  如果您想使用外部資料庫中的資料在傳遞中執行個人化，請收集要在工作流程中使用的資料，以便在臨時表格中提供。

若要執行此動作，請在目標工作流程中新增&#x200B;**查詢**&#x200B;活動，並使用&#x200B;**新增資料……**&#x200B;連結來選取外部資料庫。 詳細程式可在[此區段](../../automation/workflow/query.md#adding-data)中取得。

然後，使用臨時表格中的資料來個人化您的傳遞。 設定查詢活動後，請從&#x200B;**Target擴充功能**&#x200B;專案存取個人化選項中的外部資料。

![來自外部資料庫的Personalization資料](assets/perso-external-db.png)

使用FDA中存取的外部資料時，建議使用&#x200B;**使用工作流程**&#x200B;選項準備個人化資料，在專屬工作流程中預先處理訊息個人化，如下所述。

### 最佳化個人化 {#optimize-personalization}

您可以使用專用的選項&#x200B;**[!UICONTROL Prepare the personalization data with a workflow]**&#x200B;來最佳化個人化，該選項可在傳遞屬性的&#x200B;**[!UICONTROL Analysis]**&#x200B;索引標籤中使用。

在傳遞分析期間，此選項會自動建立並執行工作流程，將所有連結至目標的資料儲存在臨時表格中，包括來自FDA連結表格的資料。

勾選此選項可大幅改善處理大量資料時的傳遞分析效能，尤其是當個人化資料來自透過FDA的外部表格時。 [了解更多](../connect/fda.md)。

若要使用此選項，請遵循下列步驟：

1. 建立行銷活動。
1. 在行銷活動的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;索引標籤中，新增&#x200B;**查詢**&#x200B;活動至您的工作流程。
1. 將&#x200B;**[!UICONTROL Email delivery]**&#x200B;活動新增至工作流程並開啟它。
1. 移至&#x200B;**[!UICONTROL Analysis]**&#x200B;的&#x200B;**[!UICONTROL Delivery properties]**&#x200B;標籤，並選取&#x200B;**[!UICONTROL Prepare the personalization data with a workflow]**&#x200B;選項。
1. 設定傳送並啟動工作流程以啟動分析。

分析完成後，個人化資料會透過分析期間即時建立的臨時技術工作流程，儲存在臨時表格中。

Adobe Campaign介面中看不到此工作流程。 其目的僅在於成為快速儲存和處理個人化資料的技術方法。

分析完成後，移至工作流程&#x200B;**[!UICONTROL Properties]**&#x200B;並選取&#x200B;**[!UICONTROL Variables]**&#x200B;標籤。 您可以在此看到可用來進行SQL呼叫以顯示其包含之ID的暫存表格名稱。

## 工作流程中的Personalization資料

在工作流程內容中建立傳遞時，您可以使用暫時工作流程表格中的資料。 儲存在工作流程臨時工作表中的資料可用於個人化任務。 資料可用於個人化欄位。

此資料會分組到&#x200B;**[!UICONTROL Target extension]**&#x200B;功能表中。 如需詳細資訊，請參閱[本節](../../automation/workflow/use-workflow-data.md#target-data)。
