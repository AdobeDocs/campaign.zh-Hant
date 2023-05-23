---
product: campaign
title: 使用多維資料集建立資料報告
description: 瞭解如何使用多維資料集建立報告
feature: Reporting
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 1%

---

# 使用 cubes 來探索資料{#use-cubes-to-create-reports}

使用多維資料集建立報告，並識別和選擇資料庫中的資料。 您可以：

* 基於立方建立報告。 [了解更多](#explore-the-data-in-a-report)。
* 收集資料庫中的資料並將其分組到清單中，例如識別和構建目標和交付。 [了解更多](#build-a-target-population)。
* 將透視表插入報表，引用報表中的現有多維資料集。 [了解更多](#insert-a-pivot-table-into-a-report)。

## 瀏覽報告中的資料 {#explore-the-data-in-a-report}

### 步驟1 — 基於多維資料集建立報告 {#step-1---create-a-report-based-on-a-cube}

一旦 [已配置多維資料集](cube-indicators.md)，可用作建立新報告的模板。

要基於現有立方建立報告，請執行以下步驟：

1. 按一下 **[!UICONTROL Create]** 按鈕 **[!UICONTROL Reports]** 頁籤，然後選擇您剛建立的多維資料集。

   ![](assets/new-report-based-on-cube.png)

1. 按一下 **[!UICONTROL Create]** 按鈕確認：這將帶您進入報告配置和查看頁面。

   預設情況下，前兩個可用維以行和列提供，但表中不顯示任何值。 要生成表，請按一下主表徵圖：

   ![](assets/cube-report-config.png)

1. 可以切換尺寸軸、刪除它們、添加新測量等。 為此，請使用相應的表徵圖。

   ![](assets/cube-switch-axis.png)

   這些操作詳見下文。

### 步驟2 — 選擇行和列 {#step-2---select-lines-and-columns}

預設顯示顯示立方的前兩個維（在本例中為年齡和城市）。

的 **[!UICONTROL Add]** 每個軸上的按鈕使您能夠添加尺寸。

![](assets/cube-switch.png)

1. 選擇要在表的行和列中顯示的尺寸。 為此，請拖放可用尺寸。
1. 從清單中選擇要添加到表的維：
   ![](assets/cube-select-dimension.png)

1. 然後選擇此尺寸的參數。

   ![](assets/cube-dimension-param.png)

   這些參數取決於所選維的資料類型。

   例如，對於日期，可以使用多個級別。 有關此內容的詳細資訊，請參閱 [顯示度量](customize-cubes.md#display-measures)。

   在這種情況下，可以使用以下選項：

   ![](assets/cube-config.png)

   您可以：

   * 載入期間展開資料：預設情況下，每次更新報告時，都會顯示值(預設值：不)。
   * 在行末顯示合計：在列中顯示資料時，附加選項允許您在行的末尾顯示合計：將列添加到表中(預設值：是)。
   * 應用排序：可以根據值、標籤或基於度量(預設值：按值)。
   * 按升序(a-z, 0-9)或降序(z-a, 9-0)順序顯示值。
   * 更改載入時要顯示的列數(預設情況下：200)。

1. 按一下 **[!UICONTROL Ok]** 確認：該維將添加到現有維。

   表上的黃色標語顯示您已進行更改：按一下 **[!UICONTROL Save]** 按鈕。

   ![](assets/cube-in-report.png)

### 步驟3 — 配置要顯示的測量 {#step-3---configure-the-measures-to-display}

定義行和列後，選擇要顯示的度量。 預設情況下，只顯示一個度量。

要添加和配置度量，請執行以下步驟：

1. 按一下 **[!UICONTROL Measures]** 按鈕。

   ![](assets/cube-measure-button.png)

1. 維特 **[!UICONTROL Use a measure]** 按鈕，選擇現有度量之一。

   ![](assets/cube-add-measure.png)

   選擇要顯示的資訊和格式選項。 選項清單取決於測量類型。

   ![](assets/cube-measure-options.png)

   通過 **[!UICONTROL Edit the configuration of the pivot table]** 的子菜單。

   ![](assets/cube-pivot-table-config.png)

   然後，可以選擇是否顯示度量標籤。 [了解更多](customize-cubes.md#configure-the-display)。

1. 可以基於現有度量構建新度量。 要執行此操作，請按一下 **[!UICONTROL Create a measure]** 並配置。

   ![](assets/cube-create-new-measure.png)

   可以使用以下類型的度量：

   * 措施組合：此類型的度量使您能夠使用現有度量構建新度量：

      可用運算子包括：和、差、乘法和速率。

   * 比例：此類型的度量使您能夠計算給定維的測量記錄數。 可以根據尺寸或子尺寸計算比例。
   * 變體：此度量允許您計算級別值的變化。
   * 標準差：此類型的度量允許您計算每組單元格中與值平均值相比的偏差。 例如，您可以比較所有現有段的採購量。

   建立後，該度量將添加到報表中。

   ![](assets/cube-display-new-measure.png)

   建立度量後，可以編輯它並更改其配置。 要執行此操作，請按一下 **[!UICONTROL Measures]** 按鈕，然後瀏覽到要編輯的度量的頁籤。

   然後按一下 **[!UICONTROL Edit the dynamic measure]** 的子菜單。

## 構建目標人口 {#build-a-target-population}

使用多維資料集生成報告使您能夠從表中收集資料並將其保存到清單中。

要將人口分組到清單中，請執行以下步驟：

1. 按一下包含要收集的填充的單元格以選擇它們，然後按一下 **[!UICONTROL Add to cart]** 表徵圖

   ![](assets/cube-add-to-cart.png)

   收集各種配置檔案時需要多次

1. 按一下 **[!UICONTROL Show cart]** 按鈕，在運行導出之前查看其內容。

   ![](assets/cube-show-cart.png)

1. 使用 **[!UICONTROL Export]** 按鈕，將購物車中的項目組合到清單中。

   輸入清單名稱，然後選擇要執行的導出類型。

   ![](assets/cube-export-report.png)

   按一下 **[!UICONTROL Start]** 以運行導出。

1. 導出完成後，將顯示一條消息確認其執行情況和已處理的記錄數。

   ![](assets/cube-export-confirm.png)

   您可以保存購物車的內容或將其清空。

   新清單可通過 **[!UICONTROL Profiles and targets]** 頁籤。

   ![](assets/cube-list-available.png)

## 將透視表插入報表 {#insert-a-pivot-table-into-a-report}

要建立表並瀏覽多維資料集中的資料，請執行以下步驟：

1. 使用單頁建立新報告，並將透視表插入其中。

   ![](assets/cube-insert-in-report.png)

1. 在 **[!UICONTROL Data]** 頁籤，選擇一個多維資料集以處理它包含的維並顯示計算度量。

   ![](assets/cube-selected-in-report.png)

   這允許您生成要顯示的報告。 有關此內容的詳細資訊，請參閱 [步驟2 — 選擇行和列](#step-2---select-lines-and-columns)。
