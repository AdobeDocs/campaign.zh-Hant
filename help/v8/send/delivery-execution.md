---
title: 發送和監視事務性消息
description: 瞭解如何發送和監視事務性消息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# 發送和監視事務性消息 {#delivery-execution}

## 傳送訊息{#send-transactional-msg}

一旦完成濃縮並且傳遞模板已連結到事件，則從執行實例發送傳遞。

>[!NOTE]
>
>事務性消息比任何其它傳遞優先。

所有交貨均在 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 的子菜單。

預設情況下，按交貨月將它們分類為子資料夾。 可以在消息模板屬性中更改此項。

## 監視消息 {#monitor-transactional-msg}

要監視事務性消息，請檢查 [交貨日誌](send.md)。

從執行實例發送的事務性交付通過技術工作流(**[!UICONTROL Message Center execution instance]**&#x200B;每小時運行一次。

>[!NOTE]
>
>交貨每週根據最新事件更新累計事件，而不是根據事件建立日期累計事件。 因此，當從控制實例提取事務性消息傳遞日誌時，與每個傳遞日誌ID相關聯的傳遞ID可隨著日誌的更新而隨時間而改變（例如，當接收到事件的入站跳回時）。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 報告{#reporting-transactional-msg}

Adobe Campaign提供了多個報告，使您能夠控制執行實例的活動並順利運行。

可以從 **[!UICONTROL Reports]** 頁籤 **控制實例**。

![](assets/mc-reports.png)

### 消息中心事件歷史記錄 {#history-events}

的 **[!UICONTROL Message Center event history]** report顯示消息中心模組活動的概覽，即作為事務性消息處理和傳遞的事件數。

開啟報告時，預設顯示的資訊與成功發送事務性消息的速率一致。 要查看更多級別，您可以開啟各種節點並將游標置於適當級別上以選擇它。

您可以查看每個時段中特定於每個事件類型的資料。 的 **[!UICONTROL Events]** 列對應於每個控制實例接收的事件數。 轉換為個性化事務消息的事件數在 **[!UICONTROL Sent]** 的雙曲餘切值。


### 訊息中心處理時間 {#processing-time}

的 **[!UICONTROL Message Center processing time]** 報告顯示與即時隊列相關的主要指標。 此報告也可以通過 **[!UICONTROL Monitoring]** 的子菜單。

![](assets/mc-processing-time-report.png)

您可以選擇顯示全局統計資訊或與特定執行實例相關的統計資訊。 您還可以按通道和特定時段過濾資料。

顯示在 **[!UICONTROL Indicators over the period]** 按選定期間計算：

* **[!UICONTROL Average queuing time]**:成功處理消息中心中所用事件的平均時間。 只考慮處理時間。
* **[!UICONTROL Average message sending time (s)]**:成功處理消息中心中所用事件的平均時間。 只考慮郵件交付時間。
* **[!UICONTROL Average processing time (s)]**:成功處理消息中心中所用事件的平均時間。 該計算考慮了處理時間和發送時間。
* **[!UICONTROL Maximum number of queued events]**:消息中心隊列中任意給定時刻存在的最大事件數。
* **[!UICONTROL Minimum number of queued events]**:消息中心隊列中任意給定時刻存在的最小事件數。
* **[!UICONTROL Average number of queued events]**:消息中心隊列中任意給定時刻存在的事件的平均數。

>[!NOTE]
>
>警告（橙色）和警報（紅色）指示器閾值可以在Adobe Campaign部署嚮導中配置。 請參閱 [監視閾值](#thresholds)。



### 訊息中心服務層級 {#service-level}

的 **[!UICONTROL Message Center service level]** 報告顯示與事務性消息相關的傳遞統計資訊以及錯誤細分。 可以按一下錯誤類型以顯示其詳細資訊。

此報告也可以通過 **[!UICONTROL Monitoring]** 的子菜單。

您可以選擇顯示全局統計資訊或與特定執行實例相關的統計資訊。 您還可以按通道和特定時段過濾資料。

顯示在 **[!UICONTROL Indicators over the period]** 按選定期間計算：

* **[!UICONTROL Incoming (throughput event/h)]**:在消息中心隊列中輸入的事件的平均小時數。
* **[!UICONTROL Incoming (event vol)]**:在消息中心隊列中輸入的事件數。
* **[!UICONTROL Outgoing (throughput msg/h)]**:成功傳出消息中心事件（通過傳遞發送）的平均小時數。
* **[!UICONTROL Outgoing (msg vol)]**:成功傳出的消息中心事件數（由傳遞發送）。
* **[!UICONTROL Average sending time (seconds)]**:在消息中心中處理成功處理的事件的平均時間。 該計算考慮了處理時間和發送時間。
* **[!UICONTROL Error rate]**:與已進入消息中心隊列的事件數相比，出現錯誤的事件數。 將考慮以下錯誤：路由錯誤、過期事件（隊列中的事件過長）、傳遞錯誤，被傳遞忽略（隔離等）。

>[!NOTE]
>
>警告（橙色）和警報（紅色）指示器閾值可以在Adobe Campaign部署嚮導中配置。 請參閱 [監視閾值](#thresholds)。

### 監視臨界值 {#thresholds}

您可以配置顯示在 **消息中心服務級別** 和 **消息中心處理時間** 報告。

要執行此操作，請遵循下列步驟：

1. 在 **執行實例**，並瀏覽至 **[!UICONTROL Message Center]** 的子菜單。
1. 使用箭頭更改閾值。

   ![](assets/mc-thresholds.png)
