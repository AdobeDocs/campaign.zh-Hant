---
product: campaign
title: 開始工作流程
description: 瞭解如何啟動工作流程，以及探索工作流程動作工具列和滑鼠右鍵功能表
feature: Workflows
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# 開始工作流程 {#starting-a-workflow}

工作流程一律以手動方式啟動。 然而，啟動後，它會根據透過排程器指定的資訊保持非使用中(請參閱 [排程器](scheduler.md))或活動排程。

與目標工作流程執行相關的動作（啟動、停止、暫停等） 是 **非同步** 處理序：訂單會記錄下來，並在伺服器可供套用時立即生效。

工具列可讓您啟動及追蹤工作流程的執行。

中可用的選項清單 **[!UICONTROL Actions]** 功能表和右鍵功能表詳述如下。

>[!IMPORTANT]
>
>請記住，當運運算元在工作流程上執行動作（開始、停止、暫停等）時，該動作不會立即執行，而是放置在佇列中以便由工作流程模組處理。

## 動作工具列 {#actions-toolbar}

此 **[!UICONTROL Actions]** 工具列的按鈕可讓您存取所選工作流程的其他執行選項。 您也可以使用 **[!UICONTROL File > Actions]** 功能表，或以滑鼠右鍵按一下工作流程並選取 **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

   此動作可讓您開始執行工作流程：此工作流程已 **已完成**， **正在編輯** 或 **已暫停** 將狀態更改為 **已開始**. 然後，工作流程引擎會處理此工作流程的執行。 如果工作流程已暫停，則會繼續進行，否則會從頭開始工作流程並啟動初始活動。

   啟動為非同步流程：系統會儲存請求，並儘快由工作流程伺服器處理。

* **[!UICONTROL Pause]**

   此動作會將工作流程的狀態設為 **已暫停**. 在繼續工作流程之前，不會啟用任何活動，但不會暫停進行中的作業。

* **[!UICONTROL Stop]**

   此動作會停止目前正在執行的工作流程。 執行個體的狀態設定為 **已完成**. 如果可能的話，進行中的作業會停止。 匯入和SQL查詢會立即取消。

   >[!IMPORTANT]
   >
   >停止工作流程為非同步程式：要求已註冊，然後工作流程伺服器取消正在進行的操作。 因此，停止工作流程例項可能需要一些時間，尤其是當工作流程正在多個伺服器上執行時，每個伺服器都必須取得控制權，才能取消進行中的工作。 為避免任何問題，請等待停止操作完成，並且不要在同一工作流程上執行多個停止請求。

* **[!UICONTROL Restart]**

   此動作會停止，然後重新啟動工作流程。 在大多數情況下，可以更快速地重新啟動。 當停止需要一定的時間時，自動重新啟動也很實用：這是因為當工作流程停止時，「停止」命令無法使用。

* **[!UICONTROL Purge history]**

   此動作可讓您清除工作流程歷史記錄。 有關詳細資訊，請參閱 [清除記錄](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

   此選項可讓您以模擬模式而非實際模式啟動工作流程。 這表示當您啟用此模式時，只會執行不會影響資料庫或檔案系統的活動(例如 **[!UICONTROL Query]**， **[!UICONTROL Union]**， **[!UICONTROL Intersection]**、等)。 有影響的活動(例如 **[!UICONTROL Export]**， **[!UICONTROL Import]**、等) 以及之後的專案（在相同分支中）都不會執行。

* **[!UICONTROL Execute pending tasks now]**

   此動作可讓您儘快啟動所有擱置中的任務。 若要啟動特定任務，請以滑鼠右鍵按一下其活動並選取 **[!UICONTROL Execute pending task(s) now]**.

* **[!UICONTROL Unconditional stop]**

   此選項會將工作流程狀態變更為 **[!UICONTROL Finished]**. 此動作僅應在正常停止程式在幾分鐘後失敗時作為最後手段使用。 只有在您確定沒有進行中的實際工作流程工作時，才使用無條件停止。

   >[!CAUTION]
   >
   >此選項為專家使用者保留。

* **[!UICONTROL Save as template]**

   此動作會根據所選的工作流程建立新的工作流程範本。 您必須指定儲存該檔案的資料夾(在 **[!UICONTROL Folder]** 欄位)。

## 在功能表上按一下右鍵 {#right-click-menu}

選取一或多個工作流程活動時，您可以按一下滑鼠右鍵以按一下您的選取專案執行動作。

![](assets/contextual_menu.png)

在右鍵功能表中提供下列選項：

**[!UICONTROL Open]**：此選項可讓您存取活動屬性。

**[!UICONTROL Display logs:]** 此選項可讓您檢視所選活動的任務執行記錄。 請參閱 [顯示記錄](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** 此動作可讓您儘快開始擱置中的任務。

**[!UICONTROL Workflow restart from a task:]** 此選項可讓您使用先前為此活動儲存的結果來重新啟動工作流程。

**[!UICONTROL Cut/Copy/Paste/Delete:]** 這些選項可讓您剪下、複製、貼上和刪除活動。

**[!UICONTROL Copy as bitmap:]** 此選項可讓您擷取所有活動的熒幕擷圖。

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** 這些選項也適用於 **[!UICONTROL Advanced]** 活動屬性的索引標籤。 如需詳細資訊，請參閱 [執行](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** 可讓您儲存或取消對工作流程所做的變更。

>[!NOTE]
>
>您可以選取一組活動，然後將其中一個命令套用至這些活動。

