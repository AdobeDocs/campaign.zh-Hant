---
title: Campaign中的金鑰管理
description: 開始使用金鑰管理
feature: FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# 金鑰管理和唯一性 {#key-management}

在的內容中 [企業(FFDA)部署](enterprise-deployment.md)，主索引鍵是通用唯一識別碼(UUID)，這是字元上的字串。 若要建立此UUID，結構描述的主要元素必須包含 **autouid** 和 **autopk** 屬性設定為 **true**.

Adobe Campaign v8使用 [!DNL Snowflake] 作為核心資料庫。 分散式架構 [!DNL Snowflake] 資料庫不提供機制來確保表格中索引鍵的唯一性：終端使用者需負責Adobe Campaign資料庫中的索引鍵一致性。

若要保持關聯式資料庫的一致性，必須避免索引鍵上的重複專案，尤其是主索引鍵上的重複專案。 主索引鍵上的重複專案會導致資料管理工作流程活動(例如 **查詢**， **調解**， **更新資料**、等等。 這對於在更新時定義適當的調解標準至關重要 [!DNL Snowflake] 表格。


>[!CAUTION]
>
>重複的金鑰不限於UUID。 這可能發生在具有ID中，包括在自訂表格中建立的自訂金鑰。


## Unicity Service{#unicity-service}

Unicity Service是Cloud Database Manager元件，可協助使用者保留和監控雲端資料庫表格中唯一關鍵值限制的完整性。 這可讓您降低插入重複金鑰的風險。

由於Cloud Database不強制執行unicity限制，Unicity Service減少了使用Adobe Campaign管理資料時插入重複專案的風險。

### 唯一性工作流程{#unicity-wf}

Unicity Service隨附專屬的 **[!UICONTROL Unicity alerting]** 內建工作流程，可監視單向性限制，並在偵測到重複專案時發出警報。

此技術工作流程可從以下網址取得： **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** Campaign Explorer節點。 **不可修改**.

此工作流程會檢查所有自訂和內建的結構描述，以偵測重複的列。

![](assets/unicity-alerting-wf.png)

如果 **[!UICONTROL Unicity alerting]** (ffdaUnicity)工作流程會偵測到一些重複的索引鍵，這些索引鍵會新增至特定 **稽核唯一性** 表格，其中包含結構描述名稱、索引鍵型別、受影響的列數和日期。 您可以從「 」存取重複的金鑰 **[!UICONTROL Administration > Audit > Key Unicity]** 節點。

![](assets/unicity-table.png)

身為資料庫管理員，您可以使用SQL活動來移除重複專案，或聯絡Adobe客戶服務以取得更多指引。

### 警報{#unicity-wf-alerting}

特定通知會傳送至 **[!UICONTROL Workflow Supervisors]** 偵測到重複的索引鍵時所使用的運運算元群組。 此警報的內容和對象可在以下位置變更： **警報** 的活動 **[!UICONTROL Unicity alerting]** 工作流程。

![](assets/wf-alert-activity.png)


## 其他護欄{#duplicates-guardrails}

Campaign隨附一組新護欄，以防止在中插入重複的索引鍵 [!DNL Snowflake] 資料庫。

>[!NOTE]
>
>從Campaign v8.3開始提供這些護欄。若要檢查您的版本，請參閱 [本節](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### 傳遞準備{#remove-duplicates-delivery-preparation}

Adobe Campaign會在傳送準備期間自動從對象中移除任何重複的UUID。 此機制可防止在準備傳送時發生任何錯誤。 身為一般使用者，您可以在傳送記錄中檢查此資訊：由於金鑰重複，某些收件者可從主要目標中排除。 在這種情況下，會顯示下列警告： `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### 更新工作流程中的資料{#duplicates-update-data}

在的內容中 [企業(FFDA)部署](enterprise-deployment.md)，您無法選取內部金鑰(UUID)作為欄位來更新工作流程中的資料。

![](assets/update-data-no-internal-key.png)

使用明確調解金鑰時， **更新資料** 活動會根據此索引鍵自動確保目的地結構描述的唯一性，方法是：

1. 刪除傳入資料的重複資料（從轉變）
1. 使用目的地表格刪除重複資料（合併）


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>此護欄僅適用於option **[!UICONTROL Using reconciliation keys]**.


### 查詢包含重複專案的結構描述{#query-with-duplicates}

當工作流程開始在結構描述上執行查詢時，Adobe Campaign會檢查中是否報告了任何重複記錄 [稽核唯一性表格](#unicity-wf). 若是如此，工作流程會記錄警告，因為對重複資料的後續操作應可能會影響工作流程結果。

![](assets/query-with-duplicates.png)

此檢查會在下列工作流程活動中執行：

* 查詢
* 增量查詢
* 讀取清單