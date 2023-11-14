---
title: 技術工作流程和資料複製
description: 技術工作流程和資料複製
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: f807963a7640773ac18d49999b561f2f3b894d7f
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 5%

---

# 技術工作流程和資料複製 {#wf-data-replication}

## 技術工作流程 {#tech-wf}

在的內容中 [企業(FFDA)部署](enterprise-deployment.md)，Adobe Campaign隨附一組內建的技術工作流程。 技術工作流程會定期在伺服器上執行排程的流程或工作。

這些工作流程會對資料庫執行維護操作、利用傳送記錄中的追蹤資訊、建立週期性行銷活動等。

![](../assets/do-not-localize/glass.png) 完整的技術工作流程清單詳見 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

除了這些技術工作流程之外，Campaign v8還仰賴特定的技術工作流程來管理 [資料復寫](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
此工作流程會執行內建表格的自動復寫，這些表格需要出現在Campaign本機資料庫(Postgres)和雲端資料庫([!DNL Snowflake])。 排程為每小時、每天執行。 如果 **lastModified** 欄位存在，會遞增複製，否則會複製整個表格。 以下陣列中的表格順序是復寫工作流程使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流程會複製單一呼叫的分段資料。 排程為每小時、每天執行。
* **[!UICONTROL Deploy FFDA immediately]**\
  此工作流程會執行雲端資料庫的立即部署。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流程會復寫指定外部帳戶的XS資料。

這些技術工作流程可從 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** Campaign Explorer的節點。 **不得更改它們。**

如有需要，您可以手動啟動資料同步處理。 若要執行此動作，請用滑鼠右鍵按一下 **排程器** 活動並選取 **立即執行擱置中的任務**.

## 資料複製 {#data-replication}

有些內建表格會從Campaign本機資料庫複製到 [!DNL Snowflake] 透過上述專用工作流程建立雲端資料庫。

瞭解Adobe Campaign v8使用哪些資料庫、複製資料的原因、正在複製哪些資料以及複製過程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 資料複製原則 {#data-replication-policies}

複製原則是根據表格的大小。 有些表格會即時複製，有些表格則會每小時進行複製。 有些表格會有漸進式更新，而其他表格則會被取代。

除了內建外， **復寫參考資料表** 技術工作流程，您可以在工作流程中強制進行資料復寫。

您可以：

* 新增特定 **Javascript程式碼** 活動，代碼如下：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 新增特定 **nlmodule** 使用下列命令的活動：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**相關主題**

* [瞭解如何開始使用工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant)

* [資料保留期](../dev/datamodel-best-practices.md#data-retention)
