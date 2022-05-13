---
title: 使用活動和外部資料庫(FDA)
description: 瞭解如何使用活動和外部資料庫
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 3%

---

# 同盟資料存取 (FDA){#gs-fda}

使用FDA連接器（聯合資料存取）將市場活動連接到一個或多個 **外部資料庫** 並處理儲存在其中的資訊，而不影響您的市場活動雲資料庫資料。 然後，您可以訪問外部資料，而不更改Adobe Campaign資料的結構。

>[!NOTE]
>
>* FDA的相容資料庫列於 [相容性矩陣](../start/compatibility-matrix.md)。
>
>* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，可使用特定外部帳戶管理市場活動本地資料庫和Snowflake雲資料庫之間的通信。 此外部帳戶是通過Adobe為您設定的，不得修改。
>


活動FDA選項允許您在第三方資料庫中擴展您的資料模型。 它將自動檢測目標表的結構並使用SQL源中的資料。

特定 **權限** 需要 [!DNL Adobe Campaign] 並在外部資料庫上進行交互。 瞭解詳情 [此部分](#fda-permissions)。

## 最佳實務和限制

* **利用外部資料優化電子郵件個性化**

   您可以在專用工作流中預處理消息個性化。 要執行此操作，請使用 **[!UICONTROL Prepare the personalization data with a workflow]** ，在 **[!UICONTROL Analysis]** 的子菜單。

   在傳遞分析期間，此選項會自動建立並執行一個工作流，該工作流將連結到目標的所有資料儲存在臨時表中，包括來自外部資料庫中連結的表的資料。

   此選項在執行個性化設定步驟時顯著提高效能。

* **FDA限制**

   FDA選項用於在工作流中以批處理模式處理外部資料庫中的資料。 為避免業績問題，不建議在單一操作中使用FDA模組，例如：個性化、交互、即時消息等。

   避免需要盡可能使用Adobe Campaign和外部資料庫的操作。 為此，您可以：

   * 將Adobe Campaign資料庫導出到外部資料庫，並僅在將結果重新導入Adobe Campaign之前從外部資料庫執行操作。

   * 從外部Adobe Campaign資料庫收集資料並在本地執行操作。

   如果您希望使用外部資料庫中的資料在交貨中執行個性化設定，請收集要在工作流中使用的資料，使其在臨時表中可用。 然後使用臨時表中的資料來個性化您的交付。

   FDA選項受您使用的外部資料庫系統的限制。


## 設定步驟{#fda-configuration-steps}

要使用FDA設定對外部資料庫的訪問，配置步驟包括：

1. 作為Adobe Managed Services用戶，請與Adobe聯繫，以在您的市場活動實例上安裝驅動程式。
1. 安裝驅動程式後，在Adobe Campaign伺服器上設定與資料庫對應的外部帳戶並test外部帳戶。 [了解更多](#fda-external-account)
1. 在Adobe Campaign建立外部資料庫的架構。 這允許您標識外部資料庫的資料結構。 [了解更多](#create-data-schema)

<!--
1. If needed, create a new target mapping from the previously created schema. This is required if the recipients of your deliveries come from the external database. This implementation comes with limitations related to message personalization. [Learn more](#define-data-mapping)
-->

請注意，使用市場活動 [企業(FDA)部署](../architecture/enterprise-deployment.md)，無法從FDA訪問的外部資料庫中儲存的架構建立目標映射。 因此，您交貨的收件人不能來自外部資料庫。

## 外部資料庫外部帳戶{#fda-external-account}

您需要建立特定的外部帳戶以將市場活動實例連接到外部資料庫。

請遵循以下步驟完成此項目：

1. 從市場活動 **[!UICONTROL Explorer]**，瀏覽 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

1. 按一下&#x200B;**[!UICONTROL New]**。

   >[!NOTE]
   >
   > 要處於活動狀態， **[!UICONTROL Enabled]** 選項。 如有必要，取消選中此選項可禁用對此資料庫的訪問，而不刪除其配置。

1. 選擇 **[!UICONTROL External database]** 作為您的外部帳戶 **[!UICONTROL Type]**。

1. 在下拉清單中選擇外部資料庫並配置外部帳戶。 必須指定：

   * **[!UICONTROL Server]**:伺服器的URL

   * **[!UICONTROL Account]**:用戶名

   * **[!UICONTROL Password]**:用戶帳戶密碼

   * **[!UICONTROL Database]**:資料庫的名稱

      ![](assets/snowflake.png)

1. 按一下 **[!UICONTROL Parameters]** 按鈕 **[!UICONTROL Deploy functions]** 按鈕。

1. 輸入參數後，按一下 **[!UICONTROL Test the connection]** 按鈕

1. 要允許Adobe Campaign訪問此資料庫，必須部署SQL函式。 按一下 **[!UICONTROL Parameters]** 按鈕 **[!UICONTROL Deploy functions]** 按鈕

您可以為中的表和索引定義特定的工作表空間 **[!UICONTROL Parameters]** 頁籤。

對於 [!DNL Snowflake]，連接器支援以下選項：

| Option | 說明 |
|---|---|
| 工作架構 | 用於工作表的資料庫架構 |
| 倉庫 | 要使用的預設倉庫的名稱。 它將覆蓋用戶的預設值。 |
| 時區名稱 | 預設為空，這意味著使用Campaign Classic應用伺服器的系統時區。 該選項可用於強制TIMEZONE會話參數。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
| 周開始 | WEEK_START會話參數。 預設設定為0。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
| UseCachedResult | USE_CACHED_RESULTS會話參數。 預設設定為TRUE。 此選項可用於禁用Snowflake快取結果。 <br>[如需關於此項目的詳細資訊，請參閱此頁面](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |


## 建立資料方案{#create-data-schema}

要在Adobe Campaign建立外部資料庫的模式，請執行以下步驟：

1. 按一下 **[!UICONTROL New]** 按鈕，然後選擇 **[!UICONTROL Access external data]**。

   ![](assets/wf_new_schema_fda.png)

1. 輸入方案的名稱和說明，然後選擇啟用與資料庫連接的外部帳戶。 這允許訪問外部基中可用的表清單。 選擇包含要收集的資料的表。

   ![](assets/wf_new_schema_select_table_fda.png)

1. 按一下 **[!UICONTROL OK]** 確認。 Adobe Campaign自動檢測所選表的結構並生成邏輯架構。 請注意，Adobe Campaign未生成連結。

1. 按一下 **[!UICONTROL Save]** 確認建立。

<!-- 
## Define the target mapping{#define-data-mapping}

You can define a mapping on the data in an external table.

To do this, once the schema of the external table has been created, you need to create a new delivery mapping to use the data in this table as a delivery target.

To do this, follow these steps:

1. Browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** from Adobe Campaign explorer.

1. Create a new target mapping and select the schema you just created as the targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indicate the fields where the delivery information is stored (last name, first name, email, address, etc.).

   ![](assets/wf_new_mapping_define_join.png)

1. Specify the parameters for information storage, including the suffix of the extension schemas for them to be easily identifiable.

   ![](assets/wf_new_mapping_define_names.png)

   You can choose whether to store exclusions (**excludelog**), with messages (**broadlog**) or in a separate table.

   You can also choose whether to manage tracking for this delivery mapping (**trackinglog**).

1. Then select the extensions to be taken into account. The extension type depends on your platform's parameters and options (view your license contract).

   ![](assets/wf_new_mapping_define_extensions.png)

   Click the **[!UICONTROL Save]** button to launch delivery mapping creation: all linked tables are created automatically based on the selected parameters.
-->

## 權限{#fda-permissions}

特定 **權限** 需要 [!DNL Adobe Campaign] 並在外部資料庫上進行交互。

首先，為了使用戶能夠通過FDA對外部資料庫執行操作，操作員必須在中具有特定的命名權限 [!DNL Adobe Campaign]。

1. 選擇 **[!UICONTROL Administration > Access Management > Named Rights]** 的子菜單。
1. 通過指定所選標籤建立新權限。
1. 按以下格式輸入命名權的名稱 **用戶：base@server**，其中：

   * **用戶** 是外部資料庫中用戶的名稱
   * **基礎** 是外部資料庫的名稱
   * **伺服器** 是外部資料庫伺服器的名稱

1. 保存「已命名」右側，並將其連結到所選運算子 **[!UICONTROL Administration > Access Management > Operators]** 的下界。

然後，要處理外部資料庫中包含的資料，Adobe Campaign操作員必須對資料庫至少具有「寫入」權限才能建立工作表。 這些表由Adobe Campaign自動刪除。

需要以下權限：

* **CONNECT**:到遠程資料庫的連接
* **讀取資料**:對包含客戶資料的表的只讀訪問
* **讀取「元資料」**:訪問伺服器資料目錄以獲取表結構
* **載入**:在工作表中成批載入（在處理集合和聯接時需要）
* **建立/刪除** 為 **表/索引/過程/函式** (僅用於Adobe Campaign生成的工作表)
* **解釋** （推薦）:用於在出現問題時監視效能
* **寫入資料** （取決於整合方案）

資料庫管理員需要使這些權限與每個資料庫引擎的特定權限相匹配，如下所述。

|   | Snowflake | Amazon Redshift |
|:-:|:-:|:-:|
| **連接到遠程資料庫** | 倉庫的使用、資料庫的使用和模式權限的使用 | 建立連結到AWS帳戶的用戶 |
| **建立表** | 在架構上建立表權限 | CREATE權限 |
| **建立索引** | N/A | CREATE權限 |
| **建立函式** | 對架構權限建立函式 | USAGE ON LANGUAGE plpythonu權限，可以調用外部python指令碼 |
| **建立過程** | 不適用 | USAGE ON LANGUAGE Python權限，可以調用外部python指令碼 |
| **刪除對象（表、索引、函式、過程）** | 擁有對象 | 擁有對象或是超級用戶 |
| **監視執行** | 對所需對象的MONITOR權限 | 使用EXPLAIN命令不需要權限 |
| **寫入資料** | INSERT和/或UPDATE權限（取決於寫入操作） | INSERT和UPDATE權限 |
| **將資料載入到表** | 在方案上建立階段，在目標表權限上選擇和插入 | SELECT和INSERT權限 |
| **訪問客戶端資料** | SELECT on(FUTURE)TABLE(S)或VIEW(S)權限 | SELECT權限 |
| **訪問元資料** | 選擇INFORMATION_SCHEMA權限 | SELECT權限 |


## 在工作流中使用外部資料

建立資料模式後，可以在Adobe Campaign工作流中處理資料。

通過多個活動，您可以與外部資料庫中的資料交互：

* **篩選外部資料** - **[!UICONTROL Query]** 活動允許您添加外部資料並在定義的篩選器配置中使用它。

* **建立子集** - **[!UICONTROL Split]** 活動允許您建立子集。 可以使用外部資料來定義要使用的篩選條件。

* **載入外部資料庫**  — 您可以使用 **[!UICONTROL Data loading (RDBMS)]** 的子菜單。

* **添加資訊和連結** - **[!UICONTROL Enrichment]** 「活動」(Activity)允許您向工作流的工作表添加附加資料，並連結到外部表。 在此上下文中，它可以使用外部資料庫中的資料。


您也可以直接從這些工作流活動定義到外部資料庫的連接，以便暫時使用。 在這種情況下，它將位於本地外部資料庫上，保留用於當前工作流：不會保存在外部帳戶中。

>[!CAUTION]
>
>此類型的配置只能用於臨時收集資料。 對於任何其他用途，應首選外部帳戶配置。

例如，在 **[!UICONTROL Query]** 活動，可以定義到外部資料庫的臨時連接，如下所示：

1. 開啟活動，然後按一下 **[!UICONTROL Add data...]**
1. 選擇 **[!UICONTROL External data]** 選項
1. 選擇 **[!UICONTROL Locally defining the data source]** 選項
1. 在下拉清單中選擇目標資料庫引擎。 輸入伺服器名稱並提供驗證參數。 還指定外部資料庫的名稱。
1. 選擇儲存資料的表。 可以直接在相應欄位中輸入表的名稱，或按一下編輯表徵圖訪問資料庫表的清單。
1. 按一下 **[!UICONTROL Add]** 按鈕，定義外部資料庫資料與Adobe Campaign資料庫中資料之間的一個或多個協調欄位。 的 **[!UICONTROL Edit expression]** 表徵圖 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 允許您訪問每個表的欄位清單。
1. 如有必要，請指定篩選條件和資料排序模式。
1. 選擇要在外部資料庫中收集的其他資料。 為此，請按兩下要添加的欄位，以在 **[!UICONTROL Output columns]**。
1. 按一下 **[!UICONTROL Finish]** 確認此配置。
