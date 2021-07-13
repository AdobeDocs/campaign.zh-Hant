---
product: Adobe Campaign
title: 使用Adobe Campaign工作流程管理並自動化流程
description: 開始使用工作流程
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 2%

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

## 設計和使用工作流程{#gs-ac-wf}

使用Adobe Campaign工作流程來改善行銷活動各個層面（從建立區段、準備訊息到傳送）的速度和規模。

了解如何在這些[端對端使用案例](#end-to-end-uc)中設計工作流程。

進一步了解Campaign Classicv7檔案中的工作流程使用者介面和執行：

↗️ [開始使用工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}
* 工作流程活動：
   * [目標定位活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}:查詢、讀取清單、擴充、聯合等
   * [流量控制活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html){target=&quot;_blank&quot;}:排程器、分支、警報、外部訊號等
   * [動作活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;}:跨通道傳送、Javascript程式碼、CRM活動、更新匯總等
   * [事件活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;}:檔案傳輸、網頁下載等↗️   [在行銷活動工作流程中建立對象](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;} ↗️   [工作流程最佳作法](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html){target=&quot;_blank&quot;} ↗️  [內建技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;} ↗️  [監視工作流程執行](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html){target=&quot;_blank&quot;}


## 設定循環促銷活動

設計循環工作流程，並在每次執行工作流程時建立新的傳送例項。 例如，如果您的工作流程設計為每週執行一次，則一年後會產生52個傳送。 這也表示記錄檔將依每個傳送例項分隔。

↗️了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns){target=&quot;_blank&quot;}中建立循環促銷活動


## 運用觸發事件

使用Campaign交易式訊息來自動化從資訊系統觸發的事件產生的訊息。 例如，這些交易式訊息可以是發票、訂單確認、發運確認、密碼更改、產品不可用通知、帳戶對帳單或網站帳戶建立。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知批次傳送。

??在[本小節](../send/transactional.md)中深入了解交易式訊息功能。

連線Adobe Campaign和Adobe Analytics以擷取使用者動作並傳送近乎即時的個人化訊息。

??在[本小節](../start/connect.md)中了解如何將Campaign與其他解決方案整合


## 工作流程端對端使用案例{#end-to-end-uc}

在本節中，您會利用Campaign工作流程功能找到各種使用案例。 這些使用案例內建於Adobe Campaign Classic v7中，並適用於Adobe Campaign v8。

### 傳遞 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;}

   了解如何透過目標工作流程比較兩個電子郵件傳送內容。 訊息和文字在兩個傳送中都相同：只有版面會變更。 目標人口分為三個：兩個測試群組和剩餘母體。 傳送的不同版本會傳送至每個測試群組。

* [傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html){target=&quot;_blank&quot;}

   此使用案例說明如何規劃在收件者生日當天傳送循環電子郵件至其清單。

* [載入傳送內容](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target=&quot;_blank&quot;}當您的傳送內容位於遠端伺服器上的HTML檔案中時，您可以輕鬆將此內容載入Adobe Campaign傳送中。

* [跨通道傳送工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target=&quot;_blank&quot;}

   了解如何建立跨通道傳遞工作流程。 目標是將受眾從您資料庫的收件者細分為不同的群組，並傳送電子郵件給第一個群組，以及傳送簡訊給另一個群組。

* [使用自訂日期欄位](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target=&quot;_blank&quot;}擴充電子郵件

   了解如何傳送包含自訂資料欄位的電子郵件給本月生日的設定檔。 電子郵件將包含一週前和一週後有效的抵用券。

* [自動建立、編輯和發佈內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;}

   了解如何使用Campaign Content Management附加元件，自動建立和傳送內容區塊。


### 監視 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [將報表傳送至清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html){target=&quot;_blank&quot;}

   了解如何以PDF格式產生每月內建的追蹤指標報表，並將其傳送至Campaign運算子清單。

* [監督您的工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html){target=&quot;_blank&quot;}

   了解如何建立工作流程，讓您監控「暫停」、「停止」或「有錯誤」之工作流程集的狀態。

* [傳送個人化警報給運算子](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html){target=&quot;_blank&quot;}

   了解如何將警報傳送至運算子，運算子將包含開啟電子報但未點按其所包含連結之設定檔的名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調資料更新](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html){target=&quot;_blank&quot;}

   了解如何在執行其他更新操作之前檢查更新過程是否已結束。 為此，我們將設定一個實例變數，並讓工作流測試是否正在運行實例以決定是否繼續執行工作流並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html){target=&quot;_blank&quot;}

   了解如何建立工作流程，此工作流程在收集檔案並執行數個擴充功能後，可讓您建立摘要清單。 此示例基於在商店中進行購買的聯繫人清單。

* [擴充資料](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html){target=&quot;_blank&quot;}

   了解如何根據分數，將個人化傳遞傳送至參加最新競爭的設定檔。

* [使用匯總](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html){target=&quot;_blank&quot;}

   了解如何識別上次新增至資料庫的收件者。

* [使用增量查詢](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html){target=&quot;_blank&quot;}更新每季清單

   了解如何使用增量查詢自動更新收件者清單。

* [設定循環匯入工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html){target=&quot;_blank&quot;}

   了解如何設計可重複用於匯入來自Adobe Campaign資料庫中CRM之設定檔的工作流程。

### 目標定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件者表](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html){target=&quot;_blank&quot;}

   了解如何復原電子郵件網域為「orange.co.uk」且未居住在倫敦的收件者的姓名和電子郵件。

* [查詢傳送資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html){target=&quot;_blank&quot;}

   了解如何定義傳送資訊的查詢以擷取設定檔的行為。

* [計算匯總](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html){target=&quot;_blank&quot;}

   了解如何根據性別來計算住在倫敦的個人資料數量。

* [使用多對多關係](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;}進行查詢

   了解如何尋找過去7天未聯絡的設定檔。

* [在查詢](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example){target=&quot;_blank&quot;}中呼叫例項變數

   了解如何使用例項變數以動態方式運算要套用至母體的分割百分比。

