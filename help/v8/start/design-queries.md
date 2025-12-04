---
title: 在Campaign v8中設計查詢
description: 瞭解如何在Campaign使用者端主控台中建立查詢
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: edd495a377559007dad7158c9ab4a4917d89ae73
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 3%

---

# 查詢行銷活動資料庫

透過使用所選資料表的欄位或公式可以建立查詢。

在Adobe Campaign中建立查詢的步驟如下：

1. [選取工作表](#step-1---choose-a-table)。
1. [選取要擷取的資料](#step-2---choose-data-to-extract)。
1. [定義資料排序模式](#step-3---sort-data)。
1. [定義資料篩選選項](#step-4---filter-data)。
1. [設定資料格式](#step-5---format-data)。
1. [預覽查詢的結果](#step-6---preview-data)。

所有這些步驟都可在[一般查詢編輯器](query-editor.md)中使用。 在另一個前後關聯中建立查詢時，可能會遺漏某些步驟。 若要深入瞭解查詢，另請參閱[工作流程查詢活動檔案](../../automation/workflow/query.md)。


## 步驟1 — 選擇表格 {#step-1---choose-a-table}

若要查詢Campaign資料庫，請開啟&#x200B;**[一般查詢編輯器](query-editor.md)**，然後選取包含您要在&#x200B;**[!UICONTROL Document type]**&#x200B;視窗中查詢之資料的資料表。

![](assets/query_editor_nveau_21.png)

如有需要，請使用篩選欄位或&#x200B;**[!UICONTROL Filters]**&#x200B;按鈕來篩選資料。

## 步驟2 — 選擇要擷取的資料 {#step-2---choose-data-to-extract}

在&#x200B;**[!UICONTROL Data to extract]**&#x200B;畫面上，選擇要包含在輸出中的欄位。 這些欄位將定義結果中顯示的欄。

例如，您可以選取&#x200B;**[!UICONTROL Age]**、**[!UICONTROL Primary key]**、**[!UICONTROL Email domain]**&#x200B;和&#x200B;**[!UICONTROL City]**。 輸出將根據此選取專案進行結構化。 若要調整欄的順序，請使用視窗右側的藍色箭頭。

![](assets/query_editor_nveau_01.png)

您可以透過新增公式或將流程套用至彙總函式來修改運算式。 若要編輯運算式，請按一下&#x200B;**[!UICONTROL Expression]**&#x200B;欄位，然後選取&#x200B;**[!UICONTROL Edit expression]**。

![](assets/query_editor_nveau_97.png)

您可以將輸出欄中顯示的資料分組。 若要這麼做，請在&#x200B;**[!UICONTROL Yes]**&#x200B;視窗的&#x200B;**[!UICONTROL Group]**&#x200B;欄中選取&#x200B;**[!UICONTROL Data to extract]**。 然後會根據選取的群組軸來彙總結果。 如需使用分組的查詢範例，請參閱[此區段](../../automation/workflow/query-delivery-info.md)。

![](assets/query_editor_nveau_56.png)

* **[!UICONTROL Handle groupings (GROUP BY + HAVING)]**&#x200B;選項可讓您將結果群組並套用條件至這些群組。 它適用於輸出欄中的所有欄位。 例如，您可以使用它來分組輸出欄中的值，然後篩選結果以僅擷取特定資訊，例如年齡介於35到50歲的收件者。

  如需詳細資訊，請參閱[本章節](../../automation/workflow/query-grouping-management.md)。

**[!UICONTROL Remove duplicate rows (DISTINCT)]**&#x200B;選項會從輸出中排除相同的列（刪除重複專案）。 例如，如果您選取&#x200B;**姓氏**、**名字**&#x200B;和&#x200B;**電子郵件**&#x200B;作為輸出欄，則所有三個欄位中具有相同值的任何記錄都將視為重複。 結果中只會保留一個例項，確保每個聯絡人只會出現一次。

## 步驟3 — 排序資料 {#step-3---sort-data}

**[!UICONTROL Sorting]**&#x200B;視窗可讓您排序欄內容。 使用箭頭來變更欄順序：

* **[!UICONTROL Sorting]**&#x200B;欄可啟用簡單排序，並從A到Z或依遞增順序排列欄內容。
* **[!UICONTROL Descending sort]**&#x200B;會以遞減順序將內容從Z排列到A。 這對於檢視紀錄銷售非常有用，例如：最高數字會顯示在清單頂端。

在此範例中，資料會根據收件者年齡以遞增順序排序。

![](assets/query_editor_nveau_57.png)

## 步驟4 — 篩選資料 {#step-4---filter-data}

查詢編輯器可讓您篩選資料以縮小結果。 可用的篩選器取決於您要查詢的表格。

![](assets/query_editor_nveau_09.png)

選取&#x200B;**[!UICONTROL Filtering conditions]**&#x200B;後，**[!UICONTROL Target elements]**&#x200B;區段隨即開啟。 在這裡，您可以定義規則來篩選要收集的資料。

* 若要建立新篩選器，請選擇建立條件所需的欄位、運運算元和值。 您也可以合併多個條件，如本頁[的](filter-conditions.md)所述。

* 若要重複使用現有的篩選器，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕，選取&#x200B;**[!UICONTROL Predefined filter]**&#x200B;並選擇您想要的篩選器。

  ![](assets/query_editor_15.png)

在&#x200B;**[!UICONTROL Generic query editor]**&#x200B;中建立的篩選器可重複用於其他查詢應用程式，反之亦然。 若要儲存篩選器以供稍後使用，請按一下&#x200B;**[!UICONTROL Save]**&#x200B;圖示。

>[!NOTE]
>
>如需建立和使用篩選的詳細資訊，請參閱[篩選選項](filter-conditions.md)。

如下列範例所示，若要復原所有說英語的收件者，請選取：「收件者語言&#x200B;**等於** EN」。

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>您可以在&#x200B;**值**&#x200B;欄位中輸入下列公式，直接存取選項： **$（選項:OPTION_NAME）**。

按一下&#x200B;**[!UICONTROL Preview]**&#x200B;標籤以檢視篩選條件的結果。 在此情況下，所有說英語的收件者都會顯示其名稱、名字和電子郵件地址。

![](assets/query_editor_nveau_98.png)

熟悉SQL語言的使用者可以按一下&#x200B;**[!UICONTROL Generate SQL query]**&#x200B;以檢視SQL中的查詢。

![](assets/query_editor_nveau_99.png)

## 步驟5 — 格式化資料 {#step-5---format-data}

設定限制篩選器後，**[!UICONTROL Data formatting]**&#x200B;視窗會開啟。 在此視窗中，您可以重新排列輸出欄、轉換資料，以及調整欄標籤大小寫。 您也可以建立計算欄位，將公式套用至最終結果。

>[!NOTE]
>
>如需有關計算欄位型別的詳細資訊，請參閱[建立計算欄位](filter-conditions.md#creating-calculated-fields)。

未勾選的欄會隱藏在資料預覽視窗中。

![](assets/query_editor_nveau_10.png)

**[!UICONTROL Transformation]**&#x200B;欄可讓您將欄標籤變更為大寫或小寫。 選取欄並按一下&#x200B;**[!UICONTROL Transformation]**&#x200B;欄。 您可以選擇：

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**。

![](assets/query_editor_nveau_42.png)

## 步驟6 — 預覽資料 {#step-6---preview-data}

**[!UICONTROL Data preview]**&#x200B;視窗標籤查詢程式的最後階段。 按一下&#x200B;**[!UICONTROL Start the preview of the data]**&#x200B;以檢閱結果，結果可以欄或XML格式顯示。 若要檢查基礎SQL查詢，請開啟&#x200B;**[!UICONTROL Generated SQL queries]**&#x200B;索引標籤。 此步驟可讓您在進一步使用查詢之前，先驗證查詢是否如預期般運作。

在此範例中，資料會根據收件者年齡以遞增順序排序。

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>如同中，對於主控台中可用的所有清單，預設情況下，**[!UICONTROL Data preview]**&#x200B;視窗中只會顯示前200行。 若要變更，請在&#x200B;**[!UICONTROL Lines to display]**&#x200B;方塊中輸入數字，然後按一下&#x200B;**[!UICONTROL Start the preview of the data]**。 [了解更多](../config/ui-settings.md#manage-and-customize-lists)



**相關主題**

* [工作流程查詢活動](../../automation/workflow/query.md)
* [查詢收件者表格](../../automation/workflow/querying-recipient-table.md)
* [篩選條件](filter-conditions.md)