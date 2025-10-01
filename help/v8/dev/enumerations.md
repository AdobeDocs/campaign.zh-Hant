---
title: 管理列舉
description: 瞭解如何使用分項清單
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# 管理列舉 {#manage-enumerations}

分項清單（也稱為分項清單）是預先定義的值清單，可用於填寫某些欄位。 列舉有助於標準化欄位值，使資料輸入更一致並簡化查詢。

值可用時，會顯示在下拉式清單中。 您可以直接選取值或開始輸入 — 預測輸入會建議符合的值，並自動完成這些值。

![](assets/enum_values.png)

有些主控台欄位已設定分項清單。 如果列舉是&#x200B;**開啟**，您也可以直接在欄位中新增值。

## 存取分項清單

這些欄位中使用的值會集中管理。 您可以在&#x200B;**管理** `>` **平台** `>` **分項清單**&#x200B;下的Explorer樹狀結構中，新增、編輯、更新或刪除這些專案。

* 上方區段提供已定義分項清單的欄位清單。
* 下方的區段會列出可用的值。

當分項清單為&#x200B;**[!UICONTROL Open]**&#x200B;時，使用者可以直接在使用者介面的對應欄位中輸入新值。

當分項清單為&#x200B;**[!UICONTROL Closed]**&#x200B;時，只能從&#x200B;**分項清單**&#x200B;功能表新增值。

## 新增值

若要建立新的分項清單值，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。

![](assets/enumeration_screen.png)

輸入值的標籤。


## 別名清除 {#alias-cleansing}

在列舉欄位中，您可以輸入列舉值以外的值。 這些檔案可依原樣儲存，也可加以清除。

>[!CAUTION]
>
>資料清除是影響資料庫中資料的重要程式。 Adobe Campaign會執行大量資料更新，這可能會導致某些值被刪除。 因此，這項作業將保留給專家使用者。

然後輸入的值會是：

* 已新增至專案清單值：在此情況下，必須選取&#x200B;**[!UICONTROL Open]**&#x200B;選項，
* 或自動取代為其對應的別名：在此情況下，必須在分項清單的&#x200B;**[!UICONTROL Alias]**&#x200B;索引標籤中定義此案例，
* 或會儲存在別名清單中：稍後會指派別名。

### 建立別名 {#creating-an-alias}

選項&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;可以針對選取的逐項清單使用別名。 選取此選項時，**[!UICONTROL Alias]**&#x200B;索引標籤會顯示在視窗底部。

若要建立別名，請執行下列步驟：

1. 瀏覽到要更新的分項清單，然後按一下&#x200B;**[!UICONTROL Add]**。

   ![](assets/enumeration_alias_create.png)

1. 輸入您要轉換的別名以及要套用的值，然後按一下&#x200B;**[!UICONTROL Ok]**。

1. 確認此作業之前請先檢查引數。

>[!CAUTION]
>
>確認此步驟後，可能無法復原先前的值：系統將取代這些值。

因此，當使用者在「公司」欄位(在Adobe Campaign主控台或表單中)中輸入值&#x200B;**NEILSEN**&#x200B;時，該值會自動被值&#x200B;**NIELSEN Ltd**&#x200B;取代。 值取代是由&#x200B;**別名清除**&#x200B;工作流程執行。 請參閱[執行資料清除](#running-data-cleansing)。

![](assets/enumeration_alias_use.png)

### 將值轉換為別名 {#values-into-aliases}

您可以將現有值轉換為別名。 若要執行此動作，請依照下列步驟執行：

1. 在值清單中按一下滑鼠右鍵，然後選擇&#x200B;**[!UICONTROL Convert values into aliases...]**。

1. 選擇要轉換的值並按一下&#x200B;**[!UICONTROL Next]**。

1. 按一下&#x200B;**[!UICONTROL Start]**&#x200B;以執行轉換。

執行完成後，別名會新增至別名清單中。

### 擷取別名點選 {#alias-hits}

當使用者輸入未包含在列舉中的值時，它們會儲存在&#x200B;**[!UICONTROL Alias]**&#x200B;索引標籤中。

**別名清除**&#x200B;技術工作流程每晚都會復原這些值，以更新分項清單。 請參閱[執行資料清除](#running-data-cleansing)

如有需要，**[!UICONTROL Hits]**&#x200B;欄會顯示輸入此值的次數。 但是，計算這個值可能既費時又費記憶體。 如需詳細資訊，請參閱[計算專案發生次數](#calculating-entry-occurrences)。

### 執行資料清除 {#run-data-cleansing}

資料清除是由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技術工作流程執行。 為執行期間會套用為列舉定義的設定。 請參閱[別名清除工作流程](#alias-cleansing-workflow)。

可透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結觸發清除。

**[!UICONTROL Advanced parameters...]**&#x200B;連結可讓您設定開始考慮所收集值的日期。

按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕以執行資料清除。

### 計算專案發生次數 {#entry-occurrences}

逐項清單的&#x200B;**[!UICONTROL Alias]**&#x200B;子索引標籤可顯示輸入的所有值中別名的發生次數。 此資訊為預估值，會顯示在&#x200B;**[!UICONTROL Hits]**&#x200B;欄中。

>[!CAUTION]
>
>計算別名專案發生次數可能需要很長的時間。 因此使用此函式時請務必謹慎。

您可以透過&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;連結手動執行點選計算。 若要這麼做，請按一下&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;連結，然後選取所要的選項。

* **[!UICONTROL Update the number of alias hits]**：這可讓您根據輸入的日期，更新已計算的點選。
* **[!UICONTROL Recalculate the number of alias hits from the start]**：可讓您在整個Adobe Campaign平台上執行計算。

您也可以建立專屬的工作流程，讓計算在指定的期間內自動執行（例如每週執行一次）。

若要這麼做，請建立&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;工作流程的復本、變更排程器，並在&#x200B;**[!UICONTROL Enumeration value cleansing]**&#x200B;活動中使用下列設定：

* **-updateHits**&#x200B;以更新別名點選數，
* **-updateHits:full**&#x200B;以重新計算所有別名點選。

### 別名清除工作流程 {#alias-cleansing-workflow}

**別名清除**&#x200B;工作流程會執行列舉值清除。 預設會每天執行。

可透過&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;節點存取它。


