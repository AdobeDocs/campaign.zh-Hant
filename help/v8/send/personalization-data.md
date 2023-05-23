---
title: 個性化資料源
description: 瞭解哪些源可用於個性化
feature: Personalization
role: User
level: Beginner
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 個性化資料源{#personalization-data}

可以從各種類型的源中檢索個性化資料：市場活動資料庫資料源、外部檔案資料源或外部資料庫資料源。

## 市場活動資料庫資料源

在最常見的情況下，個性化資料儲存在資料庫中。 例如，「收件人個性化欄位」是「收件人」表中定義的所有欄位，即標準欄位(通常為：姓氏、名字、地址、城市、出生日期等) 或自定義域。

![電子郵件中的市場活動個性化欄位](assets/perso-campaign-datasource.png)


## 外部檔案資料源

可以使用包含列中定義的所有欄位的外部檔案。 此檔案在消息傳遞定義期間用作輸入。 可以選擇在資料庫中插入這些配置檔案。

要選擇要用作資料源的檔案，請瀏覽到消息建立窗口中的「收件人」連結，然後選擇 **在外部檔案中定義** 的雙曲餘切值。 載入檔案後，從 **檔案中的欄位** 的子菜單。

![檔案中的個性化資料](assets/perso-from-file.png)


## FDA資料源

可從外部表中通過 [聯合資料存取](../connect/fda.md)。  如果您希望使用外部資料庫中的資料在交貨中執行個性化設定，請收集要在工作流中使用的資料，使其在臨時表中可用。

要執行此操作，請添加 **查詢** 目標工作流中的活動，並使用 **添加資料……** 連結以選擇外部資料庫。 詳細過程可在 [此部分](../../automation/workflow/query.md#adding-data)。

然後使用臨時表中的資料來個性化您的交付。 配置查詢活動後，從 **目標擴展** 的子菜單。

![來自外部資料庫的個性化資料](assets/perso-external-db.png)

當使用在FDA中訪問的外部資料時，建議使用 **使用工作流準備個性化資料** 選項。

### 優化個性化 {#optimize-personalization}

可以使用專用選項優化個性化： **[!UICONTROL Prepare the personalization data with a workflow]**，在 **[!UICONTROL Analysis]** 的子菜單。

在傳遞分析期間，此選項會自動建立並執行一個工作流，該工作流將連結到目標的所有資料儲存在臨時表中，包括FDA連結的表中的資料。

選中此選項可在處理大量資料時大大提高交付分析效能，特別是當個性化資料通過FDA從外部表格來時。 [了解更多](../connect/fda.md)。

要使用此選項，請執行以下步驟：

1. 建立促銷活動.
1. 在 **[!UICONTROL Targeting and workflows]** 頁籤，添加 **查詢** 活動。
1. 添加 **[!UICONTROL Email delivery]** 活動並將其開啟。
1. 轉到 **[!UICONTROL Analysis]** 頁籤 **[!UICONTROL Delivery properties]** 的 **[!UICONTROL Prepare the personalization data with a workflow]** 的雙曲餘切值。
1. 配置交付並啟動工作流以啟動分析。

分析完成後，個性化資料通過分析期間即時建立的臨時技術工作流儲存在臨時表中。

此工作流在Adobe Campaign介面中不可見。 它只是一種技術手段來快速儲存和處理個性化資料。

分析完成後，轉到工作流 **[!UICONTROL Properties]** 的 **[!UICONTROL Variables]** 頁籤。 在此，您可以看到用於進行SQL調用以顯示其包含的ID的臨時表的名稱。

## 工作流中的個性化資料

在工作流上下文中建立交貨時，可以使用臨時工作流表中的資料。 儲存在工作流臨時工作表中的資料可用於個性化任務。 資料可以在個性化欄位中使用。

此資料將分組到 **[!UICONTROL Target extension]** 的子菜單。 如需詳細資訊，請參閱[本章節](../../automation/workflow/use-workflow-data.md#target-data)。
