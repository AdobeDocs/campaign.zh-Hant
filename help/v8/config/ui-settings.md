---
title: Campaign介面設定
description: 了解如何自訂Campaign介面設定
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 0b4483e0f16f14582a1a4bc28b0e1ff719823ef3
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Campaign使用者介面設定 {#ui-settings}

## 分項清單 {#enumerations}

列舉（也稱為「分項清單」）是系統建議填入欄位的值清單。 使用枚舉來標準化這些欄位的值，幫助輸入資料或在查詢內使用。

值清單會顯示為下拉式清單，您可從中選取要在欄位中輸入的值。 下拉式清單也會啟用預測性輸入：輸入第一個字母，應用程式填入其餘字母。

會定義此類型欄位的值，並透過 **[!UICONTROL Administration > Platform > Enumerations]** 樹的節點。

![訪問枚舉](assets/enumerations-menu.png)

### 枚舉類型 {#types-of-enum}

枚舉儲存在 **[!UICONTROL Administration > Platform > Enumerations]** 檔案總管的資料夾。

可以是：開啟、系統、表情符號或關閉。

* 安 **開啟** 分項清單可讓使用者根據這項分項清單，直接在欄位中新增值。
* A **已關閉** 枚舉具有固定的值清單，只能從 **[!UICONTROL Administration > Platform > Enumerations]** 檔案總管的資料夾。
* 安 **表情符號** 枚舉用於更新表情符號清單。 了解更多
* A **系統** 枚舉與系統欄位相關聯，且具有內部名稱。

針對 **開啟** 和 **已關閉** 列舉，可使用特定選項：

* **簡單枚舉** 是預設的標準類型。
* **別名清除** 枚舉用於協調儲存在資料庫中的枚舉值。 [了解更多](#alias-cleansing)
* **保留為綁定** 是一個選項，可讓您將多維資料集值連結到此枚舉。 [了解更多](../reporting/gs-cubes.md)


### 別名清除 {#alias-cleansing}

在列舉欄位中，您可以選取值，或輸入下拉式清單中無法使用的自訂值。 可將自訂值新增至現有的列舉值，作為新的值 — 在此例中， **[!UICONTROL Open]** 選項。 可以使用別名清除功能來清除這些自訂值。 例如，如果使用者輸入 `Adob` 而非 `Adobe`，別名清除程式可以自動以正確的詞取代。

>[!CAUTION]
>
>資料清理是影響資料庫中資料的關鍵過程。 Adobe Campaign會執行大量資料更新，而可能導致某些值遭刪除。 因此，此操作將保留給專家用戶。

啟用 **[!UICONTROL Alias cleansing]** 選項來對分項清單使用資料清除功能。 選取此選項時， **[!UICONTROL Alias]** 頁簽。

當用戶輸入別名清除枚舉中不存在的值時，該值將添加到 **值** 清單。 您可以 [從這些值建立別名](#convert-to-alias)，或 [從頭建立新別名](#create-alias).

#### 建立別名{#create-alias}

要建立別名，請執行以下步驟：

1. 按一下 **[!UICONTROL Add]** 按鈕 **[!UICONTROL Alias]** 標籤。
1. 輸入要轉換的別名，然後在下拉式清單中選取要套用的值。

   ![建立新別名](assets/new-alias.png)

1. 按一下 **[!UICONTROL Ok]** 並確認。

1. 儲存您的變更。值的取代由 **別名清除** 每晚執行的工作流程。 請參閱 [執行資料清理](#running-data-cleansing).

針對此列舉的所有欄位，當使用者輸入值時 **Adobe** 在「公司」欄位(在Adobe Campaign主控台中，在Web表單中)中，會自動取代為值 **Adobe**.

#### 將錯誤的值轉換為別名{#convert-to-alias}

您也可以將現有的分項清單值轉換為別名。 若要執行此動作：

1. 在枚舉的值清單中，按一下右鍵並瀏覽到 **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![將值轉換為別名](assets/convert-into-aliases.png)

1. 選擇要以別名轉換的值，然後按一下 **[!UICONTROL Next]**.
1. 按一下 **[!UICONTROL Start]** 來執行轉換。

   執行完成後，別名會新增至清單，位於 **別名** 標籤。 您可以關聯正確值以替換錯誤的條目。 若要執行此動作：

1. 選取要清除的值。
1. 按一下 **細節……** 按鈕。
1. 在下拉式清單中選取新值。

   ![建立新別名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以在 **[!UICONTROL Hits]** 欄中 **[!UICONTROL Alias]** 頁簽。 它可顯示輸入此值的次數。  [了解更多資訊](#calculate-entry-occurrences)。

#### 執行資料清理 {#running-data-cleansing}

資料清除由 **[!UICONTROL Alias cleansing]** 技術工作流程。 預設會每天執行。

清除也可透過 **[!UICONTROL Cleanse values...]** 連結。

此 **[!UICONTROL Advanced parameters...]** 連結可讓您設定從開始將收集的值納入考量的日期。

按一下 **[!UICONTROL Start]** 按鈕來執行資料清除。

##### 監視發生次數 {#calculate-entry-occurrences}

此 **[!UICONTROL Alias]** 枚舉的子頁簽可以顯示輸入的所有值中別名的發生次數。 此資訊為預估值，將顯示在 **[!UICONTROL Hits]** 欄。

>[!CAUTION]
>
>計算別名條目發生次數可能需要很長時間。

您可以透過 **[!UICONTROL Cleanse values...]** 連結。 若要這麼做，請按一下 **[!UICONTROL Advanced parameters...]** 連結並選取選項。

* **[!UICONTROL Update the number of alias hits]**:這可讓您根據輸入的日期更新已計算的點擊。
* **[!UICONTROL Recalculate the number of alias hits from the start]**:可讓您在整個Adobe Campaign平台上執行計算。

您也可以建立專用的工作流程，以便計算在指定期間自動執行，例如每週執行一次。

若要這麼做，請建立 **[!UICONTROL Alias cleansing]** 工作流程，請變更排程器，並在 **[!UICONTROL Enumeration value cleansing]** 活動：

* **-updateHits** 若要更新別名點擊數，
* **-updateHits:full** 重新計算所有別名點擊。
