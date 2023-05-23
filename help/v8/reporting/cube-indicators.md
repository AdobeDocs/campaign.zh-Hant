---
title: 在Adobe Campaign建立立方
description: 瞭解如何建立立方
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: 03a6816b-e51a-4eaf-ab76-02d24f97ba46
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 3%

---

# 建立多維度資料集{#create-a-cube}

## 多維資料集工作區 {#cube-workspace}

要訪問多維資料集，請瀏覽到 **[!UICONTROL Administration > Configuration > Cubes]** 從市場活動瀏覽器。

![](assets/cube-node.png)

使用立方，您可以：

* 直接在報告中導出資料， **[!UICONTROL Reports]** 頁籤。

   為此，請建立新報告並選擇要使用的多維資料集。

   ![](assets/create-new-cube.png)

   立方顯示為基於其建立報告的模板。 選擇模板後，按一下 **[!UICONTROL Create]** 以配置和查看新報告。

   您可以調整測量、更改顯示模式或配置表，然後使用主按鈕顯示報告。

   ![](assets/display-cube-table.png)

* 引用中的立方 **[!UICONTROL Query]** 報告框，以使用其指標，如下所示：

   ![](assets/cube-report-query.png)

* 將基於多維資料集的透視表插入報表的任何頁。 為此，請引用要在 **[!UICONTROL Data]** 對話框。

   ![](assets/cube-in-a-report.png)

   有關此內容的詳細資訊，請參閱 [瀏覽報告中的資料](cube-tables.md#explore-the-data-in-a-report)。


>[!CAUTION]
>
>建立多維資料集需要管理員權限。

## 生成多維資料集{#cube-create}

在開始生成立方報表之前，請確定相關的維和度量，然後在立方中建立它們。

要建立立方，請應用以下步驟：

1. 選擇工作表。 [了解更多](#select-the-work-table)。
1. 定義尺寸。 [了解更多](#define-dimensions)。
1. 定義度量。 [了解更多](#build-indicators)。
1. 建立聚合（可選）。 [了解更多](customize-cubes.md#calculate-and-use-aggregates)。

在下面的示例中，瞭解如何快速在報告中建立一個簡單的多維資料集以導出其度量。

### 選擇工作表 {#select-the-work-table}

要建立立方，請執行以下步驟：

1. 按一下 **[!UICONTROL New]** 按鈕。

   ![](assets/create-a-cube.png)

1. 選擇包含要瀏覽的元素的架構（也稱為「事實架構」）。 在此示例中，選擇 **收件人** 的子菜單。
1. 按一下 **[!UICONTROL Save]** 要建立多維資料集：它被添加到立方清單中。 現在，您可以使用頁籤來配置它。

1. 按一下 **[!UICONTROL Filter the source data...]** 連結，將此多維資料集的計算應用到資料庫中的資料。

   ![](assets/cube-filter-source.png)

### 定義尺寸 {#define-dimensions}

建立立方後，定義其維。 Dimension是根據每個多維資料集的相關事實模式為它們定義的分析軸。 這些是分析中探討的維度，如時間（年、月、日）、產品或合同的分類（家庭、參考等）、人口部分（按城市、年齡組、狀態等）。

要建立尺寸，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Dimension]** 頁籤，然後按一下 **[!UICONTROL Add]** 按鈕
1. 在 **[!UICONTROL Expression field]**，按一下 **[!UICONTROL Edit expression]** 表徵圖以選擇包含相關資料的欄位。

   ![](assets/cube-add-dimension.png)

1. 在此示例中，我們選擇收件人 **年齡**。 對於此欄位，您可以定義組合以分組年齡，並使資訊讀取更容易。 建議在可能存在多個單獨值時使用綁定。

要執行此操作，請檢查 **[!UICONTROL Enable binning]** 的雙曲餘切值。 [了解更多](customize-cubes.md#data-binning)。

1. 添加 **日期** 類型維。 在此，我們要顯示收件人配置檔案建立日期。 要執行此操作，請按一下 **[!UICONTROL Add]** 的 **[!UICONTROL Creation date]** 的子菜單。
可以自定義日期顯示模式。 為此，請選擇要使用的層次和要生成的級別：

![](assets/cube-date-dimension.png)

在我們的例子中，我們只想顯示年、月和日。 請注意，您不能同時處理周和學期/月：這些級別不相容。

1. 建立另一個維以分析與收件人所在城市相關的資料。 要執行此操作，請添加新維，然後在 **[!UICONTROL Location]** 收件人架構的節點。

您可以啟用綁定，使資訊讀取更容易，並將值連結到枚舉。

從下拉清單中選擇枚舉。 請注意，此枚舉必須定義為 **[!UICONTROL Reserved for binning]**。

![](assets/cube-dimension-with-enum.png)

只顯示枚舉中的值。 其它組將分組到 **[!UICONTROL Label of the other values]** 的子菜單。

如需詳細資訊，請參閱[本章節](customize-cubes.md#dynamically-manage-bins)。

### 建立指標 {#build-indicators}

定義維後，為要在單元格中顯示的值指定計算模式。

為此，請在 **[!UICONTROL Measures]** 頁籤。 根據此多維資料集建立報表中要顯示的列的數量。

要構建指標，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Measures]** ，然後按一下 **[!UICONTROL Add]** 按鈕
1. 選擇要應用的度量類型和公式。 在本例中，我們計算受助者中婦女的數量。 我們的度量基於事實模式並使用 **[!UICONTROL Count]** 運算子。

   ![](assets/cube-new-measure.png)

   使用 **[!UICONTROL Filter the measure data...]** 連結以僅選擇女性。 [了解更多](customize-cubes.md#define-measures)。

   ![](assets/cube-filter-measure-data.png)

1. 輸入度量的標籤並保存。

   ![](assets/cube-save-measure.png)

1. 保存多維資料集。


現在，您可以基於此多維資料集建立報告。 [了解更多](cube-tables.md)。
