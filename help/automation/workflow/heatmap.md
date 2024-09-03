---
product: campaign
title: 行銷活動工作流程熱度圖
description: 使用Workflow HeatMap監視您的工作流程
feature: Workflows, Heatmap
role: Admin
exl-id: aeb35076-2f0d-456d-8562-be69e7e902eb
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 3%

---

# 工作流程熱度圖 {#workflow-heatmap}

Campaign Workflow HeatMap包含目前執行的所有工作流程，並以色彩編碼的圖形來加以呈現。 僅限&#x200B;**Campaign管理員**&#x200B;使用。

## 開始使用工作流程熱度圖 {#about-the-workflow-heatmap}

藉由提供並行工作流程數目的快速概覽，「工作流程熱度圖」可讓Adobe Campaign平台管理員監控執行個體的負載，並據此計畫工作流程。

更準確地說，這有助於Platform管理員：

* 檢視並瞭解並行的工作流程
* 依期間篩選工作流程，以查看哪些工作流程可能遇到問題
* 依期間篩選活動，以檢視哪些活動可能會遇到問題
* 輕易尋找個別的工作流程及所有的相關活動 (包括其持續時間)
* 依工作流程型別篩選： [技術工作流程](technical-workflows.md)或[行銷活動工作流程](campaign-workflows.md)
* 尋找特定工作流程並加以分析

>[!NOTE]
>
>除了&#x200B;**工作流程熱度圖**，您可以建立工作流程，讓您監視一組工作流程的狀態，並傳送週期性訊息給主管。 如需詳細資訊，請參閱[專屬區段](workflow-supervision.md)。

使用工作流程熱度圖需要深入瞭解下列概念： [工作流程](about-workflows.md)、[活動](activities.md)和[工作流程最佳實務](workflow-best-practices.md)。

## 自訂工作流程熱度圖 {#using-the-heatmap}

>[!NOTE]
>
>如果工作流程熱度圖中未顯示任何資料，請按一下&#x200B;**[!UICONTROL Load data]**&#x200B;按鈕。

1. 移至&#x200B;**[!UICONTROL Monitoring]**&#x200B;並按一下&#x200B;**[!UICONTROL Workflow HeatMap]**&#x200B;連結以顯示&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;頁面。

   ![](assets/wkf_monitoring_path.png)

1. 按一下行事曆以選取日期。

   依預設，頁面會顯示當天的工作流程活動。 您可以加以變更，並選取過去的任何一天。

   >[!NOTE]
   > 
   >依預設，Workflow HeatMap時區是為目前管理員使用者定義的時區。 例如，如果您所在的區域與正在使用的行銷使用者不同，您可能會想要變更此專案。

1. 按一下 **[!UICONTROL Filters]** 按鈕。

   ![](assets/wkf_monitoring_filters.png)

1. 使用滑桿來設定從0秒到1小時的最短持續時間。 這可讓您僅搜尋執行時間超過特定秒數或分鐘的工作流程。

   ![](assets/wkf_monitoring_filters_duration.png)

1. 您也可以從&#x200B;**[!UICONTROL Workflows]**&#x200B;下拉式清單中選擇特定工作流程。

   ![](assets/wkf_monitoring_filters_workflows.png)

   >[!NOTE]
   >
   >已套用&#x200B;**[!UICONTROL Min duration]**&#x200B;篩選器。 如果找不到特定工作流程，請將最短持續期間重設為0，以便所有工作流程都顯示在清單中。

1. 您也可以篩選&#x200B;**[!UICONTROL Workflow type]**：

   * **[!UICONTROL Technical]**：只顯示[內建的技術工作流程](technical-workflows.md)和[資料管理工作流程](targeting-workflows.md#data-management)。
   * **[!UICONTROL Marketing]**：僅顯示連結至行銷活動的工作流程，稱為[行銷活動工作流程](campaign-workflows.md)。

1. 若要依名稱搜尋特定工作流程，您也可以使用&#x200B;**[!UICONTROL Workflow name filter]**&#x200B;欄位。

1. 如果您編輯了介於兩者之間的一些工作流程，請按一下&#x200B;**[!UICONTROL Reload data]**&#x200B;按鈕，重新整理網格中顯示的資料。

## 解譯工作流程熱度圖 {#reading-the-heatmap}

Campaign Workflow HeatMap是從左上到右下自然可讀的格線，允許尋找具有綠色至紅色顏色編碼範圍的「熱區」。

* 較暗的紅色儲存格對應於同時執行大量工作流程時的時段。
* 灰色儲存格對應於沒有執行工作流程時的週期。

若要瞭解如何套用色彩代碼以及如何導覽HeatMap，請按一下&#x200B;**[!UICONTROL Help]**&#x200B;按鈕。

![](assets/wkf_monitoring_legend.png)

每一列代表一天中的一小時，每個儲存格代表該小時的5分鐘。

此格線會顯示這5分鐘期間中每個期間同時執行的所有工作流程。

在以下範例中，上午8點至上午8:05之間，有三個工作流程在執行中（無論其個別持續時間為何）：

![](assets/wkf_monitoring_ex_8am.png)

1. 按一下彩色儲存格，以顯示在此期間執行的所有並行工作流程詳細資料。

   ![](assets/wkf_monitoring_details.png)

   對於每個工作流程，會列出其中包含的所有活動及其持續時間。

1. 按一下工作流程ID或名稱，直接開啟工作流程。
1. 若要返回&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;檢視，請按一下&#x200B;**[!UICONTROL Home]**&#x200B;按鈕。

## 使用案例：使用熱度圖採取動作 {#use-cases--using-the-heatmap-to-take-actions}

行銷活動工作流程熱度圖有兩個主要用途。

### 減少同時進行的工作流程數量 {#reducing-the-number-of-concurrent-workflows}

作為Campaign管理員，Workflow HeatMap可協助您瞭解執行個體的負載，並在適當時機規劃現有或新的工作流程。

1. 從&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;檢視，按一下&#x200B;**[!UICONTROL Filters]**&#x200B;按鈕。
1. 將持續時間設定為幾秒或幾分鐘。
1. 增加持續時間篩選條件，以排除不重要的最短工作流程。

   ![](assets/wkf_monitoring_short_duration.png)

1. 探索結果以瞭解執行個體的負載並採取適當的動作：

   * 如果您遇到效能問題，而且格線中顯示一或多個紅色的儲存格，請考慮變更數個工作流程的開始時間。 要求行銷使用者將手動工作流程從忙碌（「忙碌」）時段移至更多可用的時段。 這應該會維持一天的穩定活動水準。
   * 為避免峰值並防止執行個體過載，在規劃新工作流程之前請檢視熱度圖並選擇最佳時間。 考慮格線中對應灰色或綠色儲存格的時隙，以開始新的工作流程。

### 尋找影響效能的長期執行工作流程 {#finding-long-running-workflows-that-impact-performance}

作為Campaign管理員，Workflow HeatMap可協助您找出拖慢活動速度的最長工作流程。

1. 從&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;檢視，按一下&#x200B;**[!UICONTROL Filters]**&#x200B;按鈕。
1. 將持續時間設為1小時。

   ![](assets/wkf_monitoring_long_duration.png)

1. 減少&#x200B;**[!UICONTROL Min duration]**&#x200B;篩選器，以包含更多結果。
1. 探索結果以找出最長的工作流程，這些工作流程可能會對伺服器和資料庫資源（CPU、RAM、網路、IOPS等）造成更多影響。
1. 採取適當的動作：

   * 建議行銷使用者分割最長的工作流程，以減少處理時間。
   * 開始更深入分析特定工作流程和特定活動(例如JavaScript、匯入、匯出等)，以隔離問題並更輕鬆地解決問題。

## 使用HeatMap改善工作流程規劃 {#example--using-the-heatmap-to-improve-workflow-planning}

以下範例說明如何在使用Adobe Campaign Workflow HeatMap時提高規劃效率，以及如何改善效能。

在這種情況下，許多使用者抱怨工作流程效能。 您需要檢查哪些因素導致活動變慢，以及如何解決問題。

1. 移至&#x200B;**[!UICONTROL Monitoring]**&#x200B;並按一下&#x200B;**[!UICONTROL Workflows]**&#x200B;連結以顯示&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;頁面。
1. 將&#x200B;**[!UICONTROL Min duration]**&#x200B;篩選器設為5分鐘。
1. 將&#x200B;**[!UICONTROL Workflow type]**&#x200B;篩選器設為&#x200B;**[!UICONTROL Marketing]**。
1. 在「熱度圖」格線中，觀察下列專案：

   ![](assets/wkf_monitoring_without.png)

   * 50個長效的行銷活動工作流程正在上午10點執行（超過5分鐘）。
   * 其中大多數都具有擱置狀態（預設情況下，並行限制設為20）。
   * 擱置的工作流程每天都需要手動重新啟動。
   * 效能低。

1. 與其讓五十個工作流程從上午10點開始，不如在一天中的其餘時間平均分配工作流程的開始時間。
1. 返回&#x200B;**[!UICONTROL Campaign Workflow HeatMap]**&#x200B;頁面並按一下&#x200B;**[!UICONTROL Reload data]**&#x200B;按鈕。
1. 現在請觀察下列專案：

   ![](assets/wkf_monitoring_with.png)

   * 上午10點，只有18個長期的行銷活動工作流程仍在執行中。
   * 沒有其他工作流程處於擱置狀態（並行限制仍設為20）。
   * 工作流程開始時間會平均分配在一天當中。
   * 沒有更多使用者抱怨效能問題。
