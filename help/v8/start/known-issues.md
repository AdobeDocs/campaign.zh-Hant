---
title: Campaign v8已知問題
description: 最新Campaign版本中的已知問題
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 96e9f5fe5f07ea0c476395d33efa4d6bcf10cf60
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# 已知問題{#known-issues}

此頁面列出 **最新Campaign v8版本**. 此外，還列出Campaign v8的限制 [在本頁](ac-guardrails.md).


>[!NOTE]
>
>Adobe自行發佈此已知問題清單。 它以客戶報表數量、嚴重性和解決方案可用性為基礎。 如果您遇到的問題未列出，則可能不符合本頁面中發佈的條件。

## Campaign v8.3.8{#8.3-issues}

### 更改資料源活動問題#1 {#issue-1}

#### 說明{#issue-1-desc}

此 **變更資料來源** 將資料從Campaign本機資料庫傳輸至Snowflake雲端資料庫時，活動失敗。 切換方向時，活動可能會產生問題。

#### 再現步驟{#issue-1-repro}

1. 連線至用戶端主控台並建立工作流程。
1. 新增 **查詢** 活動與 **變更資料來源** 活動。
1. 在 **電子郵件**，即字串。
1. 執行工作流程並以滑鼠右鍵按一下轉變以檢視母體：電子郵件記錄會以 `****`.
1. 檢查工作流程記錄檔：the **變更資料來源** 活動會將這些記錄解譯為數值。

#### 錯誤訊息{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

#### 因應措施{#issue-1-workaround}

若要讓資料從Snowflake雲端資料庫傳輸至Campaign本機資料庫，再傳回至Snowflake，您必須使用兩個不同的 **變更資料來源** 活動。

#### 內部參考{#issue-1-ref}

參考資料：NEO-45549



### 變更資料來源活動問題 {#issue-2}

#### 說明{#issue-2-desc}

使用Campaign將資料插入Snowflake雲端資料庫時 **查詢** 和 **變更資料來源** 活動中，當資料中出現反斜線字元時，程式會失敗。 來源字串未逸出，且資料在Snowflake時無法正確處理。

只有反斜線字元位於字串結尾時才會發生此問題，例如： `Barker\`.


#### 再現步驟{#issue-2-repro}

1. 連線至用戶端主控台並建立工作流程。
1. 新增 **查詢** 活動並加以設定。
1. 選擇具有上述特性的資料。
1. 新增 **變更資料來源** 活動，並加以設定以選取「Snowflake雲端資料庫」。
1. 執行工作流程並檢查工作流程記錄檔以查看錯誤。


#### 錯誤訊息{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### 因應措施{#issue-2-workaround}

解決方法是排除字串結尾處包含反斜線字元的資料，或從來源檔案中移除該資料。


#### 內部參考{#issue-2-ref}

參考資料：NEO-45549


### 資料載入（檔案）活動無法在伺服器上上載檔案 {#issue-3}

#### 說明{#issue-3-desc}

在Campaign伺服器上上傳檔案時， **資料載入（檔案）** 活動時，程式會在100%處停止，但永不結束。

#### 再現步驟{#issue-3-repro}

1. 連線至用戶端主控台並建立工作流程。
1. 新增 **資料載入（檔案）** 活動並加以設定。
1. 選取 **在伺服器上傳** 選項。
1. 在本地電腦上選擇檔案，
1. 按一下 **上傳**


#### 錯誤訊息{#issue-3-error}

過程永遠不會結束。

#### 因應措施{#issue-3-workaround}

因應措施是使用舊版用戶端主控台。 然後，您就可以在伺服器上傳檔案。

身為Campaign管理員，您可以在 [Adobe軟體分發](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Rosvation&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}。

了解如何存取AdobeSoftware Distribution [在本頁](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hant){target=&quot;_blank&quot;}。

了解如何升級您的用戶端主控台 [在本頁](connect.md)

#### 內部參考{#issue-3-ref}

參考資料：NEO-47269