---
product: campaign
title: 高級參數
description: 高級參數
feature: Workflows, Data Management
exl-id: aafd977e-c8af-426b-904c-8388c9d8e595
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 5%

---

# 高級參數{#advanced-parameters}



活動的屬性畫面具有 **[!UICONTROL Advanced]** 索引標籤可讓您定義發生錯誤時的行為、活動的執行期間，以及輸入初始化指令碼。 此標籤有兩個版本：

* 簡化版本(適用於 **[!UICONTROL Start]** 和 **[!UICONTROL End]** 例如活動)

   ![](assets/wf-advanced-basic.png)

* 更詳細的版本(適用於 **[!UICONTROL Query]** 活動)

   ![](assets/wf-advanced-full.png)

要輸入的欄位 **[!UICONTROL Advanced]** 標籤會在以下各節中詳細說明。

## 名稱 {#name}

此欄位包含活動的內部名稱。

## 影像 {#image}

此欄位可讓您變更連結至活動的影像。 有關詳細資訊，請參閱 [變更活動影像](change-activity-images.md).

## 執行 {#execution}

此欄位可讓您定義觸發任務時要執行的動作。 有三種可能的選項：

通常在購物車中以滑鼠右鍵按一下活動來選取這些選項。

* **[!UICONTROL Normal]**：活動會照常執行。
* **[!UICONTROL Do not activate]**：此任務和以下所有任務（在同一分支中）不會執行。
* **[!UICONTROL Activate but do not execute]**：此任務和以下所有任務（在同一分支中）會自動停止。 如果您想在任務啟動時到達該處，這會很有用。 若要手動執行工作，請在活動上按一下滑鼠右鍵，然後選取 **[!UICONTROL Normal execution]**.

## 相似性 {#affinity}

您可以選擇在特定電腦上強制執行工作流程或工作流程活動。 若要這麼做，您必須在工作流程或相關活動的層級定義一或多個屬性。


## 最大. 執行期間 {#max--execution-period}

此欄位可讓您為任務花費太長的時間設定警告。 這不會影響工作流程作業。 如果任務未在 **[!UICONTROL Max. execution period]** 結束， **[!UICONTROL Instance monitoring]** 頁面將顯示此工作流程的警告。 此頁面的存取方式為 **[!UICONTROL Monitoring]** 首頁的頁簽。

## 行為 {#behavior}

此欄位可讓您定義要套用於使用非同步工作的行為。 您有兩個選擇：

* **[!UICONTROL Several tasks authorized]**：即使第一個任務未完成，仍可一次執行多個任務。
* **[!UICONTROL The current task has priority]**：進行中的任務優先順序。 只要工作仍在進行中，就不會執行其他工作。

## 時區 {#time-zone}

此欄位可讓您選取活動的時區。 有關詳細資訊： [管理時區](managing-time-zones.md).

## 發生錯誤時 {#in-case-of-errors}

此欄位可讓您定義活動發生錯誤時要執行的動作。 您有兩個選擇：

* **[!UICONTROL Suspend the process]**：工作流程會自動停止。 其狀態變更為 **[!UICONTROL Failed]**. 問題解決後，請重新啟動工作流程。
* **[!UICONTROL Ignore]**：此任務和以下所有任務（在同一分支中）不會執行。 這對於週期性任務很有用。 如果分支有排程器放在上游，它將在下一個執行日期照常啟動。
* **[!UICONTROL Abort on error]**：工作流程會自動停止，且無法重新啟動。 其狀態變更為 **[!UICONTROL Failed]**.

## 初始化指令碼 {#initialization-script}

此欄位可讓您初始化變數或修改活動屬性。 有關詳細資訊，請參閱： [JavaScript指令碼和範本](javascript-scripts-and-templates.md).

## 評論 {#comment}

此 **[!UICONTROL Comment]** 欄位是自由欄位，可讓您新增說明。
