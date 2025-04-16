---
title: 使用Adobe Campaign工作流程管理和自動化流程
description: 開始使用工作流程
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 8e1401ef0aada30d941905936b45c6c1819c83a7
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

---

# 開始使用工作流程{#gs-with-workflows}

設定Campaign以運用強大的行銷活動自動化功能。

您可以設定：

* 工作流程
* 週期性行銷活動
* 端對端驗證週期
* 警報
* 自動報告傳送
* 觸發的事件

>[!NOTE]
>
>Adobe Campaign Web UI隨附重新打造的工作流程畫布，可建立更動態且個人化的客戶歷程。 若要深入瞭解Web UI的工作流程，請參閱[Adobe Campaign Web UI檔案](https://experienceleague.adobe.com/en/docs/campaign-web/v8/wf/gs-workflows){target=_blank}。


## 設計和使用工作流程 {#gs-ac-wf}

使用Adobe Campaign工作流程來提高行銷活動各方面的速度和規模，從建立區段和準備訊息到傳送。

瞭解如何在這些[端對端使用案例](#end-to-end-uc)中設計工作流程。

在以下頁面中進一步瞭解工作流程使用者介面與執行：

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant){target="_blank"}

* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

* [內建技術工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

* [監視工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

* [在行銷活動工作流程中建立對象](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant){target="_blank"}

## 工作流程活動 {#wf-activities}

在[本節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=zh-Hant){target="_blank"}中進一步瞭解可用的工作流程活動

工作流程活動會依類別分組。 提供四種活動類別：

* [目標定位活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}：查詢、讀取清單、擴充、聯合等
* [流量控制活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}：排程器、分支、警示、外部訊號等
* [動作活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}：跨頻道傳遞、Javascript程式碼、CRM活動、更新彙總等
* [事件活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}：檔案傳輸、網頁下載等

### 變更資料來源活動 {#change-data-source-activity}

該 **[!UICONTROL Change data source]** 活動可讓您變更工作流程 **[!UICONTROL Working table]**&#x200B;的資料來源。 這為跨不同數據源（如 FDA、FFDA 和本地資料庫）管理數據提供了更大的靈活性。

這 **[!UICONTROL Working table]** 可讓Adobe Campaign工作流程處理數據並與工作流程活動共享數據。默認情況下，在 **[!UICONTROL Working table]** 與我們查詢的數據源相同的資料庫中創建。

例如，在查詢 **[!UICONTROL Profiles]** 存儲在雲資料庫上的表時，您將在同一雲資料庫上創建一個 **[!UICONTROL Working table]** 。要更改此設置，您可以添加&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動以資料來源為您的 .**[!UICONTROL Working table]**

請注意，使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動時，您必須切換回雲端資料庫才能繼續執行工作流程。

若要使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動：

1. 建立工作流程。

1. 查詢具有&#x200B;**[!UICONTROL Query]**&#x200B;活動的目標收件者。

   如需&#x200B;**[!UICONTROL Query]**&#x200B;活動的詳細資訊，請參閱[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}。

1. 從&#x200B;**[!UICONTROL Targeting]**&#x200B;索引標籤，新增&#x200B;**[!UICONTROL Change data source]**&#x200B;活動並連按兩下以選取&#x200B;**[!UICONTROL Default data source]**。

   然後會將包含查詢結果的工作表移至預設PostgreSQL資料庫。

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;索引標籤，拖放&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動以在工作表格上執行單一作業。

   如需&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動的詳細資訊，請參閱[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}。

1. 新增其他&#x200B;**[!UICONTROL Change data source]**&#x200B;活動以切換回雲端資料庫。

   連按兩下您的活動，然後選取&#x200B;**[!UICONTROL Active FDA external account]**，再選取對應的外部帳戶。

1. 您現在可以開始工作流程。

## 管理虛擬倉儲 {#warehouse}

建立工作流程後，您可以使用&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕存取其他選項，以進行進一步設定。

在[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html){target="_blank"}中進一步瞭解&#x200B;**工作流程屬性**。

在工作流程&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Execution]**&#x200B;標籤中，您可以選擇將工作流程連結至不同的倉儲，並最佳化您的工作負載管理。 如需&#x200B;**倉儲**&#x200B;的詳細資訊，請參閱[Snowflake檔案](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}。

![](assets/warehouse.png)

根據工作流程的用途，您可以從下拉清單中選擇 **[!UICONTROL Warehouse]** 以下三個倉庫：

* **[!UICONTROL Default]** / ： **[!UICONTROL Campaign]**&#x200B;建立新工作流程時預設設定。

* **[!UICONTROL Import / Export]**： 應設定匯入或匯出工作流程，以優化活動的效能。

* **[!UICONTROL Campaign Burst]**：應設定為行銷活動或傳遞工作流程，以優化您的傳遞處理時間。

>[!NOTE]
>
>倉庫 **[!UICONTROL System]** 僅為內置工作流程設置。

## 設置重複的廣告系列

設計循環工作流程，並在每次執行工作流程時建立新的傳遞執行個體。 例如，如果您的工作流程設計為每週執行一次，則在一年後會產生52個傳送。 這也表示每個傳送執行個體會分隔記錄檔。

瞭解如何在[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=zh-Hant){target="_blank"}中建立週期性行銷活動。


## 利用觸發事件

使用Campaign異動訊息，自動化從資訊系統觸發的事件產生的訊息。 這些異動訊息可以是發票、訂單確認、出貨確認、密碼變更、產品無法使用通知、帳戶對帳單或網站帳戶建立等。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知批次傳送。

在[本節](../send/transactional.md)中進一步瞭解異動訊息傳送功能。

連線Adobe Campaign和Adobe Analytics以擷取使用者動作，並傳送近乎即時的個人化訊息。

在[本節](../start/connect.md)中瞭解如何將Campaign與其他解決方案整合


## 工作流程端對端使用案例{#end-to-end-uc}

在本節中，您將找到運用Campaign工作流程功能的各種使用案例。

### 傳遞 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant){target="_blank"}

  此用例介紹了如何計劃在清單收件人生日當天向其發送定期電子郵件。

* [加載傳遞內容](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}
當您的傳遞內容在位於遠端伺服器上的 HTML 文件中可用時，您可以輕鬆地將此內容載入到Adobe Campaign傳遞中。

* [Cross-通道 傳遞 工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target="_blank"}
了解如何版本編號跨通道傳遞工作流程。 目標是將資料庫收件人的對象區段到不同的組中，並向第一個群組發送電子郵件，向另一個發送短信。

* [使用自訂日期欄位擴充電子郵件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target="_blank"}
瞭解如何傳送包含自訂資料欄位的電子郵件給本月慶祝生日的設定檔。 電子郵件將包含優惠券，有效期限為生日前一週，生日後一週。

Campaign v7檔案中的這些頁面：

* [自動建立、編輯和發佈內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target="_blank"}
瞭解如何使用Campaign內容管理附加元件自動建立及傳送內容區塊。

* [A/B測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target="_blank"}
瞭解如何透過定位工作流程比較兩個電子郵件傳遞內容。 訊息和文字在兩個傳送中均相同：只有版面配置會變更。 目標母體分為三組：兩個測試群組及剩餘母體。 會將不同版本的傳遞傳送傳送至每個測試群組。

### 監視 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [傳送報告至清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html){target="_blank"}
瞭解如何以PDF格式產生每月內建的追蹤指標報告，並將其傳送給Campaign運運算元清單。

* [監督您的工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html){target="_blank"}
瞭解如何建立工作流程，以讓您監視一組「已暫停」、「已停止」或「發生錯誤」的工作流程的狀態。

* [傳送個人化警示給營運商](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html){target="_blank"}
瞭解如何傳送警報給運運算元，該警報會包含開啟電子報但未按一下電子報所含連結的設定檔名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調數據更新](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html){target="_blank"}
瞭解如何在執行其他更新作之前檢查更新過程是否已結束。 為此，我們將設定一個執行個體變數，並讓工作流程測試執行個體是否正在執行，以決定是否繼續執行工作流程並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html){target="_blank"}
瞭解如何建立工作流程，在收集檔案並完成數個擴充功能後，可讓您建立摘要清單。 此範例是根據在商店中進行購買的聯絡人清單。

* [擴充資料](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=zh-Hant){target="_blank"}
瞭解如何根據分數將個人化傳送給參加最新競爭的個人檔案。

* [使用彙總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}
瞭解如何識別上次新增至資料庫的收件者。

* [使用增量查詢](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html){target="_blank"}進行每季清單更新
了解如何使用 增量查詢 自動更新 收件者 清單。

* [設定週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}
瞭解如何設計可重複使用以導入來自 Adobe Campaign 資料庫 CRM 的個人資料的 工作流程。

### 目標定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件者表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html){target="_blank"}
瞭解如何恢復電子郵件網域為「orange.co.uk」且不居住在倫敦的收件者的姓名和電子郵件。

* [查詢傳遞資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html){target="_blank"}
了解如何定義對傳遞信息的查詢以擷取設定檔的行為。

* [計算聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html){target="_blank"}
瞭解如何根據性別計算居住在倫敦的個人資料數量。

* [使用多對多關係進行查詢](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html){target="_blank"}
瞭解如何尋找過去7天期間未聯絡的設定檔。

* [呼叫查詢中的執行個體變數](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html){target="_blank"}
瞭解如何使用執行個體變數，以動態方式計算要套用至母體的分割百分比。

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

