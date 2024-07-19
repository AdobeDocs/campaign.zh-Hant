---
title: 技術工作流程和資料複製
description: 技術工作流程和資料複製
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# 技術工作流程和資料複製 {#wf-data-replication}

## 技術工作流程 {#tech-wf}

在[企業(FFDA)部署](enterprise-deployment.md)的內容中，Adobe Campaign隨附一組內建的技術工作流程。 技術工作流程會定期在伺服器上執行排程的流程或工作。

這些工作流程會對資料庫執行維護操作、利用傳送記錄中的追蹤資訊、建立週期性行銷活動等。

[此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}中詳細列出完整的技術工作流程。

除了這些技術工作流程之外，Campaign v8還仰賴特定的技術工作流程來管理[資料復寫](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流程會執行內建表格的自動復寫，這些內建表格需要出現在Campaign本機資料庫(Postgres)和雲端資料庫([!DNL Snowflake])上。 排程為每小時、每天執行。 如果存在&#x200B;**lastModified**&#x200B;欄位，則會遞增進行復寫，否則會復寫整個資料表。 以下陣列中的表格順序是復寫工作流程使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流程會複製單一呼叫的分段資料。 排程為每小時、每天執行。
* **[!UICONTROL Deploy FFDA immediately]**\
  此工作流程會執行雲端資料庫的立即部署。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流程會復寫指定外部帳戶的XS資料。

這些技術工作流程可從Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]**&#x200B;節點取得。 **它們不可修改。**

如有需要，您可以手動啟動資料同步處理。 若要執行此動作，請在&#x200B;**排程器**&#x200B;活動上按一下滑鼠右鍵，然後選取&#x200B;**立即執行擱置中的工作**。

## 資料複製 {#data-replication}

部分內建表格會透過上述專用工作流程，從Campaign本機資料庫復寫至[!DNL Snowflake]雲端資料庫。

瞭解Adobe Campaign v8使用哪些資料庫、複製資料的原因、正在複製哪些資料以及複製過程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 資料複製原則 {#data-replication-policies}

複製原則是根據表格的大小。 有些表格會即時複製，有些表格則會每小時進行複製。 有些表格會有漸進式更新，而其他表格則會被取代。

除了內建的&#x200B;**復寫參考資料表**&#x200B;技術工作流程之外，您也可以在工作流程中強制進行資料復寫。

您可以：

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


**相關主題**

* [瞭解如何開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant){target="_blank"}

* [資料保留期](../dev/datamodel-best-practices.md#data-retention)
