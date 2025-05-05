---
title: Campaign v8已知問題
description: 最新Campaign版本中的已知問題
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# 已知問題{#known-issues}

此頁面列出&#x200B;**最新Campaign v8版本**&#x200B;中發現的已知問題。 此外，Campaign v8的限制[已列於本頁](ac-guardrails.md)。


>[!NOTE]
>
>Adobe會自行發佈這份已知問題清單。 這會根據客戶報告的數量、嚴重程度以及因應措施的可用性。 如果您遇到的問題未列出，表示它可能不符合此頁面發佈的條件。

## Campaign v8.3.8{#8.3-issues}

### 變更資料Source活動問題 {#issue-2}

#### 說明{#issue-2-desc}

當使用Campaign **查詢**&#x200B;和&#x200B;**變更資料Source**&#x200B;活動將資料插入Snowflake雲端資料庫時，當資料中出現反斜線字元時，流程會失敗。 來源字串未逸出，且資料在Snowflake時未正確處理。

只有反斜線字元位於字串結尾時，才會發生此問題，例如： `Barker\`。


#### 重製步驟{#issue-2-repro}

1. 連線至使用者端主控台並建立工作流程。
1. 新增&#x200B;**查詢**&#x200B;活動並加以設定。
1. 選取具有上述特性的資料。
1. 新增&#x200B;**變更資料Source**&#x200B;活動，並將其設定為選取Snowflake雲端資料庫。
1. 執行工作流程並檢查工作流程記錄檔以檢視錯誤。


#### 錯誤訊息{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### 因應措施{#issue-2-workaround}

解決方法是排除字串結尾含有反斜線字元的資料，或是從來源檔案中移除該資料。


#### 內部參考{#issue-2-ref}

參考資料： NEO-45549


### 資料載入（檔案）活動無法在伺服器上傳檔案 {#issue-3}

#### 說明{#issue-3-desc}

在具有&#x200B;**資料載入（檔案）**&#x200B;活動的Campaign伺服器上傳檔案時，處理程式會在100%停止，但永不結束。

#### 重製步驟{#issue-3-repro}

1. 連線至使用者端主控台並建立工作流程。
1. 新增&#x200B;**資料載入（檔案）**&#x200B;活動並加以設定。
1. 選取&#x200B;**在伺服器**&#x200B;上載選項。
1. 選取本機電腦上的檔案，
1. 按一下&#x200B;**上傳**


#### 錯誤訊息{#issue-3-error}

此程式永遠不會結束。

#### 因應措施{#issue-3-workaround}

因應措施是使用舊版使用者端主控台。 然後，您就可以將檔案上傳至伺服器。

身為Campaign管理員，您可以在[Adobe軟體發佈](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}中下載Campaign v8.3.1使用者端主控台。

在此頁面[&#128279;](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hant){target="_blank"}瞭解如何存取Adobe軟體發佈。

在本頁[&#128279;](connect.md)瞭解如何升級您的使用者端主控台

#### 內部參考{#issue-3-ref}

參考資料： NEO-47269

