---
title: 資料複製
description: 技術工作流程和資料複製
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 2%

---


# 資料複製 {#wf-data-replication}

## 原則

在[Enterprise (FFDA)部署](enterprise-deployment.md)的內容中，資料復寫可確保兩個資料庫(Campaign本機資料庫(PostgreSQL)和雲端資料庫([!DNL Snowflake]))並行運作，並保持即時同步。

雲端資料庫([!DNL Snowflake])已針對處理大型資料批次（例如更新100萬個位址）進行最佳化。 同時，Campaign本機資料庫(PostgreSQL)更適合用於個別或小型磁碟區作業，例如更新單一種子位址。 同步會在背景自動且透明地進行，確保Campaign本機資料庫(PostgreSQL)中的資料在雲端資料庫([!DNL Snowflake])中即時複製，讓兩個資料庫保持同步。 資料同步涉及結構和表格以及資料。

➡️ [探索資料復寫在視訊中的運作方式](#video)

## 複製模式 {#modes}

根據使用案例，資料複製可能會以不同的模式進行。

* **即時復寫**&#x200B;會處理必須即時複製的情況。 它仰賴特定的技術執行緒即時複製資料，以利建立擴散或更新種子位址等使用案例。
* **排定的復寫**&#x200B;在不需要立即同步處理時使用。 排定的復寫使用每小時執行的特定[技術工作流程](#workflows)來同步資料，例如型別規則。

## 復寫原則

復寫原則會定義從Campaign本機資料庫(PostgreSQL)表格復寫多少資料。 這些原則取決於表格大小和特定使用案例。 有些資料表會有累加更新，而其他資料表則會完全複製。 複製原則有三種主要型別：

* **XS**：此原則用於相對較小的資料表。 整個表格會一次複製。 增量複製可避免重複複製相同的資料，方法是使用時間戳記指標來複製最近的變更。
* **SingleRow**：此原則一次只復寫一列。 它通常用於涉及目前Campaign物件和相關物件的即時復寫。
* **SomeRows**：此原則是專為使用查詢定義或篩選器來復寫有限的資料子集所設計。 它用於需要選擇性復寫的大型表格。

## 復寫工作流程 {#workflows}

Campaign v8依賴特定技術工作流程來管理排程的資料複製。 這些技術工作流程可從Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]**&#x200B;節點取得。 **它們不可修改。**

技術工作流程會定期在伺服器上執行排程的流程或工作。 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=zh-Hant){target="_blank"}中詳細列出完整的技術工作流程。

確保資料複製的技術工作流程如下：

| 技術工作流程 | 說明 |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]** (ffdaReplicateReferenceTables) | 執行需要存在於Campaign本機資料庫(PostgreSQL)和雲端資料庫([!DNL Snowflake])上的內建資料表的自動復寫。 排程為每小時、每天執行。 如果存在&#x200B;**lastModified**&#x200B;欄位，則會遞增進行復寫，否則會復寫整個資料表。 |
| **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) | 復寫單一呼叫的中繼資料。 排程為每小時、每天執行。 |
| **[!UICONTROL Deploy FFDA immediately]** (ffdaDeploy) | 執行雲端資料庫的立即部署。 |
| **[!UICONTROL Replicate FFDA data immediately]** (ffdaReplicate) | 復寫指定外部帳戶的XS資料。 |

如有需要，您可以手動啟動資料同步處理。 若要這麼做，請在&#x200B;**排程器**&#x200B;活動上按一下滑鼠右鍵，然後選取&#x200B;**立即執行擱置中的工作**。

除了內建的&#x200B;**復寫參考資料表**&#x200B;技術工作流程之外，您還可以使用下列其中一種方法在工作流程中強制進行資料復寫

+++如何強制資料複製

* 使用下列程式碼新增特定&#x200B;**Javascript程式碼**&#x200B;活動：

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* 使用下列命令新增特定&#x200B;**nlmodule**&#x200B;活動：

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>即時復寫是由特定技術執行緒處理，而非工作流程。 此模式的設定是在serverConf.xml檔案中進行管理。 您可以設定serverConf.xml以符合特定的使用案例，例如要求XS表格以增量方式複製，而非完全複製。 如需詳細資訊，請聯絡您的 Adobe 代表。

## API

API可將自訂和現成可用的資料從Campaign本機資料庫(PostgreSQL)復寫至雲端資料庫([!DNL Snowflake])。 這些API可讓您略過預先定義的工作流程，並根據特定需求自訂複製，例如複製自訂表格。

範例：

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## 復寫佇列

當同時發生大量複製要求時，雲端資料庫([!DNL Snowflake])中可能會因為MERGE作業期間的資料表層級鎖定而發生效能問題。 為了減輕這種影響，集中式復寫工作流程會將請求分組到佇列中。

每個佇列都由技術工作流程處理，該工作流程管理特定表格的復寫，以單一MERGE作業執行擱置的要求。 這些工作流程每20秒觸發一次，以處理新的復寫請求：

| 技術工作流程 | 說明 |
|------|-----------|
| **復寫nmsDelivery佇列** (ffdaReplicateQueueDelivery) | `nms:delivery`資料表的佇列。 |
| **復寫nmsDlvExclusion佇列** (ffdaReplicateQueueDlvExclusion) | `nms:dlvExclusion`資料表的佇列。 |
| **復寫nmsDlvMidRemoteIdRel佇列** (ffdaReplicateQueueDlvMidRemoteIdRel) | `nms:dlvRemoteIdRel`資料表的佇列。 |
| **復寫nmsTrackingUrl佇列** (ffdaReplicateQueueTrackingUrl)<br/>**以並行方式復寫nmsTrackingUrl佇列** (ffdaReplicateQueueTrackingUrl_2) | `nms:trackingUrl`資料表的並行佇列，利用兩個工作流程根據不同的優先順序處理請求，以提高效率。 |

## 教學課程 {#video}

此影片主要說明Adobe Campaign v8使用哪些資料庫、複製資料的原因、正在複製哪些資料以及複製過程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

[此處](https://experienceleague.adobe.com/zh-hant/docs/campaign-learn/tutorials/overview)提供其他Campaign v8使用者端主控台教學課程。
