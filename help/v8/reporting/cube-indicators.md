---
title: 在Adobe Campaign中建立多維度資料集
description: 瞭解如何建立多維度資料集
feature: Reporting
role: Developer
level: Beginner
exl-id: 03a6816b-e51a-4eaf-ab76-02d24f97ba46
TQID: 'https://experienceleague.adobe.com/XLxFJOA5J9hP-CxI3JmYBHyvCBZyerwJYBrX1IkvrMY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 63e73a31c5c46cb7544917557c3a0670d7ac91c9
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 1%
---
# 建立多維度資料集{#create-a-cube}

## Cube工作區 {#cube-workspace}

若要存取多維度資料集，請從Campaign檔案總管瀏覽至&#x200B;**[!UICONTROL Administration > Configuration > Cubes]**。

總管中「管理>組態」下的![多維資料庫節點，包含多維資料庫清單和選取的多維資料庫詳細資訊](assets/cube-node.png)

您可以使用立方體來：

* 直接在報表中匯出資料（在Adobe Campaign平台的&#x200B;**[!UICONTROL Reports]**&#x200B;索引標籤中設計）。

  要執行此操作，請建立新報表並選取您要使用的立方結構。

  ![從可用的Cube範本建立新報告，已選取收件者，並在[建立]之前輸入標籤](assets/create-new-cube.png)

  立方結構看起來就像範本，根據建立的報表而定。 選擇範本後，按一下「**[!UICONTROL Create]**」以設定並檢視新報告。

  您可以調整測量、變更顯示模式或設定表格，然後使用主要按鈕顯示報表。

  ![以Cube為基礎的新報表，包含「測量」、「年齡」和「國家/地區」欄位，以及顯示樞紐分析表的按鈕](assets/display-cube-table.png)

* 參照報告&#x200B;**[!UICONTROL Query]**&#x200B;方塊中的Cube以使用它的指標，如下所示：

  ![已選取[使用Cube]選項且已在Cube欄位中選取Cube的報表查詢活動](assets/cube-report-query.png)

* 在報表的任何頁面中插入以立方體為基礎的樞紐分析表。 若要這麼做，請在相關頁面上參考要在樞紐分析表&#x200B;**[!UICONTROL Data]**&#x200B;索引標籤中使用的Cube。

  ![報表頁面上樞紐分析表的資料頁簽，在Cube欄位中選取Cube，並選取Age和City維度](assets/cube-in-a-report.png)

  如需詳細資訊，請參閱[探索報表中的資料](cube-tables.md#explore-the-data-in-a-report)。


>[!CAUTION]
>
>建立立方體需要管理員許可權。
>

## 建立多維度資料集{#cube-create}

在建立立方結構報表之前，請先識別相關的維度和計量，並在立方結構中建立它們。

若要建立立方結構，請套用下列步驟：

1. 選取工作表。 [了解更多資訊](#select-the-work-table)。
1. 定義維度。 [了解更多資訊](#define-dimensions)。
1. 定義測量。 [了解更多資訊](#build-indicators)。
1. 建立彙總（選用）。 [了解更多資訊](customize-cubes.md#calculate-and-use-aggregates)。

在下列範例中，瞭解如何在報告中快速建立簡單的立方結構以匯出其測量。

### 選取工作表 {#select-the-work-table}

若要建立多維度資料集，請遵循下列步驟：

1. 按一下立方結構清單上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。

   ![含有事實來源選項、事實結構描述欄位、標籤和儲存按鈕的新增Cube對話方塊](assets/create-a-cube.png)

1. Select包含您要探索之元素（也稱為「事實結構描述」）的結構描述。 在此範例中，選取預設的&#x200B;**收件者**&#x200B;資料表。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以建立多維資料庫：已新增至多維資料庫清單。 您現在可以使用標籤進行設定。

1. 按一下&#x200B;**[!UICONTROL Filter the source data...]**&#x200B;連結，將此Cube的計算套用至資料庫中的資料。

   ![Cube一般頁簽，其中的[篩選]來源資料連結會開啟[編輯篩選]對話方塊，且條件Age大於18](assets/cube-filter-source.png)

### 定義維度 {#define-dimensions}

建立立方結構之後，請定義其維度。 維度是根據每個立方結構相關事實結構描述所定義的分析軸。 這些是在分析中探索的維度，例如時間（年、月、日）、產品或合約的分類（家庭、參考資料等）、人口區段（依城市、年齡群組、狀態等）。

若要建立維度，請遵循下列步驟：

1. 瀏覽至Cube的&#x200B;**[!UICONTROL Dimension]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕以建立新的維度。
1. 在&#x200B;**[!UICONTROL Expression field]**&#x200B;中，按一下&#x200B;**[!UICONTROL Edit expression]**&#x200B;圖示以選取包含相關資料的欄位。

   ![維度索引標籤，其中包含[新增]按鈕和[新增維度]對話方塊；[編輯運算式]圖示會選取欄位](assets/cube-add-dimension.png)

1. 在此範例中，我們選取的是收件者&#x200B;**年齡**。 對於此欄位，您可以定義量化以分組年齡，並讓資訊閱讀更容易。 當存在數個獨立值的可能性時，我們建議使用量化。

若要這麼做，請核取&#x200B;**[!UICONTROL Enable binning]**&#x200B;選項。 [了解更多資訊](customize-cubes.md#data-binning)。

1. 新增&#x200B;**日期**&#x200B;型別維度。 在這裡，我們要顯示收件者設定檔建立日期。 若要這麼做，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選取收件者表格中的&#x200B;**[!UICONTROL Creation date]**&#x200B;欄位。
您可以自訂日期顯示模式。 若要這麼做，請選取要使用的階層以及要產生的層次：

![建立日期維度對話方塊，其包含建立選項的層級：年、季、月、日和小時](assets/cube-date-dimension.png)

在我們的範例中，我們只想顯示年、月和日。 請注意，您不能同時使用周和半年/月：這些層級不相容。

1. 建立另一個維度以分析相對於收件者城市的資料。 若要這麼做，請新增維度，並在收件者結構描述的&#x200B;**[!UICONTROL Location]**&#x200B;節點中選取城市。

您可以啟用量化以使資訊讀取更容易，並將值連結至[分項清單](../config/enumerations.md)。

從下拉式清單中Select分項清單。 請注意，此列舉必須定義為&#x200B;**[!UICONTROL Reserved for binning]**。

![啟用量化的「城市」維度，以動態方式將值連結至其他值的列舉和標籤](assets/cube-dimension-with-enum.png)

只會顯示分項清單中的值。 其他則將在&#x200B;**[!UICONTROL Label of the other values]**&#x200B;欄位中定義的標籤下分組。

如需詳細資訊，請參閱[動態管理回收筒](customize-cubes.md#dynamically-manage-bins)。

### 建立指標 {#build-indicators}

定義維度後，請指定要在儲存格中顯示的值的計算模式。

若要這麼做，請在&#x200B;**[!UICONTROL Measures]**&#x200B;索引標籤中建立指標。 根據此Cube建立要顯示在報表中的欄數。

若要建立指標，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Measures]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。
1. Select測量型別和要套用的公式。 在此範例中，我們會計算收件者中女性的數量。 我們的量值是以事實結構描述為基礎，並使用&#x200B;**[!UICONTROL Count]**&#x200B;運運算元。

   ![新量值對話方塊，其中包含使用事實結構描述、Count運運算元和篩選量值資料連結所定義的量值](assets/cube-new-measure.png)

   使用&#x200B;**[!UICONTROL Filter the measure data...]**&#x200B;連結僅選取女性。 [了解更多資訊](customize-cubes.md#define-measures)。

   ![編輯篩選對話方塊，其條件性別等於並在值清單中選取女性值](assets/cube-filter-measure-data.png)

1. 輸入測量的標籤並儲存。

   ![使用Count運運算元完成的女性量值，篩選器性別等於Female且儲存前的Label欄位](assets/cube-save-measure.png)

1. 儲存立方體。


您現在可以根據此多維度資料集建立報告。 [了解更多資訊](cube-tables.md)。
