---
title: 建立目標工作流程
description: 瞭解如何在工作流程中建立目標對象
feature: Query Editor, Data Management
exl-id: 27be9d5a-168c-470e-a480-f3c71858fc75
source-git-commit: 122d78e310e66d5f354ffbc86c27a2fbff007447
workflow-type: tm+mt
source-wordcount: '2252'
ht-degree: 6%

---

# 建立目標定位工作流程{#target-data}

工作流程可用於查詢資料庫及劃分資料。 行銷活動工作流程模組是一個強大的工具，可執行資料管理活動、擷取、擴充和轉換資料、管理對象和調整母體。

目標工作流程可讓您建立數個傳遞目標。 由於工作流程活動，您可以根據特定條件建立查詢、定義聯合或排除、新增排程。 此目標定位的結果可自動傳輸至可作為傳遞動作目標的清單

除了這些活動以外，資料管理選項可讓您操控資料並存取進階函式，以滿足複雜的鎖定目標問題。 如需詳細資訊，請參閱[資料管理](targeting-workflows.md#data-management)。

所有這些活動都可在第一個工作流程標籤中找到。

>[!NOTE]
>
>目標定位活動在[本節](activities.md)中有詳細說明。

目標工作流程可以透過Adobe Campaign樹狀結構的&#x200B;**[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]**&#x200B;節點或透過首頁的&#x200B;**[!UICONTROL Profiles and Targets > Targeting workflows]**&#x200B;功能表來建立和編輯。

![](assets/target_wf.png)

行銷活動框架內的目標工作流程會與所有行銷活動工作流程一起儲存。

## 建立目標定位工作流程的關鍵步驟 {#implementation-steps-}

建立目標定位工作流程的步驟在以下章節中詳細說明：

1. **識別資料庫中的**&#x200B;資料 — 請參閱[建立查詢](#create-queries)
1. **準備**&#x200B;資料以符合傳遞需求 — 請參閱[擴充及修改資料](#enrich-and-modify-data)
1. **使用**&#x200B;資料執行更新或在傳遞中 — 請參閱[更新資料庫](use-workflow-data.md#update-the-database)

鎖定目標期間執行的所有增強功能和所有處理的結果都會儲存在個人化欄位中以供存取，尤其是在建立個人化訊息時使用。 如需詳細資訊，請參閱[目標資料](use-workflow-data.md#target-data)。

## 目標定位和篩選維度 {#targeting-and-filtering-dimensions}

在資料細分作業期間，目標定位鍵對應到篩選維度。目標定位維度可讓您定義作業的目標群體：收件者、合約受益人、操作者、訂閱者等。篩選維度可讓您可以根據特定標準選取群體：合約持有人、電子報訂閱者等。

例如，若要選取擁有超過5年壽險保單的客戶，請選取下列目標維度： **客戶**&#x200B;以及下列篩選維度： **合約持有者**。 然後，您可以在查詢活動中定義篩選條件

在目標維度選擇階段中，介面中只會提供相容的篩選維度。

這兩個維度必須相關。 因此，**[!UICONTROL Filtering dimension]**&#x200B;清單的內容取決於第一個欄位中指定的目標維度。

例如，收件者(**recipient**)可以使用下列篩選維度：

![](assets/query-filter-dimensions.png)

對於&#x200B;**訪客**，清單將包含下列篩選維度：

![](assets/query-filter-dimension-2.png)

## 建立查詢 {#create-queries}

### 使用其他資料 {#select-data}

**[!UICONTROL Query]**&#x200B;活動可讓您選取基本資料以建置目標母體。 如需詳細資訊，請參閱[本章節](query.md#create-a-query)。

您也可以使用下列活動來查詢及調整資料庫中的資料： [增量查詢](incremental-query.md)，[讀取清單](read-list.md)。

可在整個工作流程生命週期中收集要轉送及處理的其他資料。 如需詳細資訊，請參閱[新增資料](query.md#add-data)和[編輯其他資料](#edit-additional-data)。

### 編輯其他資料 {#edit-additional-data}

新增其他資料後，您可以編輯資料或使用這些資料來調整查詢活動中定義的目標。

**[!UICONTROL Edit additional data...]**&#x200B;連結可讓您檢視新增的資料，並修改或新增至其中。

![](assets/edit-additional-data.png)

若要將資料新增至先前定義的輸出欄，請在可用欄位清單中選取該資料。 若要建立新的輸出資料行，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;圖示，然後選取欄位並按一下&#x200B;**[!UICONTROL Edit expression]**。

![](assets/query_add_an_output_column.png)

按一下&#x200B;**進階選擇**&#x200B;按鈕。

![](assets/query_add_an_output_column_formula.png)

為要新增的欄位定義計算模式，例如彙總。

![](assets/query_add_aggregate.png)

**[!UICONTROL Add a sub-item]**&#x200B;選項可讓您將計算資料附加至集合。 這可讓您從收集中選取其他資料，或定義收集要素的彙總計算。

子元素會顯示在它們所對應之集合的子樹狀結構中。

集合顯示在&#x200B;**[!UICONTROL Collections]**&#x200B;子標籤中。 您可以按一下所選集合的&#x200B;**[!UICONTROL Detail]**&#x200B;圖示，以篩選所收集的元素。 篩選精靈可讓您選取收集的資料，並指定要套用至集合中資料的篩選條件。

### 使用其他資料調整目標 {#refine-the-target-using-additional-data}

收集的其他資料可讓您調整資料庫中的資料篩選。 若要這麼做，請按一下&#x200B;**[!UICONTROL Refine the target using additional data...]**&#x200B;連結：這可讓您對新增的資料進行過度篩選。

![](assets/wf_add_data_use_additional_data.png)

### 均勻化資料 {#homogenize-data}

在&#x200B;**[!UICONTROL Union]**&#x200B;或&#x200B;**[!UICONTROL Intersection]**&#x200B;型別活動中，您可以選擇只保留共用的其他資料，以保持資料的一致性。 在這種情況下，此活動的暫時輸出工作表將僅包含在所有入站集中找到的其他資料。

![](assets/use-common-add-data-only.png)

### 與其他資料調解 {#reconciliation-with-additional-data}

資料調解階段(**[!UICONTROL Union]**、**[!UICONTROL Intersection]**&#x200B;等 活動)，則可從其他欄中選取要用於資料協調的欄。 要執行此操作，請在選取的欄上設定調解，並指定主集。 然後選取視窗下方欄中的欄，如下列範例所示：

![](assets/select-column-and-join.png)

選取運算式並確認。

![](assets/select-column-and-join-2.png)


### 建立子集 {#create-subsets}

**[!UICONTROL Split]**&#x200B;活動可讓您根據透過擷取查詢定義的條件建立子集。 對於每個子集，當您編輯母體的篩選條件時，將存取可讓您定義目標細分條件的標準查詢活動。

您僅可使用其他資料作為篩選條件或目標資料將目標分割成數個子集。 如果您已購買&#x200B;**同盟資料存取**&#x200B;選項，也可以使用外部資料。

如需詳細資訊，請參閱[本章節](#create-subsets-using-the-split-activity)。

## 區段資料 {#segment-data}

### 結合數個目標（聯集） {#combine-several-targets--union-}

聯合活動可讓您在一個轉變中結合數個活動的結果。 集合不一定要是同質的。

![](assets/union-keys-only.png)

下列資料調解選項可供使用：

* **[!UICONTROL Keys only]**

  如果輸入母體是同質的，則可以使用此選項。

* **[!UICONTROL All columns in common]**

  此選項可讓您根據目標各種母體所共有的所有欄來調解資料。

  Adobe Campaign會根據欄的名稱來識別欄。 接受容許度臨界值：例如，「電子郵件」欄可識別為與「@email」欄相同。

* **[!UICONTROL A selection of columns]**

  選取此選項可定義將套用資料協調的欄清單。

  首先，選取主集（包含來源資料的主集），然後選取要用於聯結的欄。

  ![](assets/join-reconciliation-options.png)

  >[!CAUTION]
  >
  >在資料協調期間，母體不會進行重複資料刪除。

  您可以將母體大小限製為指定的記錄數。 若要這麼做，請按一下適當的選項，並指定要保留的記錄數。

  此外，指定入站母體的優先順序：視窗下方會列出聯合活動的入站轉變，並讓您使用視窗右側的藍色箭頭來排序它們。

  記錄會先從清單中第一個入站轉變的母體取得，如果未達到最大值，則會從第二個入站轉變的母體取得，以此類推。

  ![](assets/join_limit_nb_priority.png)

### 擷取連線點資料（交集） {#extract-joint-data--intersection-}

![](assets/traitements.png)

交集可讓您僅復原入站轉變母體所共用的線。 此活動必須像聯合活動一樣設定。

此外，可能只保留選定的欄，或只保留入站母體共用的欄。

在[交集](intersection.md)區段中會詳細說明交集活動。

### 排除人口（排除） {#exclude-a-population--exclusion-}

排除活動可讓您從不同的目標母體中排除目標的元素。 此活動的輸出目標維度將是主要集的輸出目標維度。

必要時，可以操控傳入表格。 事實上，若要從另一個維度排除目標，必須將此目標傳回主要目標的同一目標定位維度。若要這麼做，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕並指定維度變更條件。

資料調解可透過識別碼、變更軸或連線來執行。

![](assets/exclusion-add-rule.png)

### 使用分割活動建立子集 {#create-subsets-using-the-split-activity}

**[!UICONTROL Split]**&#x200B;活動是標準活動，可讓您透過一或多個篩選維度建立所需數量的集合，並為每個子集產生一個輸出轉變或產生唯一轉變。

入站轉變所傳達的其他資料可用於篩選條件中。

若要進行設定，您必須先選取條件：

1. 在工作流程中，拖放&#x200B;**[!UICONTROL Split]**&#x200B;活動。
1. 在&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中，選取所要的選項： **[!UICONTROL Use data from the target and additional data]**、**[!UICONTROL Use the additional data only]**&#x200B;或&#x200B;**[!UICONTROL Use external data]**。
1. 如果選取&#x200B;**[!UICONTROL Use data from the target and additional data]**&#x200B;選項，則目標維度可讓您使用入站轉變所傳達的所有資料。

   ![](assets/split-general-tab-options.png)

   建立子集時，會使用上述篩選引數。

   若要定義篩選條件，請選擇&#x200B;**[!UICONTROL Add a filtering condition on the inbound population]**&#x200B;選項並按一下&#x200B;**[!UICONTROL Edit...]**&#x200B;連結。 然後指定建立此子集的篩選條件。

   ![](assets/split-subset-config-all-data.png)

   在[本節](cross-channel-delivery-workflow.md)中說明如何在&#x200B;**[!UICONTROL Split]**&#x200B;活動中使用篩選條件將目標分割成不同母體的範例。

   **[!UICONTROL Label]**&#x200B;欄位可讓您為新建立的子集命名，以符合出站轉變。

   您也可以將區段代碼指派給子集，以識別該子集並使用它來定位其母體。

   如有必要，您可以針對要建立的每個子集個別變更目標定位和篩選維度。 若要這麼做，請編輯子集的篩選條件，並核取&#x200B;**[!UICONTROL Use a specific filtering dimension]**&#x200B;選項。

   ![](assets/split-subset-config-specific-filtering.png)

1. 如果選取&#x200B;**[!UICONTROL Use the additional data only]**&#x200B;選項，則僅提供額外的資料用於子集篩選。

1. 如果已啟用&#x200B;**同盟資料存取**&#x200B;選項，**[!UICONTROL Use external data]**&#x200B;可讓您在已設定的外部資料庫中處理資料，或建立與資料庫的新連線。

然後，我們需要新增子集：

1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕並定義篩選條件。

   ![](assets/wf_split_add_a_tab.png)

1. 在活動的&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中定義篩選維度（請參閱上文）。預設會套用至所有子集。

   ![](assets/wf_split_edit_filtering.png)

1. 如有必要，您可以個別變更每個子集的篩選維度。 這可讓您為所有金卡持有者建立一組檔案，一個檔案適用於在最新電子報中點按的所有收件者，第三個檔案適用於過去30天內於店內購買的18至25歲人士，所有檔案皆使用相同的分割活動。 若要這麼做，請選取&#x200B;**[!UICONTROL Use a specific filtering dimension]**&#x200B;選項並選取資料篩選內容。

建立子集後，分割活動預設會顯示與子集相同數量的輸出轉變：

![](assets/wf_split_multi_outputs.png)

您可以將所有這些子集群組為一個輸出轉變。 在此情況下，個別子集的連結將顯示在區段代碼中，例如。 若要這麼做，請選取&#x200B;**[!UICONTROL Generate all subsets in the same table]**&#x200B;選項。

![](assets/wf_split_single_output.png)

例如，您可以放置單一傳遞活動，並根據每個收件者集的區段代碼來個人化傳遞內容。


也可以使用&#x200B;**[!UICONTROL Cells]**&#x200B;活動建立子集。 如需詳細資訊，請參閱[儲存格](cells.md)區段。

### 使用目標資料 {#using-targeted-data}

識別並準備資料後，便可用於下列內容：

* 您可以在各種工作流程階段中進行資料操作後，更新資料庫中的資料。

  如需詳細資訊，[更新資料](update-data.md)。

* 您也可以重新整理現有清單的內容。

  如需詳細資訊，請參閱[清單更新](list-update.md)。

* 您可以直接在工作流程中準備或開始傳送。

  如需詳細資訊，請參閱[傳遞](delivery.md)、[傳遞控制](delivery-control.md)和[連續傳遞](continuous-delivery.md)。

## 資料管理 {#data-management}

在Adobe Campaign中，資料管理結合了一系列活動，提供更有效率、更靈活的工具以解決複雜的鎖定問題。 這可讓您使用合約、訂閱、傳遞再活動等的相關資訊，對與聯絡人的所有通訊進行一致的管理。 「資料管理」可讓您在細分作業期間追蹤資料生命週期，特別是：

* 透過包含未在資料超市中模型化的資料，來簡化及最佳化鎖定過程（建立新的資料表：根據配置，對目標工作流程進行本地擴展）。
* 保持和傳達緩衝區計算，尤其是在目標建構階段或進行資料庫管理時。
* 存取外部資料庫（選用）：在鎖定過程中考慮異質資料庫。

為了實作這些作業，Adobe Campaign提供：

* 資料收集活動： [檔案傳輸](file-transfer.md)、[資料載入（檔案）](data-loading-file.md)、[資料載入(RDBMS)](data-loading-rdbms.md)、[更新資料](update-data.md)。 收集資料的第一個步驟是準備資料，以便在其他活動中處理。 為了確保工作流程正確執行並提供預期的結果，需要監控數個引數。 例如，當您匯入資料時，此資料的主索引鍵(Pkey)對於每個記錄必須是唯一的。
* 目標活動已透過資料管理選項擴充： [查詢](query.md)、[聯合](union.md)、[交集](intersection.md)、[分割](split.md)。 這可讓您在數個不同目標維度的資料之間設定聯合或交集，前提是資料協調可行。
* 資料轉換活動： [擴充](enrichment.md)，[變更維度](change-dimension.md)。

>[!CAUTION]
>
>連結兩個工作流程時，刪除來源表格元素並不表示刪除連結至該元素的所有資料。
>  
>例如，透過工作流程刪除收件者將不會導致所有收件者的傳遞歷史記錄被刪除。 不過，直接在「收件者」資料夾中刪除收件者，實際上會導致所有連結至此收件者的資料遭到刪除。

### 豐富及修改資料 {#enrich-and-modify-data}

除了目標維度之外，篩選維度還可讓您指定收集資料的性質。 請參閱[本節](targeting-workflows.md#targeting-and-filtering-dimensions)。

已識別和收集的資料可以擴充、彙總和操作，以最佳化目標建構。 若要這麼做，除了[此區段](#segmen-data)中詳述的資料操作活動之外，請使用下列專案：

* **[!UICONTROL Enrichment]**&#x200B;活動可讓您暫時將欄新增至結構描述，以及將資訊新增至特定元素。 它在活動存放庫的[擴充](enrichment.md)區段中詳細說明。
* **[!UICONTROL Edit schema]**&#x200B;活動可讓您修改結構描述的結構。 活動存放庫的[編輯結構描述](edit-schema.md)區段中會詳細說明此專案。
* **[!UICONTROL Change dimension]**&#x200B;活動可讓您在目標建構週期中變更目標維度。 在[變更維度](change-dimension.md)區段中會詳細說明。
