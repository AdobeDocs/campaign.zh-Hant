---
title: 市場活動v8已知問題
description: 最新促銷活動版本中的已知問題
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 1b88ca57858efbfec6467452677620d59e9c9e32
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# 已知問題{#known-issues}

此頁列出了在 **最新市場活動v8版本**。 此外，還列出了市場活動v8的限制 [此頁](known-limitations.md)。


>[!NOTE]
>
>Adobe自行發佈已知問題清單。 它基於客戶報告的數量、嚴重性和變通辦法的可用性。 如果未列出您遇到的問題，則可能不符合此頁中發佈的條件。

## 更改資料源活動問題 {#issue-1}

### 說明{#issue-1-desc}

的 **更改資料源** 活動在將資料從Campagint本地資料庫傳輸到Snowflake雲資料庫時失敗。 在切換方向時，活動會產生問題。

### 複製步驟{#issue-1-repro}

1. 連接到客戶端控制台並建立工作流。
1. 添加 **查詢** 活動和 **更改資料源** 的子菜單。
1. 在 **電子郵件**，即字串。
1. 運行工作流並按一下右鍵該過渡以查看填充：電子郵件記錄顯示為 `****`。
1. 檢查工作流日誌：這樣 **更改資料源** 活動將這些記錄解釋為數值。

### 錯誤消息{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### 解決方法{#issue-1-workaround}

要將資料從Snowflake雲資料庫傳輸到市場活動本地資料庫並返回Snowflake，必須使用兩種不同的 **更改資料源** 活動。

### 內部引用{#issue-1-ref}

參考：NEO-45549



## 由於反斜線，更改資料源活動失敗 {#issue-2}

### 說明{#issue-2-desc}

將資料注入Snowflake雲資料庫時 **查詢** 和 **更改資料源** 活動，當資料中存在反斜線字元時，進程將失敗。 源字串未轉義，資料未在Snowflake上正確處理。

僅當反斜槓字元位於字串末尾時，才會出現此問題，例如： `Barker\`。


### 複製步驟{#issue-2-repro}

1. 連接到客戶端控制台並建立工作流。
1. 添加 **查詢** 並配置。
1. 選擇具有上述特徵的資料。
1. 添加 **更改資料源** 活動，並將其配置為選擇Snowflake雲資料庫。
1. 運行工作流並檢查工作流日誌以查看錯誤。


### 錯誤消息{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### 解決方法{#issue-2-workaround}

作為一種解決方法，請在有問題的值周圍導出帶雙引號的檔案(如 `Barker\`)並包含檔案格式選項 `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`。

### 內部引用{#issue-2-ref}

參考：NEO-45549


## 資料載入（檔案）活動無法在伺服器上上載檔案 {#issue-3}

### 說明{#issue-3-desc}

將檔案上載到市場活動伺服器上時 **資料載入（檔案）** 活動，該進程將在100%停止，但永不結束。

### 複製步驟{#issue-3-repro}

1. 連接到客戶端控制台並建立工作流。
1. 添加 **資料載入（檔案）** 並配置。
1. 選擇 **在伺服器上上載** 的雙曲餘切值。
1. 選擇本地電腦上的檔案，
1. 按一下 **上載**


### 錯誤消息{#issue-3-error}

這個過程永遠不會結束。

### 解決方法{#issue-3-workaround}

無

### 內部引用{#issue-3-ref}

參考：NEO-47269