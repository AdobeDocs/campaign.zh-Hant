---
title: 使用Adobe Campaign工作流管理和自動化流程
description: 開始使用工作流程
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1678'
ht-degree: 3%

---

# 管理和自動化流程

配置市場活動以利用強大的市場活動自動化功能。

您可以設定：

* 工作流程
* 定期市場活動
* 端到端驗證週期
* 警報
* 自動發送報告
* 觸發的事件

## 設計和使用工作流{#gs-ac-wf}

使用Adobe Campaign工作流可提高營銷活動各個方面（從建立市場細分和準備消息到交付）的速度和規模。

瞭解如何在這些中設計工作流 [端到端使用案例](#end-to-end-uc)。

瞭解有關工作流用戶介面和Campaign Classicv7文檔執行的詳細資訊：

* [開始使用工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;

* [工作流最佳實踐](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target=&quot;_blank&quot;

* [內置技術工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;

* [監視工作流執行](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html){target=&quot;_blank&quot;

* [在市場營銷活動工作流中構建受眾](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;

## 工作流活動 {#wf-activities}

![](../assets/do-not-localize/book.png) 瞭解有關可用工作流活動的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-activities.html){target=&quot;_blank&quot;

工作流活動按類別分組。 有四個活動類別：

* [目標活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;:查詢、讀取清單、濃縮、聯合等
* [流控制活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html){target=&quot;_blank&quot;:調度程式、分叉、警報、外部信號等
* [行動活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;:跨渠道交付、Javascript代碼、 CRM活動、更新聚合等
* [活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;:檔案傳輸、Web下載等

### 更改資料源活動 {#change-data-source-activity}

的 **[!UICONTROL Change data source]** 活動允許您更改工作流的資料源 **[!UICONTROL Working table]**。 這為跨不同資料源（如FDA、FFDA和本地資料庫）管理資料提供了更大的靈活性。

的 **[!UICONTROL Working table]** 允許Adobe Campaign工作流處理資料並與工作流活動共用資料。
預設情況下， **[!UICONTROL Working table]** 建立的資料庫與我們查詢的資料的源資料庫相同。

例如，查詢 **[!UICONTROL Profiles]** 表，儲存在雲資料庫上，您將建立 **[!UICONTROL Working table]** 在同一雲資料庫上。
要更改此項，可以添加 **[!UICONTROL Change Data Source]** 活動，為您的 **[!UICONTROL Working table]**。

請注意，當使用 **[!UICONTROL Change Data Source]** 活動，您需要切換回雲資料庫以繼續執行工作流。

使用 **[!UICONTROL Change Data Source]** 活動：

1. 建立工作流程.

1. 使用 **[!UICONTROL Query]** 的子菜單。

   有關 **[!UICONTROL Query]** 活動，請參閱 [查詢](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) Campaign ClassicV7文檔中。

1. 從 **[!UICONTROL Targeting]** 頁籤，添加 **[!UICONTROL Change data source]** 活動，並按兩下它以選擇 **[!UICONTROL Default data source]**。

   包含查詢結果的工作表隨後將移到預設的PostgreSQL資料庫。

1. 從 **[!UICONTROL Actions]** 頁籤，拖放 **[!UICONTROL JavaScript code]** 活動，以在工作表上執行單一操作。

   有關 **[!UICONTROL JavaScript code]** 活動，請參閱 [JavaScript代碼和高級JavaScript代碼](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/sql-code-and-javascript-code.html#javascript-code) Campaign ClassicV7文檔中。

1. 添加其他 **[!UICONTROL Change data source]** 活動以切換回雲資料庫。

   按兩下活動並選擇 **[!UICONTROL Active FDA external account]** 然後是相應的外部帳戶。

1. 現在可以啟動工作流。

## 管理虛擬倉庫 {#warehouse}

建立工作流後，您可以使用 **[!UICONTROL Properties]** 的子菜單。

![](../assets/do-not-localize/book.png) 瞭解有關 **工作流屬性** 在 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/workflow-properties.html?lang=zh-Hant){target=&quot;_blank&quot;

從 **[!UICONTROL Execution]** 頁籤 **[!UICONTROL Properties]**，您可以選擇將工作流連結到不同的倉庫並優化工作量管理。 有關 **倉庫**，請參閱 [Snowflake文檔](https://docs.snowflake.com/en/user-guide/warehouses-overview.html)。

![](assets/warehouse.png)

根據工作流的用途，您可以從以下三個倉庫中進行選擇 **[!UICONTROL Warehouse]** 下拉：

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**:建立新工作流時預設設定。

* **[!UICONTROL Import / Export]**:應設定導入或導出工作流以優化活動的效能。

* **[!UICONTROL Campaign Burst]**:應設定市場活動或交貨工作流以優化交貨處理時間。

>[!NOTE]
>
>的 **[!UICONTROL System]** 倉庫僅為內置工作流設定。

## 設定定期市場活動

設計循環工作流，並在每次執行工作流時建立新的交付實例。 例如，如果您的工作流設計為每週運行一次，則在一年後將產生52個交貨。 這也意味著日誌將由每個傳遞實例分隔。

![](../assets/do-not-localize/book.png) 瞭解如何在 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns){target=&quot;_blank&quot;


## 利用觸發事件

使用市場活動事務性消息傳遞可自動執行從資訊系統觸發的事件生成的消息。 例如，這些事務性消息可以是發票、訂單確認、發運確認、密碼更改、產品不可用性通知、帳戶對帳單或網站帳戶建立。 這些消息可以單獨或通過電子郵件、簡訊或推式通知批量發送。

![](../assets/do-not-localize/glass.png) 瞭解有關中事務性消息傳遞功能的詳細資訊 [此部分](../send/transactional.md)。

連接Adobe Campaign和Adobe Analytics以檢索用戶操作併發送接近即時的個性化消息。

![](../assets/do-not-localize/glass.png) 瞭解如何將營銷活動與其他解決方案整合到 [此部分](../start/connect.md)


## 工作流端到端使用案例{#end-to-end-uc}

在本節中，您將發現利用市場活動工作流功能的各種使用案例。 這些使用案例是在Adobe Campaign Classicv7中構建的，適用於Adobe Campaignv8。

### 傳遞 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;

   瞭解如何通過目標工作流比較兩個電子郵件傳遞內容。 消息和文本在兩個遞送中都相同：只更改佈局。 目標人口分為三：兩個test群體和其餘人口。 將不同版本的傳遞發送到每個test組。

* [發送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html){target=&quot;_blank&quot;

   此使用案例介紹如何計畫在收件人生日當天向其清單發送定期電子郵件。

* [正在載入傳遞內容](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target=&quot;_blank&quot;}當您的傳遞內容位於遠程伺服器上的HTML檔案中可用時，您可以輕鬆將此內容載入到Adobe Campaign傳遞中。

* [跨渠道交付工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target=&quot;_blank&quot;

   瞭解如何構建跨渠道交付工作流。 目標是將受眾從資料庫的收件人分割為不同的組，並向第一組發送電子郵件，向另一組發送SMS。

* [具有自定義日期欄位的電子郵件豐富性](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target=&quot;_blank&quot;

   瞭解如何向本月慶祝生日的個人資料發送包含自定義資料欄位的電子郵件。 電子郵件中將包含一張在他們生日前後一週有效的優惠券。

* [自動化內容建立、編輯和發佈](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;

   瞭解如何使用市場活動內容管理附加模組自動建立和交付內容塊。


### 監視 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [將報告發送到清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html){target=&quot;_blank&quot;

   瞭解如何以PDF格式生成每月內置跟蹤指標報告並將其發送到市場活動操作員清單。

* [監控工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html){target=&quot;_blank&quot;

   瞭解如何建立工作流，以便監視「已暫停」、「已停止」或「有錯誤」的一組工作流的狀態。

* [向操作員發送個性化警報](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html){target=&quot;_blank&quot;

   瞭解如何向操作員發送警報，操作員將包含開啟新聞簡報但未按一下該通訊所包含連結的配置檔案的名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調資料更新](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html){target=&quot;_blank&quot;

   瞭解如何在執行另一個更新操作之前檢查更新進程是否已結束。 為此，我們將設定一個實例變數，並在實例正在運行時讓工作流test決定是否繼續執行工作流並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html){target=&quot;_blank&quot;

   瞭解如何建立工作流，該工作流在收集檔案並完成若干項任務後，允許您建立摘要清單。 該示例基於在商店中進行採購的聯繫人清單。

* [豐富資料](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html){target=&quot;_blank&quot;

   瞭解如何根據個人得分將個性化送貨發送給參加最新競爭的個人資料。

* [使用聚合](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html){target=&quot;_blank&quot;

   瞭解如何標識添加到資料庫的最後一個收件人。

* [使用增量查詢的季度清單更新](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html){target=&quot;_blank&quot;

   瞭解如何使用增量查詢自動更新收件人清單。

* [設定定期導入工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html){target=&quot;_blank&quot;

   瞭解如何設計可重新用於導入來自Adobe Campaign資料庫中CRM的配置檔案的工作流。

### 目標定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件人表](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html){target=&quot;_blank&quot;

   瞭解如何恢復電子郵件域為「orange.co.uk」且不居住在倫敦的收件人的姓名和電子郵件。

* [查詢傳遞資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html){target=&quot;_blank&quot;

   瞭解如何定義傳遞資訊查詢以檢索配置檔案的行為。

* [計算聚合](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html){target=&quot;_blank&quot;

   瞭解如何根據性別統計倫敦居住的檔案數量。

* [使用多對多關係進行查詢](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;

   瞭解如何查找過去7天內未聯繫的配置檔案。

* [在查詢中調用實例變數](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example){target=&quot;_blank&quot;

   瞭解如何使用實例變數動態計算要應用於總體的拆分百分比。

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

