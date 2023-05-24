---
product: campaign
title: 工作流程屬性
description: 進一步瞭解Campaign工作流程屬性
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 39%

---

# 工作流程屬性{#workflow-properties}



## 執行標籤 {#execution-tab}

此 **[!UICONTROL Execution]** 的標籤 **[!UICONTROL Properties]** 工作流程中的視窗分為3個區段：

![](assets/wf_execution_tab.png)

### 排程器 {#scheduler}

此區段只會顯示在行銷活動工作流程中。

* **[!UICONTROL Priority]**

   工作流程引擎會根據此欄位中定義的優先順序條件，處理要執行的工作流程。 例如，所有工作流程具有 **[!UICONTROL Average]** 優先順序會先於具有 **[!UICONTROL Low]** 優先順序。

* **[!UICONTROL Schedule execution for a time of low activity]**

   此選項會將工作流程開始時間延後至較不忙碌的期間。 某些工作流程可能需要耗費大量資料庫引擎資源。 我們建議將執行排程為活動較少的時間（例如，在晚上）。 低活動期間定義於 **[!UICONTROL Processes on campaigns]** 技術工作流程。

### 執行 {#execution}

* **[!UICONTROL Default affinity]**

   如果您的安裝包括多個工作流程伺服器，請使用此欄位選擇工作流程將在其中執行的電腦。如果在此欄位定義的值不存在於任何伺服器，工作流程將保持待處理狀態。

* **[!UICONTROL History in days]**

   資料庫的工作表會保留執行（任務、事件、記錄）的歷史記錄。 您可以在此處定義此工作流程的封存天數：清除程序會每天刪除一次最舊的封存檔。如果此欄位的值為零，則永遠不會刪除封存檔。

* **[!UICONTROL Log SQL queries in the journal]**

   此功能保留給進階使用者使用。它涉及包含目標定位活動 (查詢、聯合、交集等) 的工作流程。勾選此選項後，在工作流程執行期間傳送到資料庫的 SQL 查詢將顯示在 Adobe Campaign 中：這表示您可以分析它們以最佳化查詢或診斷問題。

   查詢會顯示在 **[!UICONTROL SQL logs]** 標籤，新增至工作流程（行銷活動工作流程除外）和 **[!UICONTROL Properties]** 活動。 此 **[!UICONTROL Audit]** 索引標籤也包含SQL查詢。

   ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

   此選項僅能用於偵錯，絕不能用於生產。 啟用時，工作流程會獲得優先順序，而所有其他工作流程會一直停止，直到此工作流程完成。

### 錯誤管理 {#error-management}

* **[!UICONTROL Troubleshooting]**

   此欄位可讓您定義工作流程的任務發生錯誤時要採取的動作。您有兩個選擇：

   * **[!UICONTROL Stop the process]**：工作流程會自動暫停。 工作流程狀態變更為 **[!UICONTROL Failed]**. 問題解決後，請使用重新啟動工作流程 **[!UICONTROL Start]** 或 **[!UICONTROL Restart]** 按鈕。
   * **[!UICONTROL Ignore]**：觸發錯誤的工作狀態會變更為 **[!UICONTROL Failed]**，但工作流程會保留 **[!UICONTROL Started]** 狀態。 此設定與週期性任務相關：如果分支包含排程器，它將在下次工作流程執行時正常啟動。

* **[!UICONTROL Consecutive errors]**

   此欄位在下列情況中變得可用： **[!UICONTROL Ignore]** 值已選取於 **[!UICONTROL In case of errors]** 欄位。 您可以指定程序停止之前可以忽略的錯誤數。達到此數目後，工作流程狀態會變更為 **[!UICONTROL Failed]**. 如果此欄位的值為 0，則無論錯誤數為何，工作流程都不會停止。

* **[!UICONTROL Template]**

   此欄位可讓您選取當工作流程監督員的狀態變更為時，要傳送給其工作流程監督員的通知範本 **[!UICONTROL Failed]**.

   如果相關操作員的設定檔中有電子郵件地址，則會以電子郵件通知相關操作員。 若要定義工作流程主管，請前往 **[!UICONTROL Supervisor(s)]** 屬性欄位(**[!UICONTROL General]** 標籤)。

   ![](assets/wf-properties_select-supervisors.png)

   此 **[!UICONTROL Notification to a workflow supervisor]** 預設範本包含一個連結，可透過網頁存取Adobe Campaign主控台，這樣收件者就可以在登入後處理問題。

   若要建立個人化範本，請前往 **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**.
