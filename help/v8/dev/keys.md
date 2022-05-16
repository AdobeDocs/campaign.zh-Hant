---
title: 市場活動中的關鍵管理
description: 開始密鑰管理
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---

# 金鑰管理和唯一性 {#key-management}

在Campaign v8中，主鍵是通用唯一標識符(UUID)，它是字串。 要建立此UUID，架構的主元素必須包含 **autouuid** 和 **奧托普** 屬性設定為 **真**。

Adobe Campaign v8 以 Snowflake 作為核心資料庫。 Snowflake資料庫的分佈式體系結構沒有提供管理表中密鑰唯一性的機制：最終用戶負責確保Adobe Campaign資料庫中密鑰的一致性。

要保持關係資料庫一致性，必須避免在鍵上重複，尤其是在主鍵上重複。 主鍵上的重複導致資料管理工作流活動出現問題，如 **查詢**。 **協調**。 **更新資料**。

作為最佳做法，Adobe建議採用 [檢測](#detect-duplicates) 和 [正確](#correct-duplicates) 策略作為整個資料管理流程的一部分，以防重複的密鑰被載入到資料庫中。

## 檢測重複項{#detect-duplicates}

市場活動附帶了一個新的護欄，在交付準備期間自動從受眾中刪除任何重複的UUID。 此新機制可防止在準備傳遞時發生任何錯誤。

>[!CAUTION]
>
>重複的鍵不限於UUID。 可以在中使用ID（包括在自定義表中建立的自定義鍵）。

作為最終用戶，您可以在傳遞日誌中檢查以下資訊：由於密鑰重複，某些收件者可從主目標中排除。 在這種情況下，將顯示以下警告： `Exclusion of duplicates (based on the primary key or targeted records)`。

![](assets/delivery-log-duplicates.png)

發生此情況時，可以建立一個工作流來標識重複的鍵。 然後，您就能更正這些鍵。 要執行此操作，請執行以下步驟：

1. 建立新工作流。

   ![](assets/new-wf.png)

1. 添加 **查詢** 活動
1. 選擇 **收件人** 表

   ![](assets/add-query-on-rcp.png)

1. 添加 **重複資料消除** 在主鍵(UUID)上執行活動和重複資料消除。 只保留一個副本，然後檢查  **生成補碼** 選項，為重複項建立出站轉換。

   ![](assets/deduplicate.png)

1. 使用「清單」更新活動將重複項保存到清單中。

   ![](assets/list-update.png)

現在，您可以直接從清單訪問重複的收件人。 即使轉換只包含重複行之一，所有重複行都將記錄到清單中。


## 更正重複項{#correct-duplicates}

更正重複項要求客戶更新市場活動資料。 行動類型與重複項的性質和實施密切相關。 我們可能面臨多個需要不同緩解策略（刪除、合併或更新）的案例。

>[!IMPORTANT]
>
>重複的主鍵會阻止您使用內置工作流活動來選擇或更新特定行。 由於重複的UUID，重複資料消除將失敗，並可能影響資料庫完整性。 因此，強烈建議更正重複項。

例如：

* **案例1**  — 具有相同UUID和相同配置檔案資訊（相同電子郵件、名等）的重複收件人 :接收者看起來像「真實」重複項，緩解措施可能只是刪除其中一個重複項。
另一種方法是將一個接收方的資訊合併到另一個接收方。

* **案例2**  — 具有相同UUID但不同配置檔案資訊（不同的電子郵件、名等）的重複收件人:這次，似乎有不同的配置檔案，您可能希望將這兩個配置檔案都保留在市場活動資料庫中，這意味著我們可能更願意只更新其中一個重複項，生成新的UUID。 [在本示例中瞭解更多資訊](#deduplicate-sample)。

根據緩解策略，您始終可以從另一個工作流查詢清單，然後根據需要應用更新。 如需更多指導，請聯繫Adobe。

### 重複資料消除示例{#deduplicate-sample}

如果收件人重複，您可以在市場活動資料庫中保留這兩個記錄。 在這種情況下，您需要使用新的UUID更新其中一個UUID。

因此，要在雲資料庫上運行SQL更新查詢，可以使用 **SQL資料管理** 並執行以下SQL更新：

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

使用新的UUID更新選定行後，您就可以從介面檢查更新的行，並注意UUID已按預期方式更新。 還可以通過運行 **檢測重複項** 工作流 [如此解釋](#detect-duplicates)。
