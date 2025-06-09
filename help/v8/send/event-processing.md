---
title: 收集和處理事件
description: 瞭解Campaign異動訊息如何收集和處理事件
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---

# 事件處理 {#event-processing}

在交易式訊息的內容中，事件是由外部資訊系統產生，並透過&#x200B;**[!UICONTROL PushEvent]**&#x200B;和&#x200B;**[!UICONTROL PushEvents]**&#x200B;方法傳送至Adobe Campaign。 在[本節](event-description.md)中說明這些方法。

此事件包含連結至事件的資料，例如：

* 其[型別](transactional.md#create-event-types)：訂單確認、在網站上建立帳戶等，
* 電子郵件地址或電話號碼，
* 在傳送之前擴充及個人化交易式訊息的任何其他資訊：客戶聯絡資訊、訊息語言、電子郵件格式等。

事件資料的範例：

![](assets/mc-event-request.png)

若要處理異動訊息事件，下列步驟將套用至執行例項：

1. [事件集合](#event-collection)
1. [事件轉移至訊息範本](#routing-towards-a-template)
1. 使用個人化資料擴充事件
1. [傳遞執行](delivery-execution.md)
1. [回收連結傳遞失敗的事件](#event-recycling) (透過Adobe Campaign工作流程)

完成所有步驟後，每個目標收件者都會收到個人化訊息。

## 收集事件 {#event-collection}

資訊系統產生的事件可使用兩種模式收集：

* 對SOAP方法的呼叫可讓您在Adobe Campaign中推送事件：PushEvent方法可讓您一次傳送一個事件，PushEvents方法則可讓您一次傳送多個事件。 [了解更多](event-description.md)。

* 建立工作流程可讓您透過匯入檔案或透過SQL閘道，搭配[同盟資料存取](../connect/fda.md)模組來復原事件。

收集到事件後，系統會根據技術工作流程，在執行個體的即時和批次佇列之間，以及等待連結至[訊息範本](transactional-template.md)時，對事件進行劃分。

![](assets/mc-event-queues.png)

>[!NOTE]
>
>在執行例項上，**[!UICONTROL Real time events]**&#x200B;或&#x200B;**[!UICONTROL Batch events]**&#x200B;資料夾不能設定為檢視，因為這樣可能會導致存取許可權問題。 如需將資料夾設定為檢視的詳細資訊，請參閱[本節](../audiences/folders-and-views.md#turn-a-folder-to-a-view)。

## 將事件轉移至範本 {#event-to-template}

在執行例項上發佈訊息範本後，就會自動產生兩個範本：一個會連結至即時事件，另一個則會連結至批次事件。

路由步驟是將事件連結至適當的訊息範本，依據為：

* 在事件本身的屬性中指定的事件型別：

  ![](assets/event-type-sample.png)

* 訊息範本屬性中指定的事件型別：

  ![](assets/event-type-select.png)

依預設，路由依賴下列資訊：

* 事件型別
* 要使用的頻道（預設：電子郵件）
* 根據發佈日期的最新傳遞範本

## 檢查事件狀態 {#event-statuses}

所有已處理的事件都會分組到&#x200B;**事件歷史記錄**&#x200B;資料夾或Explorer中的單一檢視。 它們可以依事件型別或&#x200B;**狀態**&#x200B;分類。

可能的狀態包括：

* **擱置中**

   * 擱置事件可以是剛剛收集且尚未處理的事件。 **[!UICONTROL Number of errors]**&#x200B;欄顯示值0。 尚未連結電子郵件範本。
   * 擱置事件也可以是已處理但其確認錯誤的事件。 **[!UICONTROL Number of errors]**&#x200B;資料行顯示的值不是0。 若要知道何時再次處理此事件，請參閱&#x200B;**[!UICONTROL Process requested on]**&#x200B;欄。

* **擱置的傳遞**
已處理事件，且已連結傳遞範本。 電子郵件正在等候傳遞，且已套用傳統傳遞程式。 如需詳細資訊，您可以開啟傳遞。
* **已傳送**，**已忽略**&#x200B;和&#x200B;**傳遞錯誤**
這些傳遞狀態是透過**updateEventsStatus**&#x200B;工作流程復原。 如需詳細資訊，您可以開啟相關的傳送。
* **事件未涵蓋**
異動訊息路由階段失敗。 例如，Adobe Campaign找不到當作事件範本的電子郵件。
* **事件已過期**
已達到最大傳送嘗試次數。 該事件會視為Null。

## 回收事件 {#event-recycling}

如果特定頻道上的訊息傳送失敗，Adobe Campaign可以使用其他頻道重新傳送訊息。 例如，如果簡訊頻道上的傳遞失敗，則使用電子郵件頻道重新傳送訊息。

若要這麼做，您需要設定一個工作流程，重新建立所有狀態為&#x200B;**傳遞錯誤**&#x200B;的事件，並指派不同的管道給這些事件。

>[!CAUTION]
>
>此步驟只能使用工作流程執行，因此保留給專家使用者。 如需詳細資訊，請聯絡您的Adobe帳戶主管。
