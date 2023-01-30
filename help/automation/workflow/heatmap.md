---
product: campaign
title: 促銷活動工作流程熱度圖
description: 使用工作流程熱度圖監控您的工作流程
feature: Workflows, Heatmap
exl-id: aeb35076-2f0d-456d-8562-be69e7e902eb
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 3%

---

# 工作流程熱度圖 {#workflow-heatmap}

促銷活動工作流程熱度圖包含目前執行之所有工作流程的色彩編碼圖形表示法。 它僅適用於 **Campaign管理員**.

## 開始使用工作流程熱度圖 {#about-the-workflow-heatmap}

透過提供並行工作流程數目的快速概覽，Adobe Campaign平台管理員可監控執行個體的負載，並據此規劃工作流程。

更準確地說，這可協助平台管理員：

* 檢視並瞭解並行的工作流程
* 依期間篩選工作流程，以查看哪些工作流程可能遇到問題
* 依持續時間篩選活動，以查看哪些活動可能遇到問題
* 輕易尋找個別的工作流程及所有的相關活動 (包括其持續時間)
* 按工作流類型篩選： [技術工作流程](technical-workflows.md) 或 [行銷活動工作流程](campaign-workflows.md)
* 尋找特定工作流程並加以分析

>[!NOTE]
>
>除了 **工作流程熱度圖**，您可以建立工作流程，讓您監控一組工作流程的狀態並傳送循環訊息給主管。 有關詳細資訊，請參閱 [專屬區段](workflow-supervision.md).

使用「工作流熱度圖」需要熟悉下列概念： [工作流程](about-workflows.md), [活動](activities.md) 和 [工作流程最佳實務](workflow-best-practices.md).

## 自訂工作流程熱度圖 {#using-the-heatmap}

>[!NOTE]
>
>如果「工作流熱度圖」中未顯示任何資料，請按一下 **[!UICONTROL Load data]** 按鈕。

1. 前往 **[!UICONTROL Monitoring]** 並按一下 **[!UICONTROL Workflow HeatMap]** 連結以顯示 **[!UICONTROL Campaign Workflow HeatMap]** 頁面。

   ![](assets/wkf_monitoring_path.png)

1. 按一下日曆以選取日。

   依預設，頁面會顯示當天的工作流程活動。 您可以變更它，並選取過去的任何日期。

   >[!NOTE]
   > 
   >預設情況下，為當前管理員用戶定義的工作流熱度映射時區。 例如，如果您與您所使用的行銷使用者不在相同區域，則可能會想要加以變更。

1. 按一下 **[!UICONTROL Filters]** 按鈕。

   ![](assets/wkf_monitoring_filters.png)

1. 使用滑桿將最短持續時間設定為0秒到1小時。 這可讓您只搜尋執行超過特定秒數或分鐘的工作流程。

   ![](assets/wkf_monitoring_filters_duration.png)

1. 您也可以從 **[!UICONTROL Workflows]** 下拉式清單。

   ![](assets/wkf_monitoring_filters_workflows.png)

   >[!NOTE]
   >
   >此 **[!UICONTROL Min duration]** 篩選。 如果您找不到特定的工作流程，請將最小持續時間重設為0，讓清單中顯示所有工作流程。

1. 您也可以篩選 **[!UICONTROL Workflow type]** :

   * **[!UICONTROL Technical]** :僅 [內建的技術工作流程](technical-workflows.md) 和 [資料管理工作流程](targeting-workflows.md#data-management) 的下界。
   * **[!UICONTROL Marketing]** :僅連結至行銷活動的工作流程，稱為 [行銷活動工作流程](campaign-workflows.md)，則會顯示。

1. 若要依名稱搜尋特定工作流程，您也可以使用 **[!UICONTROL Workflow name filter]** 欄位。

1. 如果您在兩者之間的時間編輯了某些工作流程，請按一下 **[!UICONTROL Reload data]** 按鈕，刷新網格中顯示的資料。

## 解譯工作流程熱度圖 {#reading-the-heatmap}

促銷活動工作流程熱度圖是自然可從左上至右下閱讀的格線，可讓您尋找具有綠色至紅色色彩編碼範圍的「熱區」。

* 較深的紅色儲存格對應於同時執行大量工作流程的期間。
* 灰色儲存格對應至沒有執行工作流程的期間。

若要了解如何套用顏色代碼以及如何導覽熱度圖，請按一下 **[!UICONTROL Help]** 按鈕。

![](assets/wkf_monitoring_legend.png)

每一列代表一天中的一小時，而每個儲存格代表該小時的5分鐘。

格線會針對每個5分鐘的期間，顯示同時執行的所有工作流程。

在下列範例中，從上午8:05到上午8:05，三個工作流程都在執行中（無論個別持續時間為何）:

![](assets/wkf_monitoring_ex_8am.png)

1. 按一下彩色儲存格，以顯示此期間執行之所有同時工作流程的詳細資訊。

   ![](assets/wkf_monitoring_details.png)

   對於每個工作流程，其包含的所有活動都會列出及其持續時間。

1. 按一下工作流程ID或名稱，直接開啟工作流程。
1. 返回 **[!UICONTROL Campaign Workflow HeatMap]** 檢視，按一下 **[!UICONTROL Home]** 按鈕。

## 使用案例：使用熱度圖執行操作 {#use-cases--using-the-heatmap-to-take-actions}

促銷活動工作流程熱度圖有兩個主要用途。

### 減少並行工作流程的數量 {#reducing-the-number-of-concurrent-workflows}

身為Campaign管理員，工作流程熱度圖可協助您了解執行個體的負載，並在適當時間規劃現有或新的工作流程。

1. 從 **[!UICONTROL Campaign Workflow HeatMap]** 檢視，按一下 **[!UICONTROL Filters]** 按鈕。
1. 將持續時間設為幾秒或幾分鐘。
1. 增加持續時間篩選條件，排除沒有顯著性的最短工作流程。

   ![](assets/wkf_monitoring_short_duration.png)

1. 探索結果以了解例項上的負載並採取適當動作：

   * 如果您遇到效能問題，且格線中顯示一或多個紅色儲存格，請考慮變更數個工作流程的開始時間。 請行銷使用者手動將工作流程從繁忙（「熱」）時段移至更多可用時段。 這應該會維持一天中穩定的活動水準。
   * 為避免出現峰值並防止實例過載，請在規劃新工作流之前查看熱度圖，並選擇最佳時間。 請考慮格線中與灰色或綠色儲存格對應的時槽，以開始新的工作流程。

### 尋找影響效能的長時間執行的工作流程 {#finding-long-running-workflows-that-impact-performance}

身為Campaign管理員，工作流程熱度圖可協助您尋找可能減緩活動的最長工作流程。

1. 從 **[!UICONTROL Campaign Workflow HeatMap]** 檢視，按一下 **[!UICONTROL Filters]** 按鈕。
1. 將持續時間設為1小時。

   ![](assets/wkf_monitoring_long_duration.png)

1. 減少 **[!UICONTROL Min duration]** 篩選。
1. 探索結果以找出最長的工作流，這些工作流可能會對伺服器和資料庫資源（CPU、RAM、網路、IOPS等）產生更大的影響。
1. 採取適當行動：

   * 建議行銷使用者分割最長的工作流程，以縮短處理時間。
   * 開始對特定工作流程和特定活動（例如JavaScript、匯入、匯出等）進行更深入的分析，以隔離問題並更輕鬆地解決問題。

## 使用熱度圖改進工作流規劃 {#example--using-the-heatmap-to-improve-workflow-planning}

以下範例說明使用Adobe Campaign Workflow HeatMap時，如何提高規劃的效率，以及如何改善效能。

在這種情況下，許多使用者都在抱怨工作流程效能。 您需要檢查哪些項目導致活動變慢以及如何解決問題。

1. 前往 **[!UICONTROL Monitoring]** 並按一下 **[!UICONTROL Workflows]** 連結以顯示 **[!UICONTROL Campaign Workflow HeatMap]** 頁面。
1. 設定 **[!UICONTROL Min duration]** 篩選為5分鐘。
1. 設定 **[!UICONTROL Workflow type]** 篩選 **[!UICONTROL Marketing]**.
1. 從熱度圖網格中，觀察以下內容：

   ![](assets/wkf_monitoring_without.png)

   * 50個持續（超過5分鐘）的行銷活動工作流程在上午10:00執行。
   * 其中大部分都有擱置狀態（預設情況下，並行限制設為20）。
   * 每天需要手動重新啟動待處理的工作流程。
   * 效能低。

1. 不必從上午10:00開始有50個工作流程，而是將工作流程的開始時間平均分配給當天的其餘時間。
1. 返回 **[!UICONTROL Campaign Workflow HeatMap]** 頁面，然後按一下 **[!UICONTROL Reload data]** 按鈕。
1. 現在，請注意下列事項：

   ![](assets/wkf_monitoring_with.png)

   * 上午10時，只有18個持續的行銷活動工作流程仍在執行。
   * 沒有其他工作流程處於擱置狀態（並行限制仍設為20）。
   * 工作流程開始時間會在一整天內平均分配。
   * 沒有更多用戶抱怨效能問題。
