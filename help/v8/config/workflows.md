---
title: 使用Adobe Campaign工作流程管理並自動化流程
description: 開始使用工作流程
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: b323dbf9504e39cca78f7082089b864544ee1633
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 3%

---

# 開始使用工作流程{#gs-with-workflows}

設定Campaign以運用強大的行銷活動自動化功能。

您可以設定：

* 工作流程
* 循環行銷活動
* 端對端驗證週期
* 警示
* 自動報表傳送
* 觸發事件

## 設計和使用工作流程{#gs-ac-wf}

使用Adobe Campaign工作流程來改善行銷活動各個層面（從建立區段、準備訊息到傳送）的速度和規模。

了解如何透過這些 [端對端使用案例](#end-to-end-uc).

進一步了解工作流程使用者介面，以及在下列頁面中執行：

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)

* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [內建的技術工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [監控工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [在行銷活動工作流程中建立對象](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant)

## 工作流程活動 {#wf-activities}

進一步了解 [本節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

工作流活動按類別分組。 有四個活動類別可供使用：

* [目標定位活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html):查詢、讀取清單、擴充、聯合等
* [流量控制活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html):排程器、分支、警報、外部訊號等
* [動作活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html):跨通道傳送、Javascript程式碼、CRM活動、更新匯總等
* [事件活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html):檔案傳輸、網頁下載等

### 變更資料來源活動 {#change-data-source-activity}

此 **[!UICONTROL Change data source]** 活動可讓您變更工作流程的資料來源 **[!UICONTROL Working table]**. 這可提供更大的彈性，可管理不同資料來源的資料，例如FDA、FFDA和本機資料庫。

此 **[!UICONTROL Working table]** 可讓Adobe Campaign工作流程處理資料，並與工作流程活動共用資料。
依預設， **[!UICONTROL Working table]** 會在與我們查詢之資料來源相同的資料庫中建立。

例如，查詢 **[!UICONTROL Profiles]** 表，儲存在雲端資料庫上，您將建立 **[!UICONTROL Working table]** 在同一個雲端資料庫上。
若要變更此項目，您可以新增 **[!UICONTROL Change Data Source]** 為您的 **[!UICONTROL Working table]**.

請注意，使用 **[!UICONTROL Change Data Source]** 活動中，您需要切換回雲端資料庫以繼續執行工作流程。

若要使用 **[!UICONTROL Change Data Source]** 活動：

1. 建立工作流程.

1. 使用 **[!UICONTROL Query]** 活動。

   如需 **[!UICONTROL Query]** 活動，請參閱 [本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. 從 **[!UICONTROL Targeting]** 標籤，新增 **[!UICONTROL Change data source]** 活動並連按兩下以選取 **[!UICONTROL Default data source]**.

   然後，將包含查詢結果的工作表移至預設的PostgreSQL資料庫。

1. 從 **[!UICONTROL Actions]** 標籤，拖放 **[!UICONTROL JavaScript code]** 在工作表上執行統一操作的活動。

   如需 **[!UICONTROL JavaScript code]** 活動，請參閱 [本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. 添加其他 **[!UICONTROL Change data source]** 切換回雲端資料庫的活動。

   連按兩下您的活動並選取 **[!UICONTROL Active FDA external account]** 然後是對應的外部帳戶。

1. 您現在可以開始工作流程。

## 管理虛擬倉庫 {#warehouse}

建立工作流程後，您可以使用 **[!UICONTROL Properties]** 按鈕以取得進一步設定。

深入了解 **工作流程屬性** in [本頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

從 **[!UICONTROL Execution]** 頁簽 **[!UICONTROL Properties]**，您可以選擇將工作流連結到不同的倉庫，並優化工作量管理。 如需 **倉庫**，請參閱 [Snowflake檔案](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

根據工作流程的用途，您可以從以下三個倉庫之間進行選擇： **[!UICONTROL Warehouse]** 下拉式清單：

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**:在建立新工作流程時預設設定。

* **[!UICONTROL Import / Export]**:應使用匯入或匯出工作流程來設定，以最佳化活動的效能。

* **[!UICONTROL Campaign Burst]**:應使用行銷活動或傳送工作流程來設定，以最佳化您的傳送處理時間。

>[!NOTE]
>
>此 **[!UICONTROL System]** 倉庫僅針對內建的工作流程進行設定。

## 設定循環促銷活動

設計循環工作流程，並在每次執行工作流程時建立新的傳送例項。 例如，如果您的工作流程設計為每週執行一次，則一年後會產生52個傳送。 這也表示記錄檔將依每個傳送例項分隔。

了解如何在 [本頁](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=zh-Hant)


## 運用觸發事件

使用Campaign交易式訊息來自動化從資訊系統觸發的事件產生的訊息。 例如，這些交易式訊息可以是發票、訂單確認、發運確認、密碼更改、產品不可用通知、帳戶對帳單或網站帳戶建立。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知批次傳送。

![](../assets/do-not-localize/glass.png) 深入了解 [本節](../send/transactional.md).

連線Adobe Campaign和Adobe Analytics以擷取使用者動作並傳送近乎即時的個人化訊息。

![](../assets/do-not-localize/glass.png) 了解如何在 [本節](../start/connect.md)


## 工作流程端對端使用案例{#end-to-end-uc}

在本節中，您會利用Campaign工作流程功能找到各種使用案例。

### 傳遞 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant)

   此使用案例說明如何規劃在收件者生日當天傳送循環電子郵件至其清單。

* [載入傳遞內容](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
若您的傳送內容位於遠端伺服器上的HTML檔案中，您便可輕鬆將此內容載入Adobe Campaign傳送中。

* [跨通道傳遞工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
了解如何建立跨通道傳遞工作流程。 目標是將受眾從您資料庫的收件者細分為不同的群組，並傳送電子郵件給第一個群組，以及傳送簡訊給另一個群組。

* [使用自訂日期欄位擴充電子郵件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
了解如何傳送包含自訂資料欄位的電子郵件給本月生日的設定檔。 電子郵件將包含一週前和一週後有效的抵用券。

Campaign v7檔案中的這些頁面：

* [自動建立、編輯和發佈內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;}了解如何使用Campaign Content Management附加元件自動建立和傳送內容區塊。

* [A/B測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;}了解如何透過目標工作流程比較兩個電子郵件傳送內容。 訊息和文字在兩個傳送中都相同：只有版面會變更。 目標人口分為三個：兩個測試群組和剩餘母體。 傳送的不同版本會傳送至每個測試群組。

### 監視 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [將報表傳送至清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
了解如何以PDF格式產生每月內建的追蹤指標報表，並將其傳送至Campaign運算子清單。

* [監督您的工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
了解如何建立工作流程，讓您監控「暫停」、「停止」或「有錯誤」之工作流程集的狀態。

* [傳送個人化警報給營運商](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
了解如何將警報傳送至運算子，運算子將包含開啟電子報但未點按其所包含連結之設定檔的名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調資料更新](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
了解如何在執行其他更新操作之前檢查更新過程是否已結束。 為此，我們將設定一個實例變數，並讓工作流測試是否正在運行實例以決定是否繼續執行工作流並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
了解如何建立工作流程，此工作流程在收集檔案並執行數個擴充功能後，可讓您建立摘要清單。 此示例基於在商店中進行購買的聯繫人清單。

* [豐富資料](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html)
了解如何根據分數，將個人化傳遞傳送至參加最新競爭的設定檔。

* [使用匯總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
了解如何識別上次新增至資料庫的收件者。

* [使用增量查詢更新每季清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
了解如何使用增量查詢自動更新收件者清單。

* [設定循環匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
了解如何設計可重複用於匯入來自Adobe Campaign資料庫中CRM之設定檔的工作流程。

### 目標定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件人表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
了解如何復原電子郵件網域為「orange.co.uk」且未居住在倫敦的收件者的姓名和電子郵件。

* [查詢傳送資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
了解如何定義傳送資訊的查詢以擷取設定檔的行為。

* [計算匯總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
了解如何根據性別來計算住在倫敦的個人資料數量。

* [使用多對多關係進行查詢](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
了解如何尋找過去7天未聯絡的設定檔。

* [在查詢中呼叫例項變數](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
了解如何使用例項變數以動態方式運算要套用至母體的分割百分比。

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

