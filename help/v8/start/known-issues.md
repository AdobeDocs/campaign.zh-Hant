---
title: 市場活動v8已知問題
description: 最新促銷活動版本中的已知問題
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 9ae93ce4e2b0424bb3b3862b2c7d016309bd630e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# 已知問題{#known-issues}

此頁列出了在 **最新市場活動v8版本**。 此外，還列出了市場活動v8的限制 [此頁](ac-guardrails.md)。


>[!NOTE]
>
>Adobe自行發佈已知問題清單。 它基於客戶報告的數量、嚴重性和變通辦法的可用性。 如果未列出您遇到的問題，則可能不符合此頁中發佈的條件。

## Campaign v8.3.8{#8.3-issues}

### 更改資料源活動問題 {#issue-2}

#### 說明{#issue-2-desc}

將資料注入Snowflake雲資料庫時 **查詢** 和 **更改資料源** 活動，當資料中存在反斜線字元時，進程將失敗。 源字串未轉義，資料未在Snowflake上正確處理。

僅當反斜槓字元位於字串末尾時，才會出現此問題，例如： `Barker\`。


#### 複製步驟{#issue-2-repro}

1. 連接到客戶端控制台並建立工作流。
1. 添加 **查詢** 並配置。
1. 選擇具有上述特徵的資料。
1. 添加 **更改資料源** 活動，並將其配置為選擇Snowflake雲資料庫。
1. 運行工作流並檢查工作流日誌以查看錯誤。


#### 錯誤訊息{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### 解決方法{#issue-2-workaround}

解決方法是排除字串結尾處包含反斜線字元的資料，或將其從源檔案中刪除。


#### 內部引用{#issue-2-ref}

參考：NEO-45549


### 資料載入（檔案）活動無法在伺服器上上載檔案 {#issue-3}

#### 說明{#issue-3-desc}

將檔案上載到市場活動伺服器上時 **資料載入（檔案）** 活動，該進程將在100%停止，但永不結束。

#### 複製步驟{#issue-3-repro}

1. 連接到客戶端控制台並建立工作流。
1. 添加 **資料載入（檔案）** 並配置。
1. 選擇 **在伺服器上上載** 的雙曲餘切值。
1. 選擇本地電腦上的檔案，
1. 按一下 **上載**


#### 錯誤訊息{#issue-3-error}

這個過程永遠不會結束。

#### 解決方法{#issue-3-workaround}

解決方法是使用較舊的客戶端控制台。 然後，您就可以在伺服器上上載該檔案。

作為市場活動管理員，您可以在下載市場活動v8.3.1客戶端控制台 [Adobe軟體分發](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3內容%2Fmetadata%2Fdc%3Rast&amp;1_group.propertyvalues.operation=等於&amp;1_group.propertyvalues.0_values=目標版本%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModifiedModied&amp;ordModied&amp;OrdSed&amp;Sed&amp;St.st&amp;St&amp;Sor&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}。

瞭解如何訪問Adobe軟體分發 [此頁](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hant){target="_blank"}。

瞭解如何升級客戶端控制台 [此頁](connect.md)

#### 內部引用{#issue-3-ref}

參考：NEO-47269

