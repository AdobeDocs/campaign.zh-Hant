---
title: Campaign介面設定
description: 瞭解如何自訂Campaign介面設定
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 20%

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

## 管理和自訂清單 {#customize-lists}

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


## 其他資源

* **[從Campaign使用者介面開始](../start/campaign-ui.md)** — 瞭解如何存取和瀏覽Adobe Campaign介面。
* **[使用分項清單](../config/enumerations.md)** — 使用預先定義的下拉式清單標準化欄位值，以更快速、更一致的資料輸入。
