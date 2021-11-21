---
title: 使用Campaign和外部資料庫(FDA)
description: 了解如何使用Campaign和外部資料庫
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: tm+mt
source-wordcount: '1843'
ht-degree: 3%

---

# 同盟資料存取 (FDA){#gs-fda}

使用FDA連接器（同盟資料存取）將Campaign連線至一或多個 **外部資料庫** 和處理儲存在其中的資訊，而不會影響您的Campaign Cloud資料庫資料。 接著，您就可以存取外部資料，而不需變更Adobe Campaign資料的結構。

>[!NOTE]
>
>FDA的相容資料庫列於 [相容性矩陣](../start/compatibility-matrix.md).

促銷活動FDA選項可讓您在協力廠商資料庫中擴充您的資料模型。 它將自動檢測目標表的結構，並使用來自SQL源的資料。

特定 **權限** 在 [!DNL Adobe Campaign] 和外部資料庫進行交互。 深入了解 [本節](#fda-permissions).

## 最佳實務和限制

* **使用外部資料最佳化電子郵件個人化**

   您可以在專用的工作流程中預先處理訊息個人化。 若要執行此作業，請使用 **[!UICONTROL Prepare the personalization data with a workflow]** 選項，可在 **[!UICONTROL Analysis]** 標籤。

   在傳遞分析期間，此選項會自動建立並執行工作流程，該工作流程會將連結到目標的所有資料儲存在臨時表中，包括來自連結到外部資料庫的表的資料。

   此選項可大幅改善執行個人化步驟時的效能。

* **FDA限制**

   FDA選項是用來在工作流程中以批次模式處理外部資料庫中的資料。 為避免效能問題，不建議在單一操作的情境下使用FDA模組，例如：個人化、互動、即時訊息傳送等。

   請盡量避免同時使用Adobe Campaign和外部資料庫的操作。 若要這麼做，您可以：

   * 將Adobe Campaign資料庫匯出至外部資料庫，並在將結果重新匯入Adobe Campaign之前，僅從外部資料庫執行操作。

   * 從外部Adobe Campaign資料庫收集資料，並在本機執行操作。

   如果您想要使用外部資料庫的資料在傳送中進行個人化，請收集要在工作流程中使用的資料，以便在暫時表格中使用。 然後使用臨時表格中的資料來個人化您的傳送。

   FDA選項受您所使用外部資料庫系統的限制。


## 設定步驟{#fda-configuration-steps}

若要使用FDA設定外部資料庫的存取權，設定步驟為：

1. 身為Adobe Managed Services使用者，請連絡Adobe以在您的Campaign執行個體上安裝驅動程式。
1. 安裝驅動程式後，請設定與Adobe Campaign伺服器上的資料庫相對應的外部帳戶，並測試外部帳戶。 [了解更多](#fda-external-account)
1. 在Adobe Campaign中建立外部資料庫的架構。 這可讓您識別外部資料庫的資料結構。 [了解更多](#create-data-schema)
1. 如有需要，從先前建立的架構建立新的目標對應。 如果傳送的收件者來自外部資料庫，則此為必要項目。 此實施隨附與訊息個人化相關的限制。 [了解更多](#define-data-mapping)

## 外部資料庫外部帳戶{#fda-external-account}

您需要建立特定的外部帳戶，將您的Campaign執行個體連結至外部資料庫。

請遵循以下步驟完成此項目：

1. 從促銷活動 **[!UICONTROL Explorer]**，瀏覽 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

1. 按一下&#x200B;**[!UICONTROL New]**。

   >[!NOTE]
   >
   > 若要啟用， **[!UICONTROL Enabled]** 選項。 如有必要，請取消選中此選項以禁用對此資料庫的訪問而不刪除其配置。

1. 選擇 **[!UICONTROL External database]** 作為外部帳戶 **[!UICONTROL Type]**.

1. 在下拉式清單中選擇您的外部資料庫，並設定外部帳戶。 您必須指定：

   * **[!UICONTROL Server]**:伺服器的URL

   * **[!UICONTROL Account]**:使用者名稱

   * **[!UICONTROL Password]**:使用者帳戶密碼

   * **[!UICONTROL Database]**:資料庫的名稱

      ![](assets/snowflake.png)

1. 按一下 **[!UICONTROL Parameters]** ，然後 **[!UICONTROL Deploy functions]** 按鈕以建立函式。

1. 輸入參數後，按一下 **[!UICONTROL Test the connection]** 按鈕來核准。

1. 要允許Adobe Campaign訪問此資料庫，必須部署SQL函式。 按一下 **[!UICONTROL Parameters]** ，然後 **[!UICONTROL Deploy functions]** 按鈕。

可以為表和中的索引定義特定的工作表空間 **[!UICONTROL Parameters]** 標籤。

針對 [!DNL Snowflake]，連接器支援下列選項：

| Option | 說明 |
|---|---|
| 工作架構 | 用於工作表的資料庫架構 |
| 倉儲 | 要使用的預設倉庫的名稱。 它會覆寫使用者的預設值。 |
| 時區名稱 | 預設為空，這表示使用Campaign Classic應用程式伺服器的系統時區。 選項可用來強制TIMEZONE會話參數。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
| WeekStart | WEEK_START會話參數。 預設為0。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
| UseCachedResult | USE_CACHED_RESULTS會話參數。 預設為TRUE。 此選項可用於禁用Snowflake快取結果。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |


## 建立資料方案{#create-data-schema}

若要在Adobe Campaign中建立外部資料庫的架構，請遵循下列步驟：

1. 按一下 **[!UICONTROL New]** 按鈕，然後選擇 **[!UICONTROL Access external data]**.

   ![](assets/wf_new_schema_fda.png)

1. 輸入方案的名稱和說明，並選擇將啟用與資料庫連接的外部帳戶。 這允許訪問外部資料庫中可用的表清單。 選擇包含要收集的資料的表。

   ![](assets/wf_new_schema_select_table_fda.png)

1. 按一下 **[!UICONTROL OK]** 確認。 Adobe Campaign會自動偵測所選表格的結構，並產生邏輯架構。 請注意，Adobe Campaign不會產生連結。

1. 按一下 **[!UICONTROL Save]** 確認建立。

## 定義目標對應{#define-data-mapping}

您可以定義外部表格中資料的對應。

要執行此操作，建立外部表的架構後，您需要建立新的傳送對應，以將此表中的資料用作傳送目標。

要執行此操作，請依照下列步驟執行：

1. 瀏覽至 **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** 從Adobe Campaign資源管理器。

1. 建立新的目標對應，並選取您剛建立的結構作為目標維度。

   ![](assets/new-target-mapping.png)


1. 指定儲存傳送資訊的欄位（姓氏、名字、電子郵件、地址等）。

   ![](assets/wf_new_mapping_define_join.png)

1. 指定資訊儲存的參數，包括擴充功能結構的尾碼，以便輕鬆識別。

   ![](assets/wf_new_mapping_define_names.png)

   您可以選擇是否儲存排除項目(**排除記錄**)，含訊息(**broadlog**)或個別表格中。

   您也可以選擇是否管理此傳送對應的追蹤(**trackinglog**)。

1. 然後選取要考慮的擴充功能。 擴充功能類型取決於您平台的參數和選項（檢視您的授權合約）。

   ![](assets/wf_new_mapping_define_extensions.png)

   按一下 **[!UICONTROL Save]** 啟動傳遞對應建立的按鈕：所有連結表都會根據所選參數自動建立。


## 權限{#fda-permissions}

特定 **權限** 在 [!DNL Adobe Campaign] 和外部資料庫進行交互。

首先，為了讓使用者能透過FDA對外部資料庫執行操作，運算子必須具有中指定的特定權限 [!DNL Adobe Campaign].

1. 選取 **[!UICONTROL Administration > Access Management > Named Rights]** 節點。
1. 指定您選取的標籤，以建立新權限。
1. 以下格式輸入「已命名」右側的名稱 **user:base@server**，其中：

   * **使用者** 是外部資料庫中用戶的名稱
   * **基礎** 是外部資料庫的名稱
   * **伺服器** 是外部資料庫伺服器的名稱

1. 儲存「已命名」權限，並從 **[!UICONTROL Administration > Access Management > Operators]** 節點。

然後，若要處理外部資料庫中包含的資料，Adobe Campaign運算子必須對資料庫至少具有「寫入」權限，才能建立工作表。 這些表格會由Adobe Campaign自動刪除。

需要下列權限：

* **CONNECT**:連接到遠程資料庫
* **讀取資料**:對包含客戶資料的表的只讀訪問
* **閱讀「MetaData」**:訪問伺服器資料目錄以獲取表結構
* **載入**:在工作表中大量載入（處理集合和聯接時需要）
* **建立/放置** for **表/索引/過程/函式** (僅適用於Adobe Campaign產生的工作台)
* **說明** （建議）:在出現問題時監控效能
* **寫入資料** （視整合案例而定）

資料庫管理員需要使這些權限與每個資料庫引擎的特定權限相匹配，如下所述。

|   | Snowflake | Amazon Redshift |
|:-:|:-:|:-:|
| **連接到遠程資料庫** | 倉庫使用、資料庫使用和方案權限使用 | 建立連結至AWS帳戶的使用者 |
| **建立表格** | 建立方案權限表 | 建立權限 |
| **建立索引** | N/A | 建立權限 |
| **建立函式** | 建立架構權限的函式 | USAGE ON LANGUAGE plpythonu特權可調用外部python指令碼 |
| **建立程式** | 不適用 | USAGE ON LANGUAGE python特權可調用外部python指令碼 |
| **刪除對象（表、索引、函式、過程）** | 擁有對象 | 擁有對象或是超級用戶 |
| **監控執行** | 對所需對象的監視權限 | 使用EXPLAIN命令無需任何權限 |
| **寫入資料** | INSERT和/或UPDATE權限（取決於寫操作） | 插入和更新權限 |
| **將資料載入表格** | 在架構上建立階段，在目標表權限上選擇並插入 | 選擇和插入權限 |
| **訪問客戶端資料** | 選擇「開啟（未來）」表或「查看」權限 | 選擇權限 |
| **存取中繼資料** | 選擇INFORMATION_SCHEMA架構權限 | 選擇權限 |


## 在工作流程中使用外部資料

建立資料結構後，即可在Adobe Campaign工作流程中處理資料。

多個活動可讓您與外部資料庫的資料互動：

* **篩選外部資料** - **[!UICONTROL Query]** 活動可讓您新增外部資料，並在定義的篩選設定中使用。

* **建立子集** - **[!UICONTROL Split]** 活動可讓您建立子集。 您可以使用外部資料來定義要使用的篩選條件。

* **載入外部資料庫**  — 您可以在 **[!UICONTROL Data loading (RDBMS)]** 活動。

* **新增資訊和連結** - **[!UICONTROL Enrichment]** 活動可讓您新增其他資料至工作流程的工作表，以及連結至外部表格。 在此內容中，它可使用外部資料庫的資料。


您也可以針對暫時用途，直接從這些工作流程活動定義外部資料庫的連線。 在此情況下，它將位於本地外部資料庫上，保留用於當前工作流中：不會儲存在外部帳戶上。

>[!CAUTION]
>
>此類型的設定只能暫時用於收集資料。 任何其他用途均應偏好使用外部帳戶設定。

例如，在 **[!UICONTROL Query]** 活動，您可以定義外部資料庫的臨時連線，如下所示：

1. 開啟活動，然後按一下 **[!UICONTROL Add data...]**
1. 選取 **[!UICONTROL External data]** 選項
1. 選取 **[!UICONTROL Locally defining the data source]** 選項
1. 在下拉式清單中選取目標資料庫引擎。 輸入伺服器的名稱並提供驗證參數。 也指定外部資料庫的名稱。
1. 選擇資料儲存所在的表。 您可以直接在相應欄位中輸入表的名稱，或按一下編輯表徵圖以訪問資料庫表的清單。
1. 按一下 **[!UICONTROL Add]** 按鈕，在外部資料庫資料和Adobe Campaign資料庫中的資料之間定義一個或多個調解欄位。 此 **[!UICONTROL Edit expression]** 表徵圖 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 可讓您存取每個表格的欄位清單。
1. 如有必要，請指定篩選條件和資料排序模式。
1. 選取要在外部資料庫中收集的其他資料。 若要這麼做，請連按兩下您要新增的欄位，以在 **[!UICONTROL Output columns]**.
1. 按一下 **[!UICONTROL Finish]** 確認此設定。
