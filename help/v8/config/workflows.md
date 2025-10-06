---
title: 使用Adobe Campaign工作流程管理和自動化流程
description: 開始使用工作流程
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 4%

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
>Adobe Campaign Web使用者介面隨附重新打造的工作流程畫布，可建立更動態且個人化的客戶歷程。 若要深入瞭解Web UI的工作流程，請參閱[Adobe Campaign Web UI檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/wf/gs-workflows){target=_blank}。


## 設計和使用工作流程 {#gs-ac-wf}

使用Adobe Campaign工作流程來提高行銷活動各方面的速度和規模，從建立區段和準備訊息到傳送。

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

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=zh-Hant){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## 管理虛擬倉儲 {#warehouse}

建立工作流程後，您可以使用&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕存取其他選項，以進行進一步設定。

在&#x200B;**此頁面**&#x200B;中進一步瞭解[工作流程屬性](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=zh-Hant){target="_blank"}。

在工作流程&#x200B;**[!UICONTROL Execution]**&#x200B;的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，您可以選擇將工作流程連結至不同的倉儲，並最佳化您的工作負載管理。 如需&#x200B;**倉儲**&#x200B;的詳細資訊，請參閱[Snowflake檔案](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}。

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

在本節[中瞭解運用行銷活動工作流程功能](../../automation/workflow/workflow-use-cases.md)的使用案例。
