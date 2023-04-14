---
title: 傳送及監控交易式訊息
description: 了解如何傳送和監控交易式訊息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---


# 傳送及監控交易式訊息 {#delivery-execution}

## 傳送訊息{#send-transactional-msg}

完成擴充並將傳送範本連結至事件後，即會從執行例項傳送傳送。

>[!NOTE]
>
>交易式訊息的優先順序高於任何其他傳送。

所有傳送都會分組於 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 檔案夾。

依預設，會依傳送月份排序為子資料夾。 這可在訊息範本屬性中變更。

## 監視訊息 {#monitor-transactional-msg}

若要監視交易式訊息，請檢查 [傳遞記錄](send.md).

從執行例項傳送的交易式傳送會透過技術工作流程同步回控制例項(**[!UICONTROL Message Center execution instance]**)，每小時執行一次。

>[!NOTE]
>
>每週傳送會根據最新事件更新累積事件，而非根據事件建立日期。 因此，從控制例項擷取交易式訊息傳送記錄時，與每個傳送記錄ID相關聯的傳送ID可能會隨著記錄更新而隨時間變更（例如，當收到事件的入站退信時）。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 報告{#reporting-transactional-msg}

Adobe Campaign提供數個報表，可讓您控制活動並順利執行執行個體。

這些訊息中心報告可從 **[!UICONTROL Reports]** 的 **控制實例**.

![](assets/mc-reports.png)

### 訊息中心事件歷史記錄 {#history-events}

此 **[!UICONTROL Message Center event history]** 報表顯示訊息中心模組活動的概觀，即以交易式訊息處理和傳送的事件數。

開啟報表時，預設顯示的資訊與成功傳送交易式訊息的速率一致。 要查看更多級別，可以開啟各種節點，並將游標置於適當級別上以進行選擇。

您可以依時段檢視每個事件類型的特定資料。 此 **[!UICONTROL Events]** 欄對應於每個控制實例接收的事件數。 轉換為個人化交易式訊息的事件數，在 **[!UICONTROL Sent]** 欄。


### 訊息中心處理時間 {#processing-time}

此 **[!UICONTROL Message Center processing time]** 報表顯示與即時佇列相關的主要指標。 此報告也可透過 **[!UICONTROL Monitoring]** 頁簽。

![](assets/mc-processing-time-report.png)

您可以選擇顯示全局統計資訊或與特定執行實例相關的統計資訊。 您也可以依管道和特定期間來篩選資料。

顯示於 **[!UICONTROL Indicators over the period]** 區段在選取的期間內計算：

* **[!UICONTROL Average queuing time]**:成功處理事件在訊息中心逗留的平均時間。 只考慮處理時間。
* **[!UICONTROL Average message sending time (s)]**:成功處理事件在訊息中心逗留的平均時間。 只考慮mta傳送時間。
* **[!UICONTROL Average processing time (s)]**:成功處理事件在訊息中心逗留的平均時間。 計算會考量處理時間和mta傳送時間。
* **[!UICONTROL Maximum number of queued events]**:在任何給定時刻消息中心隊列中存在的事件數上限。
* **[!UICONTROL Minimum number of queued events]**:在任何給定時刻消息中心隊列中存在的事件的最小數量。
* **[!UICONTROL Average number of queued events]**:在任何給定時刻消息中心隊列中存在的事件平均數。

>[!NOTE]
>
>警告（橙色）和警報（紅色）指標臨界值可在Adobe Campaign部署精靈中設定。 請參閱 [監視閾值](#thresholds).



### 訊息中心服務層級 {#service-level}

此 **[!UICONTROL Message Center service level]** 報表會顯示與交易式訊息相關的傳送統計資料，以及錯誤劃分。 您可以按一下錯誤類型以顯示其詳細資訊。

此報告也可透過 **[!UICONTROL Monitoring]** 頁簽。

您可以選擇顯示全局統計資訊或與特定執行實例相關的統計資訊。 您也可以依管道和特定期間來篩選資料。

顯示於 **[!UICONTROL Indicators over the period]** 區段在選取的期間內計算：

* **[!UICONTROL Incoming (throughput event/h)]**:在「訊息中心」佇列中輸入的每小時事件平均數。
* **[!UICONTROL Incoming (event vol)]**:在「消息中心」隊列中輸入的事件數。
* **[!UICONTROL Outgoing (throughput msg/h)]**:成功傳出訊息中心事件（由傳送傳送）的平均每小時數。
* **[!UICONTROL Outgoing (msg vol)]**:成功傳出訊息中心事件的數量（由傳送傳送）。
* **[!UICONTROL Average sending time (seconds)]**:訊息中心中成功處理事件的平均逗留時間。 計算會考量處理時間和mta傳送時間。
* **[!UICONTROL Error rate]**:與已進入「消息中心」隊列的事件數相比，存在錯誤的事件數。 會考量下列錯誤：路由錯誤、過期事件（佇列中的事件過長）、傳送錯誤，由傳送忽略（隔離等）。

>[!NOTE]
>
>警告（橙色）和警報（紅色）指標臨界值可在Adobe Campaign部署精靈中設定。 請參閱 [監視閾值](#thresholds).

### 監視臨界值 {#thresholds}

您可以設定顯示於 **訊息中心服務層級** 和 **訊息中心處理時間** 報表。

要執行此操作，請遵循下列步驟：

1. 在 **執行實例**，並瀏覽至 **[!UICONTROL Message Center]** 頁面。
1. 使用箭頭更改閾值。

   ![](assets/mc-thresholds.png)

