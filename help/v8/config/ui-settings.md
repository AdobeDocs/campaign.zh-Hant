---
title: Campaign介面設定
description: 瞭解如何自訂Campaign介面設定
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 12%

---

# Campaign使用者介面設定 {#ui-settings}

## 預設單位 {#default-units}

在Adobe Campaign中，對於表示持續時間的欄位（例如資源的有效期間、任務的核准截止日期等），值可以表示為以下&#x200B;**個單位**：

* **[!UICONTROL s]**&#x200B;秒
* **[!UICONTROL mn]**&#x200B;分鐘
* **[!UICONTROL h]**&#x200B;代表小時
* **[!UICONTROL d]**&#x200B;天

## 自訂Campaign Explorer{#customize-explorer}

您可以將資料夾新增至Campaign Explorer、建立檢視及指派許可權。

瞭解如何在[此頁面](../audiences/folders-and-views.md)中管理資料夾和檢視

## 管理和自訂清單{#customize-lists}

在Campaign使用者端主控台中，資料會顯示在清單中。 您可以根據自己的需求調整這些清單。 例如，您可以新增欄、篩選資料、計算記錄、儲存和共用您的設定。

此外，您可以建立和儲存篩選器。  在[此頁面](../audiences/create-filters.md)中進一步瞭解篩選器。

### 記錄數 {#number-of-records}

依預設，Adobe Campaign會載入清單的前200筆記錄。 這表示顯示不一定會顯示您所檢視之表格的所有記錄。 您可以統計清單中的記錄計數，並載入更多記錄。

在清單畫面右下角，**counter** 會顯示已載入的記錄數，以及資料庫中的記錄總數 (套用任何篩選器之後)：

![顯示清單中的記錄總數](assets/number-of-records.png)

如果出現問號而非右側的數字，例如`240/?`，請按一下計數器以啟動計算。

若要載入並顯示其他記錄，請按一下&#x200B;**[!UICONTROL Continue loading]**。 預設會載入200筆記錄。 若要變更要載入的預設記錄數，請使用清單右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;圖示。 在清單設定視窗中，按一下&#x200B;**[!UICONTROL Advanced parameters]** （左下方）並變更要擷取的行數。

若要載入所有記錄，請在清單上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL Load all]**。

>[!CAUTION]
>
>當清單包含大量記錄時，完整載入可能需要一些時間。
>

### 新增和移除欄 {#add-columns}

對於每個清單，內建欄配置可以調整為顯示更多資訊或隱藏未使用的欄。

當資料顯示在記錄的詳細資訊中時，用滑鼠右鍵按一下該欄位並選取&#x200B;**[!UICONTROL Add in the list]**。

![在清單中新增欄位](assets/add-in-the-list.png)

該欄會新增至現有欄的右邊。

![新增欄位資料行](assets/add-a-column.png)

您也可以使用清單設定畫面來新增及移除欄：

1. 從記錄清單中，按一下右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;圖示。
1. 連按兩下要新增至&#x200B;**[!UICONTROL Available fields]**&#x200B;清單中的欄位：它們已新增至&#x200B;**[!UICONTROL Output columns]**&#x200B;清單。

   ![清單設定畫面](assets/list-config-screen.png)


   >[!NOTE]
   >
   >依預設，不會顯示進階欄位。 若要顯示它們，請按一下可用欄位清單右下角的&#x200B;**顯示進階欄位**&#x200B;圖示。
   >
   >欄位採用特定圖示加以標識：SQL 欄位、連結的資料表、計算欄位等。可用欄位的清單下將顯示所選取的每個欄位的說明。
   >

1. 使用上/下箭頭來修改&#x200B;**顯示順序**。

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以確認設定並顯示結果。

如果您需要移除欄，請選取該欄，然後按一下&#x200B;**垃圾桶**&#x200B;圖示。

您可以使用&#x200B;**[!UICONTROL Distribution of values]**&#x200B;圖示來檢視目前資料夾中所選欄位的重新分割值。

![](assets/value-distribution.png)


### 新建欄 {#create-a-new-column}

您可以建立新的欄來顯示清單中的其他欄位。

若要建立欄，請執行下列步驟：

1. 從記錄清單中，按一下右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;圖示。
1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;圖示以在清單中顯示新欄位。
1. 設定欄位以新增到欄中。


### 在子資料夾中顯示資料 {#display-sub-folders-records}

清單可顯示：

* 所選資料夾中包含的所有記錄（預設）
* 所選資料夾及其子資料夾中包含的所有記錄

若要從一種顯示模式切換到另一種顯示模式，請按一下[促銷活動]工具列中的&#x200B;**[!UICONTROL Display sub-levels]**。

### 儲存清單設定 {#saving-a-list-configuration}

清單設定是在本機為每個使用者定義的。 清除本機快取時，會停用本機設定。

依預設，設定引數會套用至具有對應資料夾型別的所有清單。 當您修改從資料夾顯示收件者清單的方式時，此設定會套用至所有其他收件者資料夾。

您可以儲存多個要套用至相同型別之不同資料夾的設定。 該設定會隨包含資料的資料夾屬性一起儲存，並可重新套用。

若要儲存清單設定以便重複使用，請遵循下列步驟：

1. 在Explorer中，以滑鼠右鍵按一下包含所顯示資料的資料夾。
1. 選取 **[!UICONTROL Properties]**。
1. 按一下&#x200B;**[!UICONTROL Advanced settings]**，然後在&#x200B;**[!UICONTROL Configuration]**&#x200B;欄位中指定名稱。
1. 按一下&#x200B;**[!UICONTROL OK]**，然後按一下&#x200B;**[!UICONTROL Save]**。

然後，您可以將此設定套用至相同型別的任何其他資料夾。 在[此頁面](../audiences/folders-and-views.md)中進一步瞭解資料夾。

### 匯出清單 {#exporting-a-list}

若要從清單匯出資料，您必須使用匯出精靈。 若要存取，請從清單中選取要匯出的元素，按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Export...]**。

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>不可使用 [複製/貼上] 功能匯出清單中的元素。

### 排序清單 {#sorting-a-list}

清單可能包含大量資料。 您可以排序這些資料，或套用簡單或進階篩選器。 排序可讓您以遞增或遞減順序顯示資料。 透過篩選，您可以定義和合併準則以僅顯示所選資料。

按一下欄標題可套用遞增或遞減排序，或取消資料排序。 在欄標籤前，使用中的排序狀態和排序順序會以藍色箭頭表示。 欄標籤前面的紅色虛線表示排序套用至從資料庫編制索引的資料。 此排序方法用於最佳化排序工作。

您也可以設定排序或組合排序條件。 要執行此操作，請遵循下列步驟：

1. 清單右下方的&#x200B;**[!UICONTROL Configure list]**。
1. 在清單組態視窗中，按一下&#x200B;**[!UICONTROL Sorting]**&#x200B;標籤。
1. 選取要排序的欄位以及排序方向 (遞增或遞減)。
1. 排序優先順序由排序欄的順序定義。 若要變更優先順序，請使用適當的圖示來變更欄的順序。

   排序優先順序不會影響清單中欄的顯示情況。

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;以確認此設定，並在清單中顯示結果。




## 使用分項清單 {#enumerations}

分項清單（也稱為「分項清單」）是系統建議用來填入欄位的值清單。 使用列舉來標準化這些欄位的值，有助於資料輸入或在查詢中使用。

值清單會以下拉式清單的形式顯示，您可以從中選取要在欄位中輸入的值。 下拉式清單也會啟用預測性輸入：輸入第一個字母，應用程式會填入其餘字母。

此型別欄位的值已定義，這些欄位的整體管理（新增/刪除值）是透過樹狀結構的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;節點執行的。

![存取分項清單](assets/enumerations-menu.png)

### 分項清單的型別 {#types-of-enum}

列舉儲存在檔案總管的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;資料夾中。

它們可以是：開放、系統、表情符號或關閉。

* **Open**&#x200B;列舉允許使用者根據此列舉直接在欄位中新增值。
* **已關閉的**&#x200B;列舉具有只能從總管的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;資料夾修改的固定值清單。
* 使用&#x200B;**表情符號**&#x200B;列舉來更新表情符號清單。 了解更多
* **系統**&#x200B;列舉與系統欄位相關聯，而且帶有內部名稱。

對於&#x200B;**開啟**&#x200B;和&#x200B;**關閉**&#x200B;列舉，可以使用特定選項：

* **簡單列舉**&#x200B;是預設的標準型別。
* **別名清除**&#x200B;列舉是用來協調資料庫中儲存的列舉值。 [了解更多](#alias-cleansing)
* **保留給量化**&#x200B;是一個可讓您將Cube值連結到這個列舉的選項。 [了解更多](../reporting/gs-cubes.md)


### 別名清除 {#alias-cleansing}

在分項清單欄位中，您可以選取值，或輸入下拉式清單中沒有的自訂值。 可以將自訂值新增到現有的列舉值中，作為新的列舉值 — 在此情況下，必須選取&#x200B;**[!UICONTROL Open]**&#x200B;選項。 您可以使用別名清除功能來清除這些自訂值。 例如，如果使用者輸入`Adob`而非`Adobe`，則別名清除程式可以自動以正確的字詞取代它。

>[!CAUTION]
>
>資料清除是影響資料庫中資料的重要程式。 Adobe Campaign會執行大量資料更新，這可能會導致某些值被刪除。 因此，這項作業將保留給專家使用者。

啟用&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;選項以使用列舉的資料清除功能。 選取此選項時，**[!UICONTROL Alias]**&#x200B;索引標籤會顯示在視窗底部。

當使用者輸入的值不存在別名清除列舉中時，就會將其新增到&#x200B;**值**&#x200B;清單。 您可以[從這些值](#convert-to-alias)建立別名，或[從頭開始建立新別名](#create-alias)。

#### 建立別名{#create-alias}

若要建立別名，請執行下列步驟：

1. 按一下&#x200B;**[!UICONTROL Alias]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。
1. 輸入您要轉換的別名，然後在下拉式清單中選取要套用的值。

   ![建立新別名](assets/new-alias.png)

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;並確認。

1. 儲存您的變更。值取代是由每晚執行的&#x200B;**別名清理**&#x200B;工作流程所執行。 請參閱[執行資料清除](#running-data-cleansing)。

對於以此分項清單為基礎的所有欄位，當使用者在「公司」欄位(在Adobe Campaign使用者端主控台的Web表單中)中輸入值&#x200B;**Adobe**&#x200B;時，它會自動被值&#x200B;**Adobe**&#x200B;取代。

#### 將錯誤值轉換為別名{#convert-to-alias}

您也可以將現有的列舉值轉換為別名。 若要執行此動作：

1. 在列舉值清單中，按一下滑鼠右鍵並瀏覽至&#x200B;**[!UICONTROL Actions... > Convert values into aliases...]**。

   ![將值轉換為別名](assets/convert-into-aliases.png)

1. 選取要轉換為別名的值，然後按一下&#x200B;**[!UICONTROL Next]**。
1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;以執行轉換。

   執行完成後，別名會新增至&#x200B;**別名**&#x200B;索引標籤的清單中。 您可以關聯正確的值來取代錯誤的專案。 若要執行此動作：

1. 選取要清除的值。
1. 按一下&#x200B;**詳細資料……**&#x200B;按鈕。
1. 在下拉式清單中選取新值。

   ![建立新別名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以在&#x200B;**[!UICONTROL Alias]**&#x200B;子索引標籤的&#x200B;**[!UICONTROL Hits]**&#x200B;欄中追蹤別名的發生次數。 它可以顯示輸入此值的次數。  [了解更多](#calculate-entry-occurrences)。

#### 執行資料清除 {#running-data-cleansing}

資料清除是由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技術工作流程執行。 預設會每天執行。

也可以透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結觸發清除。

**[!UICONTROL Advanced parameters...]**&#x200B;連結可讓您設定開始考慮所收集值的日期。

按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕以執行資料清除。

##### 監視發生次數 {#calculate-entry-occurrences}

分項清單的&#x200B;**[!UICONTROL Alias]**&#x200B;子索引標籤可顯示輸入的所有值中別名的發生次數。 此資訊為預估值，會顯示在&#x200B;**[!UICONTROL Hits]**&#x200B;欄中。

>[!CAUTION]
>
>計算別名專案發生次數可能需要很長的時間。
>

您可以透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結手動執行點選計算。 若要這麼做，請按一下&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;連結並選取選項。

* **[!UICONTROL Update the number of alias hits]**：這可讓您根據輸入的日期，更新已計算的點選。
* **[!UICONTROL Recalculate the number of alias hits from the start]**：可讓您在整個Adobe Campaign平台上執行計算。

您也可以建立專屬的工作流程，讓計算在指定的期間內自動執行（例如每週執行一次）。

若要這麼做，請建立&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;工作流程的復本、變更排程器，並在&#x200B;**[!UICONTROL Enumeration value cleansing]**&#x200B;活動中使用下列設定：

* **-updateHits**&#x200B;以更新別名點選數，
* **-updateHits：full**&#x200B;以重新計算所有別名點選。
