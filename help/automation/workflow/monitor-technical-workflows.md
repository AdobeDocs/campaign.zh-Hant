---
product: campaign
title: 監視技術工作流程
description: 監視技術工作流程
feature: Workflows
exl-id: 8524d916-8af7-4641-b047-9c348f1017fd
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# 監視技術工作流程 {#monitoring-technical-workflows}

需要監控技術工作流，並在它們失敗時採取操作。

## 實例監視儀表板 {#instance-monitoring-dashboard}

實例監視儀表板可通過 **[!UICONTROL Monitoring]** 頁籤。

![](assets/monitoring_technical_workflows1.png)

在「System Indicators（系統指示器）」和核心檔案下，檢查沒有指示器以紅色突出顯示。 如果情況確實如此，而且有些情況確實如此，您應該：

* 檢查必要的進程是否始終在運行，
* 檢查所有過程是否都太舊，
* 檢查不同進程的日誌檔案中是否不包含警告錯誤和重複錯誤。

## 技術工作流程 {#technical-workflows}

技術工作流可從 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**。

根據技術工作流，請執行下面詳述的步驟，確保一切正常。

要更好地瞭解每個技術工作流應執行的操作，請參閱此 [節](technical-workflows.md)。

對於 **[!UICONTROL Database Cleanup workflow (‘cleanup’)]**:

檢查日記帳，以驗證已用時間是否隨時間而相對恆定，並且不干擾其他工作流。

對於 **[!UICONTROL Tracking workflow (‘tracking’)]**:

檢查跟蹤工作流是否按計畫運行（預設情況下每小時運行一次），以及日記帳是否不會突出顯示經常性錯誤。 如需詳細資訊，請參閱本[區段](delivery.md)。

對於 **[!UICONTROL Deliverability update (‘deliverabilityUpdate’)]**:

1. 檢查 **[!UICONTROL Deliverability update]** 工作流每天都成功運行並完成。
1. 在日記帳中驗證規則是否正在定期更新。

對於 **[!UICONTROL Campaign process ('operationMgt', 'deliveryMgt', ...)]**:

1. 查看位於 **[!UICONTROL Campaign process]** 的子菜單。 如需關於此項目的詳細資訊，請參閱此[頁面](technical-workflows.md)。
1. 檢查工作流是否按計畫運行，以及日記帳是否未突出顯示經常性錯誤。

## 工作流監督 {#workflow-supervision}

的 **[!UICONTROL Workflow supervisors]** 組應包含需要隨時通知故障以及可以及時採取行動的運算子。

![](assets/monitoring_technical_workflows3.png)

在出現問題時，應生成警報並將其發送到正確的組。

確保每個操作員都有有效的電子郵件地址。

為了使平台保持工作，應運行的任何工作流（如每日資料導入）都應聲明為「生產」（複選框），並以粗體顯示。

## 工作流維護清單 {#workflow-maintenance-list}

所有自定義技術工作流都應記錄在包含以下內容的工作表中：

* 工作流的名稱和位置。
* 目的。
* 計畫和依賴項。
* 負責監控的操作員。
* 有關在出錯時應執行的操作的說明。

![](assets/monitoring_technical_workflows4.png)

## 監控的規劃和自動化 {#planning-and-automation-of-monitoring}

規劃工作流監控提高了其效率。 有些任務需要每天進行，而其他任務則可以每週或每月進行。

在按重複命名的資料夾中設定工作流，並按執行計畫排序，可提高監視效率。

自動監控可減少資源開銷並確保以適當的頻率安排任務。

您可以構建監控工作流，以便在某些任務失敗或關鍵表過大時發送電子郵件。

您可以建立視圖，以便可以監視功能區域或系統範圍內的所有工作流。

您還可以使用Adobe Campaign作業或報告功能按需生成文檔，文檔始終是最新的。
