---
product: campaign
title: 工作流程屬性
description: 瞭解有關市場活動工作流屬性的詳細資訊
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 39%

---

# 工作流程屬性{#workflow-properties}



## 「執行」頁籤 {#execution-tab}

的 **[!UICONTROL Execution]** 頁籤 **[!UICONTROL Properties]** 將工作流中的窗口分為3個部分：

![](assets/wf_execution_tab.png)

### 排程器 {#scheduler}

此部分僅顯示在市場活動工作流中。

* **[!UICONTROL Priority]**

   工作流引擎根據此欄位中定義的優先順序標準處理要執行的工作流。 例如，所有具有 **[!UICONTROL Average]** 優先順序將先於 **[!UICONTROL Low]** 優先順序。

* **[!UICONTROL Schedule execution for a time of low activity]**

   此選項將工作流開始時間推遲到較少的忙時間。 某些工作流在資料庫引擎的資源方面可能成本高昂。 我們建議將執行時間安排在低活動時間（例如晚上）。 低活動期間在 **[!UICONTROL Processes on campaigns]** 技術工作流。

### 執行 {#execution}

* **[!UICONTROL Default affinity]**

   如果您的安裝包括多個工作流程伺服器，請使用此欄位選擇工作流程將在其中執行的電腦。如果在此欄位定義的值不存在於任何伺服器，工作流程將保持待處理狀態。

* **[!UICONTROL History in days]**

   資料庫的工作表保留執行的歷史記錄（任務、事件、日誌）。 您可以在此處定義此工作流程的封存天數：清除程序會每天刪除一次最舊的封存檔。如果此欄位的值為零，則永遠不會刪除封存檔。

* **[!UICONTROL Log SQL queries in the journal]**

   此功能保留給進階使用者使用。它涉及包含目標定位活動 (查詢、聯合、交集等) 的工作流程。勾選此選項後，在工作流程執行期間傳送到資料庫的 SQL 查詢將顯示在 Adobe Campaign 中：這表示您可以分析它們以最佳化查詢或診斷問題。

   查詢顯示在 **[!UICONTROL SQL logs]** 頁籤，添加到工作流（市場活動工作流除外）和 **[!UICONTROL Properties]** 選項時執行。 的 **[!UICONTROL Audit]** 頁籤還包括SQL查詢。

   ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

   此選項只能用於卸貨，不能用於生產。 啟用後，工作流將優先，並且所有其他工作流將停止，直到此工作流完成。

### 錯誤管理 {#error-management}

* **[!UICONTROL Troubleshooting]**

   此欄位可讓您定義工作流程的任務發生錯誤時要採取的動作。您有兩個選擇：

   * **[!UICONTROL Stop the process]**:工作流將自動暫停。 工作流狀態更改為 **[!UICONTROL Failed]**。 問題解決後，使用 **[!UICONTROL Start]** 或 **[!UICONTROL Restart]** 按鈕。
   * **[!UICONTROL Ignore]**:觸發錯誤更改的任務的狀態 **[!UICONTROL Failed]**，但工作流保留 **[!UICONTROL Started]** 狀態。 此設定與週期性任務相關：如果分支包含排程器，它將在下次工作流程執行時正常啟動。

* **[!UICONTROL Consecutive errors]**

   當 **[!UICONTROL Ignore]** 值 **[!UICONTROL In case of errors]** 的子菜單。 您可以指定程序停止之前可以忽略的錯誤數。一旦達到此數字，工作流狀態將更改為 **[!UICONTROL Failed]**。 如果此欄位的值為 0，則無論錯誤數為何，工作流程都不會停止。

* **[!UICONTROL Template]**

   此欄位允許您選擇在工作流主管的狀態更改為 **[!UICONTROL Failed]**。

   如果其個人資料中有電子郵件地址，將通過電子郵件通知有關操作員。 要定義工作流主管，請轉到 **[!UICONTROL Supervisor(s)]** 欄位(**[!UICONTROL General]** )的正平方根。

   ![](assets/wf-properties_select-supervisors.png)

   的 **[!UICONTROL Notification to a workflow supervisor]** 預設模板包括通過Web訪問Adobe Campaign控制台的連結，以便收件人登錄後可以處理此問題。

   要建立個性化模板，請轉到 **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**。
