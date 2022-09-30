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

在 [企業(FFDA)部署](enterprise-deployment.md)，主要索引鍵為通用唯一IDentifier(UUID)，此為字元字串。 若要建立此UUID，架構的主要元素必須包含 **autouuid** 和 **奧托普** 設定為 **true**.

Adobe Campaign v8使用 [!DNL Snowflake] 作為核心資料庫。 的分散式架構 [!DNL Snowflake] 資料庫不提供確保表中密鑰的唯一性的機制：一般使用者需負責Adobe Campaign資料庫內的關鍵一致性。

要保持關係資料庫的一致性，必須避免對密鑰（尤其是主密鑰）重複。 主要金鑰上的重複項目會導致資料管理工作流程活動發生問題，例如 **查詢**, **調解**, **更新資料**、等。 在更新時定義正確調解標準的關鍵 [!DNL Snowflake] 表格。


>[!CAUTION]
>
>重複的鍵不限於UUID。 ID中可能會發生此情況，包括在自訂表格中建立的自訂索引鍵。


## Unicity Service{#unicity-service}

Unicity Service是雲資料庫管理器元件，可幫助用戶保留和監視雲資料庫表內唯一關鍵約束的完整性。 這可讓您降低插入重複金鑰的風險。

由於雲端資料庫不強制執行非重複性限制，Unicity Service可降低使用Adobe Campaign管理資料時插入重複項的風險。

### 唯一性工作流程{#unicity-wf}

Unicity Service隨附專用 **[!UICONTROL Unicity alerting]** 內建的工作流程，可監控唯一性限制，並在偵測到重複項目時發出警報。

此技術工作流程可從 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** 行銷活動總管的節點。 **不得修改**.

此工作流程會檢查所有自訂和內建結構，以偵測重複的列。

![](assets/unicity-alerting-wf.png)

若 **[!UICONTROL Unicity alerting]** (ffdaUnicity)工作流程會偵測某些重複金鑰，並將其新增至特定 **審核唯一性** 表格，包括結構名稱、索引鍵類型、受影響列數和日期。 您可以從 **[!UICONTROL Administration > Audit > Key Unicity]** 節點。

![](assets/unicity-table.png)

身為資料庫管理員，您可以使用SQL活動來移除重複項目，或聯絡Adobe客戶服務以取得詳細指引。

### 警報{#unicity-wf-alerting}

特定通知會傳送至 **[!UICONTROL Workflow Supervisors]** 運算子組。 此警報的內容和對象可在 **警報** 活動 **[!UICONTROL Unicity alerting]** 工作流程。

![](assets/wf-alert-activity.png)


## 其他護欄{#duplicates-guardrails}

Campaign隨附一組新護欄，以防止在 [!DNL Snowflake] 資料庫。

>[!NOTE]
>
>這些護欄可從Campaign v8.3開始使用。若要檢查您的版本，請參閱 [本節](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### 傳遞準備{#remove-duplicates-delivery-preparation}

Adobe Campaign會在準備傳送期間自動移除對象中任何重複的UUID。 此機制可防止在準備傳送時發生任何錯誤。 身為一般使用者，您可以在傳送記錄檔中檢查此資訊：由於重複的金鑰，某些收件者可能會從主要目標中排除。 在這種情況下，會顯示下列警告： `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### 更新工作流程中的資料{#duplicates-update-data}

在 [企業(FFDA)部署](enterprise-deployment.md)，您無法選取內部索引鍵(UUID)作為欄位，以更新工作流程中的資料。

![](assets/update-data-no-internal-key.png)

使用明確調解金鑰時， **更新資料** 活動會依照下列項目，自動確保目標架構的不重複性：

1. 重複刪除傳入資料（從轉換）
1. 使用目標表重複刪除資料（合併）


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>此護欄僅適用於選項 **[!UICONTROL Using reconciliation keys]**.


### 查詢具有重複項的架構{#query-with-duplicates}

當工作流程開始對結構執行查詢時，Adobe Campaign會檢查 [審核唯一性表](#unicity-wf). 如果是，工作流程會記錄警告，因為重複資料的後續操作可能會影響工作流程結果。

![](assets/query-with-duplicates.png)

此檢查會在下列工作流程活動中執行：

* 查詢
* 增量查詢
* 讀取清單