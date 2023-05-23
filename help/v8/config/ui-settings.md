---
title: 市場活動介面設定
description: 瞭解如何自定義市場活動介面設定
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
exl-id: fefb6d80-c3d1-448b-82ab-648da58a0ba4
source-git-commit: 666dbdac8330cae17693142cf45cc3d3d2d187a9
workflow-type: tm+mt
source-wordcount: '1845'
ht-degree: 23%

---

# 市場活動用戶介面設定 {#ui-settings}

## 預設單位 {#default-units}

在Adobe Campaign，對於表示持續時間的欄位（例如資源的有效期、任務的批准期限等），值可以以下方式表示 **單位**:

* **[!UICONTROL s]** 秒
* **[!UICONTROL mn]** 幾分鐘
* **[!UICONTROL h]** 數小時
* **[!UICONTROL d]** 天

## 自定義市場活動瀏覽器{#customize-explorer}

您可以將資料夾添加到市場活動瀏覽器、建立視圖和分配權限。

瞭解如何管理中的資料夾和視圖 [此頁](../audiences/folders-and-views.md)

## 管理和自定義清單{#customize-lists}

在市場活動客戶端控制台中，資料顯示在清單中。 您可以根據需要調整這些清單。 例如，您可以添加列、篩選資料、計數記錄、保存和共用設定。

此外，還可以建立和保存篩選器。  瞭解有關中篩選器的詳細資訊 [此頁](../audiences/create-filters.md)。

### 記錄數 {#number-of-records}

根據預設，Adobe Campaign 會載入清單中的前 200 條記錄。這意味著將不一定顯示您正在檢視之表格中的所有記錄。您可以統計清單中的記錄計數，並載入更多記錄。

在清單畫面右下角，**counter** 會顯示已載入的記錄數，以及資料庫中的記錄總數 (套用任何篩選器之後)：

![顯示清單中的記錄總數](assets/number-of-records.png)

如果出現問號而不是右邊的數字，例如 `240/?`，按一下計數器啟動計算。

要載入和顯示其他記錄，請按一下 **[!UICONTROL Continue loading]**。 預設情況下，載入200條記錄。 要更改要載入的預設記錄數，請使用 **[!UICONTROL Configure list]** 表徵圖。 在清單配置窗口中，按一下 **[!UICONTROL Advanced parameters]** （左下）並更改要檢索的行數。

若要載入所有記錄，請以滑鼠右鍵按一下清單，然後選取 **[!UICONTROL Load all]**。

>[!CAUTION]
>
>當清單包含大量記錄時，完全載入可能需要一些時間。

### 添加和刪除列 {#add-columns}

對於每個清單，內置列配置可適於顯示更多資訊或隱藏未使用的列。

當記錄的詳細資訊中顯示資料時，按一下右鍵該欄位並選擇 **[!UICONTROL Add in the list]**。

![在清單中添加欄位](assets/add-in-the-list.png)

該欄會新增至現有欄的右邊。

![添加欄位列](assets/add-a-column.png)

也可以使用清單配置螢幕添加和刪除列：

1. 在記錄清單中，按一下 **[!UICONTROL Configure list]** 表徵圖。
1. 按兩下要添加到 **[!UICONTROL Available fields]** 清單：它們被添加到 **[!UICONTROL Output columns]** 清單框。

   ![清單配置螢幕](assets/list-config-screen.png)


   >[!NOTE]
   >
   >預設情況下，不會顯示進階欄位。要顯示它們，請按一下 **顯示高級欄位** 表徵圖。
   >
   >欄位採用特定圖示加以標識：SQL 欄位、連結的資料表、計算欄位等。可用欄位的清單下將顯示所選取的每個欄位的說明。

1. 使用上/下箭頭修改 **顯示順序**。

1. 按一下 **[!UICONTROL OK]** 確認設定並顯示結果。

如果需要刪除列，請選擇該列並按一下 **垃圾** 表徵圖

您可以使用 **[!UICONTROL Distribution of values]** 表徵圖，查看當前資料夾中選定欄位的值的重新分區。

![](assets/value-distribution.png)


### 新建欄 {#create-a-new-column}

您可以建立新的欄來顯示清單中的其他欄位。

要建立列，請執行以下步驟：

1. 在記錄清單中，按一下 **[!UICONTROL Configure list]** 表徵圖。
1. 按一下 **[!UICONTROL Add]** 表徵圖以在清單中顯示新欄位。
1. 配置要添加到列中的欄位。


### 在子資料夾中顯示資料 {#display-sub-folders-records}

清單可顯示：

* 所選資料夾中包含的所有記錄（預設）
* 所選資料夾及其子資料夾中包含的所有記錄

要從一個顯示模式切換到另一個顯示模式，請按一下 **[!UICONTROL Display sub-levels]** 的子菜單。

### 保存清單配置 {#saving-a-list-configuration}

清單配置是為每個用戶本地定義的。 清除本機快取時，會停用本機設定。

預設情況下，設定參數應用於具有相應資料夾類型的所有清單。 修改從資料夾顯示收件人清單的方式時，此配置將應用於所有其他收件人資料夾。

可以保存多個要應用於相同類型的不同資料夾的配置。 該設定會隨包含資料的資料夾屬性一起儲存，並可重新套用。

要保存清單配置以便可以重新使用，請執行以下步驟：

1. 在瀏覽器中，按一下右鍵包含顯示資料的資料夾。
1. 選取 **[!UICONTROL Properties]**。
1. 按一下 **[!UICONTROL Advanced settings]** 然後在 **[!UICONTROL Configuration]** 的子菜單。
1. 按一下 **[!UICONTROL OK]** 然後按一下 **[!UICONTROL Save]**。

然後，可以應用此配置任何其他同類型的資料夾。 瞭解有關中資料夾的詳細資訊 [此頁](../audiences/folders-and-views.md)。

### 導出清單 {#exporting-a-list}

若要匯出清單資料，您必須使用匯出精靈。若要使用此精靈，請從清單選取要匯出的元素，以滑鼠右鍵按一下後選取 **[!UICONTROL Export...]**。

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>不可使用 [複製/貼上] 功能匯出清單中的元素。

### 排序清單 {#sorting-a-list}

清單中可包含大量資料。您可以對這些資料進行排序或套用簡單、進階篩選器。透過排序，您設定以遞增或遞減順序顯示資料。透過篩選，您可以定義和合併準則以僅顯示所選資料。

按一下欄標題，套用遞增或遞減排序，或是取消資料排序。作用中的排序狀態和排序順序會在欄標籤前方以藍色箭頭表示。欄位標籤前方的紅色破折號表示該排序已套用至資料庫中索引的資料。此排序方法用於最佳化排序工作。

您也可以設定排序或合併排序準則。要執行此操作，請遵循下列步驟：

1. **[!UICONTROL Configure list]** 清單右側。
1. 在清單設定視窗中，按一下 **[!UICONTROL Sorting]** 索引標籤。
1. 選取要排序的欄位以及排序方向 (遞增或遞減)。
1. 排序優先順序透過排序欄的順序定義。若要變更優先順序，請使用適當的圖示來變更欄的順序。

   排序優先順序不會影響清單中欄的顯示情況。

1. 按一下 **[!UICONTROL Ok]** 確認此設定，並在清單中呈現結果。




## 使用枚舉 {#enumerations}

枚舉（也稱為「明細清單」）是系統建議填充欄位的值清單。 使用枚舉來標準化這些欄位的值，幫助輸入資料或在查詢中使用資料。

值清單將作為下拉清單顯示，您可以從中選擇要在欄位中輸入的值。 下拉清單還啟用預測輸入：輸入第一個字母，應用程式將填入其餘字母。

定義此類型欄位的值，並通過 **[!UICONTROL Administration > Platform > Enumerations]** 的子目標。

![訪問枚舉](assets/enumerations-menu.png)

### 枚舉類型 {#types-of-enum}

枚舉儲存在 **[!UICONTROL Administration > Platform > Enumerations]** 資料夾。

它們可以是：開啟、系統、表情或關閉。

* 安 **開啟** 枚舉允許用戶基於此枚舉直接在欄位中添加新值。
* A **已關閉** 枚舉具有固定值清單，只能從 **[!UICONTROL Administration > Platform > Enumerations]** 資料夾。
* 安 **表情** 枚舉用於更新emoticon清單。 了解更多
* A **系統** 枚舉與系統欄位關聯，並帶有內部名稱。

對於 **開啟** 和 **已關閉** 枚舉，可使用特定選項：

* **簡單枚舉** 為預設標準類型。
* **別名清除** 枚舉用於協調儲存在資料庫中的枚舉值。 [了解更多](#alias-cleansing)
* **保留用於綁定** 是一個選項，允許您將多維資料集值連結到此枚舉。 [了解更多](../reporting/gs-cubes.md)


### 別名清除 {#alias-cleansing}

在枚舉欄位中，可以選擇一個值，或輸入一個在下拉清單中不可用的自定義值。 可將自定義值作為新值添加到現有枚舉值中。 **[!UICONTROL Open]** 選項。 可以使用別名清除功能清除這些自定義值。 例如，如果用戶輸入 `Adob` 而不是 `Adobe`，別名清除過程可以自動用正確的術語替換。

>[!CAUTION]
>
>資料清理是影響資料庫中資料的關鍵過程。 Adobe Campaign進行大量資料更新，這可能導致某些值被刪除。 因此，此操作保留給專家用戶。

啟用 **[!UICONTROL Alias cleansing]** 選項，用於為枚舉使用資料清除功能。 選中此選項時， **[!UICONTROL Alias]** 頁籤。

當用戶輸入別名清除枚舉中不存在的值時，會將其添加到 **值** 清單框。 你可以 [從這些值建立別名](#convert-to-alias)或 [從頭開始建立新別名](#create-alias)。

#### 建立別名{#create-alias}

要建立別名，請執行以下步驟：

1. 按一下 **[!UICONTROL Add]** 按鈕 **[!UICONTROL Alias]** 頁籤。
1. 輸入要轉換的別名，然後在下拉清單中選擇要應用的值。

   ![建立新別名](assets/new-alias.png)

1. 按一下 **[!UICONTROL Ok]** 確認一下。

1. 儲存您的變更。值的替換由 **別名清除** 工作流，每晚執行。 請參閱 [運行資料清理](#running-data-cleansing)。

對於基於此枚舉的所有欄位，當用戶輸入值時 **阿多布** 在「company」欄位(在Adobe Campaign控制台中，在web窗體中)中，將自動替換為值 **Adobe**。

#### 將錯誤值轉換為別名{#convert-to-alias}

也可以將現有枚舉值轉換為別名。 要執行此操作，請執行以下操作：

1. 在枚舉值清單中，按一下右鍵並瀏覽到 **[!UICONTROL Actions... > Convert values into aliases...]**。

   ![將值轉換為別名](assets/convert-into-aliases.png)

1. 選擇要以別名轉換的值，然後按一下 **[!UICONTROL Next]**。
1. 按一下 **[!UICONTROL Start]** 的子菜單。

   執行完成後，別名將添加到清單中 **別名** 頁籤。 您可以關聯正確的值以替換錯誤的條目。 要執行此操作，請執行以下操作：

1. 選擇要清除的值。
1. 按一下 **細節……** 按鈕
1. 在下拉清單中選擇新值。

   ![建立新別名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以跟蹤 **[!UICONTROL Hits]** 列 **[!UICONTROL Alias]** 的子菜單。 它可以顯示輸入此值的次數。  [了解更多](#calculate-entry-occurrences)。

#### 運行資料清理 {#running-data-cleansing}

資料清理由 **[!UICONTROL Alias cleansing]** 技術工作流。 預設情況下，它每天執行。

清洗也可以通過 **[!UICONTROL Cleanse values...]** 的子菜單。

的 **[!UICONTROL Advanced parameters...]** 連結用於設定將收集的值從其開始計算的日期。

按一下 **[!UICONTROL Start]** 按鈕以運行資料清除。

##### 監視事件 {#calculate-entry-occurrences}

的 **[!UICONTROL Alias]** 枚舉的子頁籤可以顯示在輸入的所有值中別名的出現次數。 此資訊是估計值，將顯示在 **[!UICONTROL Hits]** 的雙曲餘切值。

>[!CAUTION]
>
>計算別名條目出現可能需要很長時間。

您可以通過 **[!UICONTROL Cleanse values...]** 的子菜單。 要執行此操作，請按一下 **[!UICONTROL Advanced parameters...]** 連結並選擇選項。

* **[!UICONTROL Update the number of alias hits]**:這允許您根據輸入的日期更新已計算的命中數。
* **[!UICONTROL Recalculate the number of alias hits from the start]**:讓你在整個Adobe Campaign平台上運行計算。

您還可以建立專用工作流，以便計算在給定期間自動運行，例如每週運行一次。

為此，請建立 **[!UICONTROL Alias cleansing]** 工作流，更改計畫程式，並在 **[!UICONTROL Enumeration value cleansing]** 活動：

* **-updateHits** 更新別名命中數，
* **-updateHits：完整** 重新計算所有別名命中。
