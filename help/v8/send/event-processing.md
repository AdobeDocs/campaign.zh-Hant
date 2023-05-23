---
title: 收集和處理事件
description: 瞭解市場活動事務性消息傳遞如何收集和處理事件
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# 事件處理 {#event-processing}

在事務性消息傳遞的上下文中，事件由外部資訊系統產生並通過 **[!UICONTROL PushEvent]** 和 **[!UICONTROL PushEvents]** 的雙曲餘切值。 這些方法在 [此部分](event-description.md)。

此事件包含連結到該事件的資料，如：

* 它 [類型](transactional.md#create-event-types):訂單確認、在網站上建立帳戶等，
* 電子郵件地址或電話號碼，
* 任何其他資訊，以在傳遞前豐富事務性消息並對其進行個性化：客戶聯繫資訊、郵件語言、電子郵件格式等。

事件資料示例：

![](assets/mc-event-request.png)

要處理事務性消息傳遞事件，將對執行實例應用以下步驟：

1. [事件集合](#event-collection)
1. [事件傳輸到消息模板](#routing-towards-a-template)
1. 具有個性化資料的事件豐富
1. [傳遞執行](delivery-execution.md)
1. [事件的循環](#event-recycling) 連結傳遞失敗(通過Adobe Campaign工作流)

一旦完成所有步驟，每個目標接收者接收個性化消息。

## 收集事件 {#event-collection}

資訊系統生成的事件可以採用兩種模式進行收集：

* 對SOAP方法的調用允許您在Adobe Campaign推送事件：PushEvent方法允許您一次發送一個事件，PushEvents方法允許您一次發送多個事件。 [了解更多](event-description.md)。

* 建立工作流允許您通過導入檔案或通過SQL網關恢復事件， [聯合資料存取](../connect/fda.md) 中。

一旦收集了這些事件，就會按執行實例的即時隊列和批處理隊列之間的技術工作流細分事件，同時等待連結到 [消息模板](transactional-template.md)。

![](assets/mc-event-queues.png)

>[!NOTE]
>
>在執行實例上， **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 不能將資料夾設定為視圖，因為這可能導致訪問正確的問題。 有關將資料夾設定為視圖的詳細資訊，請參閱 [此部分](../audiences/folders-and-views.md#turn-a-folder-to-a-view)。

## 將事件傳輸到模板 {#event-to-template}

在執行實例上發佈消息模板後，將自動生成兩個模板：一個連結到即時事件，另一個連結到批處理事件。

路由步驟包括根據以下內容將事件連結到相應的消息模板：

* 在事件本身的屬性中指定的事件類型：

   ![](assets/event-type-sample.png)

* 在消息模板屬性中指定的事件類型：

   ![](assets/event-type-select.png)

預設情況下，路由依賴於以下資訊：

* 事件類型
* 要使用的通道(預設情況下：電子郵件)
* 基於發佈日期的最近交貨模板

## 檢查事件狀態 {#event-statuses}

所有已處理的事件都歸為一個視圖， **事件歷史記錄** 資料夾或資源管理器。 它們可以按事件類型或按 **狀態**。

可能的狀態包括：

* **待處理**

   * 掛起事件可以是剛收集但尚未處理的事件。 的 **[!UICONTROL Number of errors]** 列顯示值0。 電子郵件模板尚未連結。
   * 掛起事件也可以是已處理但確認錯誤的事件。 的 **[!UICONTROL Number of errors]** 列顯示的值不是0。 要瞭解何時將再次處理此事件，請參考 **[!UICONTROL Process requested on]** 的雙曲餘切值。

* **等待交貨**
已處理該事件並連結了傳遞模板。 電子郵件正在等待傳遞，並且應用了經典傳遞流程。 有關詳細資訊，請開啟交貨。
* **已發送**。 **已忽略** 和 **傳遞錯誤**
這些交貨狀態通過 
**updateEventsStatus** 工作流。 有關詳細資訊，您可以開啟相關交貨。
* **未涵蓋的事件**
事務性消息傳送路由階段失敗。 例如，Adobe Campaign沒有找到作為活動模板的電子郵件。
* **事件已過期**
已達到發送嘗試的最大數目。 該事件被視為空。

## 回收事件 {#event-recycling}

如果某個特定頻道上的消息傳遞失敗，Adobe Campaign可以使用其他頻道重新發送該消息。 例如，如果SMS通道上的傳遞失敗，則使用電子郵件通道重新發送消息。

為此，您需要配置工作流，該工作流使用 **傳遞錯誤** 狀態，並為其分配不同的通道。

>[!CAUTION]
>
>此步驟只能使用工作流執行，因此保留給專家用戶。 有關詳細資訊，請與您的Adobe帳戶主管聯繫。
