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
>Adobe Campaign Web UI隨附重新打造的工作流程畫布，可建立更動態且個人化的客戶歷程。 若要深入瞭解Web UI的工作流程，請參閱[Adobe Campaign Web UI檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/wf/gs-workflows){target=_blank}。


## 設計和使用工作流程 {#gs-ac-wf}

使用Adobe Campaign工作流程來提高行銷活動各方面的速度和規模，從建立區段和準備訊息到傳送。

瞭解如何在這些[端對端使用案例](#end-to-end-uc)中設計工作流程。

在以下頁面中進一步瞭解工作流程使用者介面與執行：

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant){target="_blank"}

* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target="_blank"}

* [內建技術工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=zh-Hant){target="_blank"}

* [監視工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hant){target="_blank"}

* [在行銷活動工作流程中建立對象](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant){target="_blank"}

## 工作流程活動 {#wf-activities}

在[本節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=zh-Hant){target="_blank"}中進一步瞭解可用的工作流程活動

工作流程活動會依類別分組。 有四種活動類別可供使用：

* [目標定位活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=zh-Hant){target="_blank"}：查詢、讀取清單、擴充、聯合等
* [流量控制活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=zh-Hant){target="_blank"}：排程器、分支、警示、外部訊號等
* [動作活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=zh-Hant){target="_blank"}：跨頻道傳遞、Javascript程式碼、CRM活動、更新彙總等
* [事件活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=zh-Hant){target="_blank"}：檔案傳輸、網頁下載等

### 變更資料來源活動 {#change-data-source-activity}

**[!UICONTROL Change data source]**&#x200B;活動可讓您變更工作流程&#x200B;**[!UICONTROL Working table]**&#x200B;的資料來源。 這為管理不同資料來源（例如FDA、FFDA和本機資料庫）的資料提供更大的彈性。

**[!UICONTROL Working table]**&#x200B;可讓Adobe Campaign工作流程處理資料，並與工作流程活動共用資料。
根據預設，**[!UICONTROL Working table]**&#x200B;會與我們查詢的資料來源建立在同一資料庫中。

例如，當查詢儲存在雲端資料庫上的&#x200B;**[!UICONTROL Profiles]**&#x200B;資料表時，您將在相同的雲端資料庫上建立&#x200B;**[!UICONTROL Working table]**。
若要變更此專案，您可以新增&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動，為您的&#x200B;**[!UICONTROL Working table]**&#x200B;選擇不同的資料來源。

請注意，使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動時，您必須切換回雲端資料庫才能繼續執行工作流程。

若要使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活動：

1. 建立工作流程。

1. 查詢具有&#x200B;**[!UICONTROL Query]**&#x200B;活動的目標收件者。

   如需&#x200B;**[!UICONTROL Query]**&#x200B;活動的詳細資訊，請參閱[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"}。

1. 從&#x200B;**[!UICONTROL Targeting]**&#x200B;索引標籤，新增&#x200B;**[!UICONTROL Change data source]**&#x200B;活動並連按兩下以選取&#x200B;**[!UICONTROL Default data source]**。

   然後會將包含查詢結果的工作表移至預設PostgreSQL資料庫。

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;索引標籤，拖放&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動以在工作表格上執行單一作業。

   如需&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活動的詳細資訊，請參閱[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=zh-Hant){target="_blank"}。

1. 新增其他&#x200B;**[!UICONTROL Change data source]**&#x200B;活動以切換回雲端資料庫。

   連按兩下您的活動，然後選取&#x200B;**[!UICONTROL Active FDA external account]**，再選取對應的外部帳戶。

1. 您現在可以開始工作流程。

## 管理虛擬倉儲 {#warehouse}

建立工作流程後，您可以使用&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕存取其他選項，以進行進一步設定。

在[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=zh-Hant){target="_blank"}中進一步瞭解&#x200B;**工作流程屬性**。

在工作流程&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Execution]**&#x200B;標籤中，您可以選擇將工作流程連結至不同的倉儲，並最佳化您的工作負載管理。 如需&#x200B;**倉儲**&#x200B;的詳細資訊，請參閱[Snowflake檔案](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}。

![](assets/warehouse.png)

根據工作流程的用途，您可以從&#x200B;**[!UICONTROL Warehouse]**&#x200B;下拉式清單中選擇下列三個倉儲：

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**：建立新工作流程時預設設定。

* **[!UICONTROL Import / Export]**：應以匯入或匯出工作流程設定，以最佳化活動的效能。

* **[!UICONTROL Campaign Burst]**：應以行銷活動或傳遞工作流程設定，以最佳化您的傳遞處理時間。

>[!NOTE]
>
>**[!UICONTROL System]**&#x200B;倉儲僅針對內建工作流程設定。

## 設定週期性行銷活動

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

  此使用案例說明如何計畫於收件者生日當天傳送定期電子郵件給收件者清單。

* [載入傳遞內容](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=zh-Hant){target="_blank"}
當您的傳送內容位於遠端伺服器的HTML檔案中時，您可以輕鬆將此內容載入到Adobe Campaign傳送中。

* [跨通道傳遞工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=zh-Hant){target="_blank"}
瞭解如何建立跨通道傳遞工作流程。 目標在於將對象從資料庫的收件者細分為不同的群組，並傳送電子郵件給第一個群組，及簡訊給另一個群組。

* [使用自訂日期欄位擴充電子郵件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=zh-Hant){target="_blank"}
瞭解如何傳送包含自訂資料欄位的電子郵件給本月慶祝生日的設定檔。 電子郵件將包含優惠券，有效期限為生日前一週，生日後一週。

Campaign v7檔案中的這些頁面：

* [自動建立、編輯和發佈內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=zh-Hant){target="_blank"}
瞭解如何使用Campaign內容管理附加元件自動建立及傳送內容區塊。

* [A/B測試](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=zh-Hant){target="_blank"}
瞭解如何透過定位工作流程比較兩個電子郵件傳遞內容。 訊息和文字在兩個傳送中均相同：只有版面配置會變更。 目標母體分為三組：兩個測試群組及剩餘母體。 會將不同版本的傳遞傳送傳送至每個測試群組。

### 監視 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [傳送報告至清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=zh-Hant){target="_blank"}
瞭解如何以PDF格式產生每月內建的追蹤指標報告，並將其傳送給Campaign運運算元清單。

* [監督您的工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=zh-Hant){target="_blank"}
瞭解如何建立工作流程，以讓您監視一組「已暫停」、「已停止」或「發生錯誤」的工作流程的狀態。

* [傳送個人化警示給營運商](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=zh-Hant){target="_blank"}
瞭解如何傳送警報給運運算元，該警報會包含開啟電子報但未按一下電子報所含連結的設定檔名稱。

### 資料管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [協調資料更新](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=zh-Hant){target="_blank"}
瞭解如何在執行另一個更新操作之前檢查更新流程是否已結束。 為此，我們將設定一個執行個體變數，並讓工作流程測試執行個體是否正在執行，以決定是否繼續執行工作流程並執行更新。

* [建立摘要清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=zh-Hant){target="_blank"}
瞭解如何建立工作流程，在收集檔案並完成數個擴充功能後，可讓您建立摘要清單。 此範例是根據在商店中進行購買的聯絡人清單。

* [擴充資料](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=zh-Hant){target="_blank"}
瞭解如何根據分數將個人化傳送給參加最新競爭的個人檔案。

* [使用彙總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=zh-Hant){target="_blank"}
瞭解如何識別上次新增至資料庫的收件者。

* 使用增量查詢[每季更新清單](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=zh-Hant){target="_blank"}
瞭解如何使用增量查詢自動更新收件者清單。

* [設定週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hant){target="_blank"}
瞭解如何設計可重複使用的工作流程，以匯入來自Adobe Campaign資料庫中CRM的設定檔。

### 目標定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查詢收件者資料表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=zh-Hant){target="_blank"}
瞭解如何復原電子郵件網域為「orange.co.uk」且並非住在倫敦的收件者的名稱和電子郵件。

* [查詢傳遞資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=zh-Hant){target="_blank"}
瞭解如何定義傳送資訊的查詢以擷取設定檔的行為。

* [計算彙總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=zh-Hant){target="_blank"}
瞭解如何根據性別計算居住在倫敦的個人檔案數。

* [使用多對多關係進行查詢](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=zh-Hant){target="_blank"}
瞭解如何尋找過去7天期間未聯絡的設定檔。

* [呼叫查詢中的執行個體變數](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=zh-Hant){target="_blank"}
瞭解如何使用執行個體變數，以動態方式計算要套用至母體的分割百分比。

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=zh-Hant#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

