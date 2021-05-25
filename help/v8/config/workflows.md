---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用行銷活動自動化
description: 開始使用行銷活動自動化
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 15b11b144d0086adf8aade0e2a3c9b388d6163dd
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 7%

---

# 管理和自動化流程

設定Campaign以運用強大的行銷活動自動化功能。

您可以設定：

* 工作流程
* 循環行銷活動
* 端對端驗證週期
* 警報
* 自動報表傳送
* 觸發事件

## 設計和使用工作流{#gs-ac-wf}

使用Adobe Campaign工作流程來改善行銷活動各個層面（從建立區段、準備訊息到傳送）的速度和規模。

進一步了解以下小節中的工作流程：

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* 工作流程活動
   * [目標定位活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html):查詢、讀取清單、擴充、聯合等
   * [流量控制活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html):排程器、分叉、警報、外部訊號等
   * [動作活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):跨通道傳送、JavaScript程式碼、CRM活動、更新匯總等
   * [事件活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):檔案傳輸、網頁下載等
* [透過端對端使用案例了解](#end-to-end-uc)
* [在行銷活動工作流程中建立對象](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [內建的技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [監控工作流程執行](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## 設定循環促銷活動

設計循環工作流程，並在每次執行工作流程時建立新的傳送例項。 例如，如果您的工作流程設計為每週執行一次，則一年後會產生52個傳送。 這也表示記錄檔將依每個傳送例項分隔。

:arrow_upper_right:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)中建立循環促銷活動。


## 運用觸發事件

使用Campaign交易式訊息來自動化從資訊系統觸發的事件產生的訊息。 例如，這些交易式訊息可以是發票、訂單確認、發運確認、密碼更改、產品不可用通知、帳戶對帳單或網站帳戶建立。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知批次傳送。

:arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging)中深入了解交易式訊息功能。


連線Adobe Campaign和Adobe Analytics以擷取使用者動作並傳送近乎即時的個人化訊息。

:arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud)中了解如何將Campaign與Analytics觸發器整合。

：燈泡：在[本小節](../start/connect.md)中了解如何將Campaign與其他解決方案整合


## 工作流程端到端使用案例{#end-to-end-uc}

在本節中，您會利用Campaign工作流程功能找到各種使用案例。 這些使用案例內建於Adobe Campaign Classic v7中，並適用於Adobe Campaign v8。

### 傳遞 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B 測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   了解如何透過目標工作流程比較兩個電子郵件傳送內容。 訊息和文字在兩個傳送中都相同：只有版面會變更。 目標人口分為三個：兩個測試群組和剩餘母體。 傳送的不同版本會傳送至每個測試群組。

* [傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   此使用案例說明如何規劃在收件者生日當天傳送循環電子郵件至其清單。

* [載入傳遞內容](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   若您的傳送內容位於遠端伺服器上的HTML檔案中，您便可輕鬆將此內容載入Adobe Campaign傳送中。

* [跨通道傳遞工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   了解如何建立跨通道傳遞工作流程。 目標是將受眾從您資料庫的收件者細分為不同的群組，並傳送電子郵件給第一個群組，以及傳送簡訊給另一個群組。

* [使用自訂日期欄位擴充電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   了解如何傳送包含自訂資料欄位的電子郵件給本月生日的設定檔。 電子郵件將包含一週前和一週後有效的抵用券。

* [自動建立、編輯和發佈內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   了解如何使用Campaign Content Management附加元件，自動建立和傳送內容區塊。


### 監控 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [傳送報吿至清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   了解如何以PDF格式產生每月內建的追蹤指標報表，並將其傳送至Campaign運算子清單。

* [監督您的工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   了解如何建立工作流程，讓您監控「暫停」、「停止」或「有錯誤」之工作流程集的狀態。

* [傳送個人化警示給營運商](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   了解如何將警報傳送至運算子，運算子將包含開啟電子報但未點按其所包含連結之設定檔的名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調資料更新](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   了解如何在執行其他更新操作之前檢查更新過程是否已結束。 為此，我們將設定一個實例變數，並讓工作流測試是否正在運行實例以決定是否繼續執行工作流並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   了解如何建立工作流程，此工作流程在收集檔案並執行數個擴充功能後，可讓您建立摘要清單。 此示例基於在商店中進行購買的聯繫人清單。

* [豐富資料](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   了解如何根據分數，將個人化傳遞傳送至參加最新競爭的設定檔。

* [使用彙總](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   了解如何識別上次新增至資料庫的收件者。

* [使用增量查詢更新每季清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   了解如何使用增量查詢自動更新收件者清單。

* [設定週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   了解如何設計可重複用於匯入來自Adobe Campaign資料庫中CRM之設定檔的工作流程。

### 目標定位{#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件者表格](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   了解如何復原電子郵件網域為「orange.co.uk」且未居住在倫敦的收件者的姓名和電子郵件。

* [查詢傳遞資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   了解如何定義傳送資訊的查詢以擷取設定檔的行為。

* [計算匯總](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   了解如何根據性別來計算住在倫敦的個人資料數量。

* [使用多對多關係進行查詢](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   了解如何尋找過去7天未聯絡的設定檔。

* [在查詢中呼叫例項變數](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   了解如何使用例項變數以動態方式運算要套用至母體的分割百分比。

