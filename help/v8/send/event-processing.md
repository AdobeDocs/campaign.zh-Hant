---
title: 收集和處理事件
description: 了解Campaign交易訊息如何收集和處理事件
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

在交易式訊息傳送的內容中，事件由外部資訊系統產生，並透過 **[!UICONTROL PushEvent]** 和 **[!UICONTROL PushEvents]** 方法。 這些方法在 [本節](event-description.md).

此事件包含連結至事件的資料，例如：

* it [type](transactional.md#create-event-types):訂單確認、在網站上建立帳戶等，
* 電子郵件地址或電話號碼，
* 傳送前要擴充及個人化交易式訊息的任何其他資訊：客戶聯絡資訊、訊息語言、電子郵件格式等。

事件資料範例：

![](assets/mc-event-request.png)

若要處理交易式訊息事件，會對執行例項套用下列步驟：

1. [事件集合](#event-collection)
1. [事件傳輸至訊息範本](#routing-towards-a-template)
1. 使用個人化資料擴充事件
1. [傳遞執行](delivery-execution.md)
1. [事件回收](#event-recycling) 其連結傳送失敗(透過Adobe Campaign工作流程)

完成所有步驟後，每個目標收件者都會收到個人化訊息。

## 收集事件 {#event-collection}

資訊系統生成的事件可以使用兩種模式來收集：

* 對SOAP方法的呼叫可讓您推送Adobe Campaign中的事件：pushEvent方法可讓您一次傳送一個事件，而PushEvents方法可讓您一次傳送多個事件。 [了解更多資訊](event-description.md)。

* 建立工作流程可讓您透過匯入檔案或透過SQL閘道(使用 [同盟資料存取](../connect/fda.md) 模組。

收集事件後，當等待連結至 [訊息範本](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>在執行例項上， **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 資料夾不能設定為檢視，因為這可能會導致存取正確的問題。 有關將資料夾設定為視圖的詳細資訊，請參閱 [本節](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## 將事件傳輸至範本 {#event-to-template}

在執行例項上發佈訊息範本後，就會自動產生兩個範本：一個要連結至即時事件，另一個要連結至批次事件。

路由步驟包括根據以下條件將事件連結到相應的消息模板：

* 在事件本身的屬性中指定的事件類型：

   ![](assets/event-type-sample.png)

* 在消息模板屬性中指定的事件類型：

   ![](assets/event-type-select.png)

依預設，路由依賴下列資訊：

* 事件類型
* 要使用的通道(預設為：電子郵件)
* 根據發佈日期的最新傳送範本

## 檢查事件狀態 {#event-statuses}

所有已處理的事件都會分組為單一檢視，位於 **事件歷史記錄** 檔案夾或檔案總管。 可依事件類型或依 **狀態**.

可能的狀態包括：

* **待處理**

   * 待定事件可以是剛收集且尚未處理的事件。 此 **[!UICONTROL Number of errors]** 欄顯示值0。 尚未連結電子郵件範本。
   * 待定事件也可以是已處理的事件，但其確認錯誤。 此 **[!UICONTROL Number of errors]** 欄會顯示非0的值。 若要知道此事件何時會再次處理，請參閱 **[!UICONTROL Process requested on]** 欄。

* **待定傳送**
已處理事件並連結傳送範本。 電子郵件擱置傳送，且會套用傳統傳送程式。 如需詳細資訊，您可以開啟傳送。
* **已傳送**, **已忽略** 和 **傳送錯誤**
這些傳送狀態會透過 
**updateEventsStatus** 工作流程。 如需詳細資訊，您可以開啟相關的傳送。
* **未涵蓋的事件**
事務報文傳送路由階段失敗。 例如，Adobe Campaign找不到可作為事件範本的電子郵件。
* **事件已過期**
已達到傳送嘗試次數上限。 該事件被視為null。

## 回收事件 {#event-recycling}

如果在特定通道上傳送訊息失敗，Adobe Campaign可以使用不同通道重新傳送訊息。 例如，如果SMS通道上的傳送失敗，會使用電子郵件通道重新傳送訊息。

若要這麼做，您需要設定工作流程，重新建立所有具有 **傳送錯誤** 狀態，並為其指派不同的通道。

>[!CAUTION]
>
>此步驟只能使用工作流程執行，因此會保留給專家使用者。 如需詳細資訊，請連絡您的Adobe帳戶主管。
