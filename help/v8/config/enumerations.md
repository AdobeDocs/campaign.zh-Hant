---
title: 管理列舉
description: 瞭解如何使用分項清單
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: a1f479538a2d93a2ec13e35cb6813e09c8c4a5f8
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# 使用分項清單 {#enumerations}

分項清單（也稱為分項清單）是預先定義的值清單，可用於填寫某些欄位。 列舉有助於標準化欄位值，使資料輸入更一致並簡化查詢。

定義後，值會顯示在下拉式清單中。 您可以直接選取值，或使用預測性輸入來輸入值，這會建議並完成相符專案。 某些欄位包含預先定義的分項清單，如果需要，可以建立其他分項清單。

![](assets/enum_values.png)


## 分項清單的型別 {#types-of-enum}

列舉儲存在檔案總管的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;資料夾中。

![存取分項清單](../config/assets/enumerations-menu.png)


列舉可以是： **開啟**、**系統**、**表情符號**&#x200B;或&#x200B;**已關閉**。

* **Open**&#x200B;列舉允許使用者根據此列舉直接在欄位中新增值。
* **已關閉的**&#x200B;列舉具有只能從總管的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;資料夾修改的固定值清單。
* 使用&#x200B;**表情符號**&#x200B;列舉來更新表情符號清單。 了解更多
* **系統**&#x200B;列舉與系統欄位相關聯，而且帶有內部名稱。

對於&#x200B;**開啟**&#x200B;和&#x200B;**關閉**&#x200B;列舉，可以使用特定選項：

* **簡單列舉**&#x200B;是預設的標準型別。
* **別名清除**&#x200B;列舉是用來協調資料庫中儲存的列舉值。 [了解更多](#alias-cleansing)
* **保留給量化**&#x200B;是一個可讓您將Cube值連結到這個列舉的選項。 [了解更多](../reporting/gs-cubes.md)


## 別名清除 {#alias-cleansing}

在列舉欄位中，可以從下拉式清單中選取值，如果清單中沒有值，則可以手動輸入。 啟用&#x200B;**[!UICONTROL Open]**&#x200B;選項時，可將自訂值新增至分項清單。 這些值稍後可以透過別名清除進行標準化，自動以正確的辭彙取代變數（例如，將`Adob`轉換為`Adobe`）。


>[!CAUTION]
>
>資料清除是影響資料庫值的關鍵作業。 Adobe Campaign會執行大量資料更新，因而刪除某些值。 這項作業僅適用於專家使用者。

啟用&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;選項以使用列舉的資料清除功能。 選取此選項時，**[!UICONTROL Alias]**&#x200B;索引標籤會顯示在視窗底部。

當使用者輸入的值不存在別名清除列舉中時，就會將其新增到&#x200B;**值**&#x200B;清單。 您可以[從這些值](#convert-to-alias)建立別名，或[從頭開始建立新別名](#create-alias)。

### 建立別名{#create-alias}

若要建立別名，請執行下列步驟：

1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Alias]**&#x200B;按鈕。
1. 輸入您要轉換的別名，然後在下拉式清單中選取要套用的值。

   ![建立新別名](assets/new-alias.png)

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;並確認。

1. 儲存您的變更。值取代是由每晚執行的&#x200B;**別名清理**&#x200B;工作流程所執行。 請參閱[執行資料清除](#running-data-cleansing)。

對於以此分項清單為基礎的所有欄位，當使用者在「公司」欄位中輸入值&#x200B;**Adobe** (在Adobe Campaign使用者端主控台中，以Web形式顯示)時，該值將自動被值&#x200B;**Adobe**&#x200B;取代。

### 將錯誤值轉換為別名{#convert-to-alias}

您也可以將現有的列舉值轉換為別名。 若要執行此動作：

1. 在列舉值清單中，按一下滑鼠右鍵並瀏覽至&#x200B;**[!UICONTROL Actions... > Convert values into aliases...]**。

   ![將值轉換為別名](assets/convert-into-aliases.png)

1. 選取要轉換為別名的值，然後按一下&#x200B;**[!UICONTROL Next]**。
1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;以執行轉換。

   執行完成後，別名會新增至&#x200B;**別名**&#x200B;索引標籤的清單中。 您可以關聯正確的值來取代錯誤的專案。 若要執行此動作：

1. 選取要清除的值。
1. 按一下&#x200B;**詳細資料……**&#x200B;按鈕。
1. 在下拉式清單中選取新值。

   ![建立新別名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以在&#x200B;**[!UICONTROL Hits]**&#x200B;子索引標籤的&#x200B;**[!UICONTROL Alias]**&#x200B;欄中追蹤別名的發生次數。 它可以顯示輸入此值的次數。  [了解更多](#calculate-entry-occurrences)。

### 執行資料清除 {#running-data-cleansing}

資料清除是由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技術工作流程執行。 預設會每天執行。

也可以透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結觸發清除。

**[!UICONTROL Advanced parameters...]**&#x200B;連結可讓您設定開始考慮所收集值的日期。

按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕以執行資料清除。

### 監視發生次數 {#calculate-entry-occurrences}

分項清單的&#x200B;**[!UICONTROL Alias]**&#x200B;子索引標籤可顯示輸入的所有值中別名的發生次數。 此資訊為預估值，會顯示在&#x200B;**[!UICONTROL Hits]**&#x200B;欄中。

>[!CAUTION]
>
>計算別名專案發生次數可能需要很長的時間。
>

您可以透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結手動執行點選計算。 若要這麼做，請按一下&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;連結並選取選項。

* **[!UICONTROL Update the number of alias hits]**：這可讓您根據輸入的日期，更新已計算的點選。
* **[!UICONTROL Recalculate the number of alias hits from the start]**：可讓您在整個Adobe Campaign平台上執行計算。

您也可以建立專屬的工作流程，讓計算在指定的期間內自動執行（例如每週執行一次）。

若要這麼做，請建立&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;工作流程的復本、變更排程器，並在&#x200B;**[!UICONTROL Enumeration value cleansing]**&#x200B;活動中使用下列設定：

* **-updateHits**&#x200B;以更新別名點選數，
* **-updateHits:full**&#x200B;以重新計算所有別名點選。
