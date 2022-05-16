---
title: 技術工作流和資料複製
description: 技術工作流和資料複製
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---

# 技術工作流和資料複製

## 技術工作流程{#tech-wf}

Adobe Campaign提供了一套內置的技術工作流程。 技術工作流在伺服器上定期執行進程或作業。

這些工作流在資料庫上執行維護操作，利用交貨日誌中的跟蹤資訊，建立經常性市場活動等。

![](../assets/do-not-localize/book.png) 技術工作流的完整清單詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;


除了這些技術工作流之外，活動v8還依賴特定的技術工作流來管理 [資料複製](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流執行內置表的自動複製，這些表需要在市場活動本地資料庫(Postgres)和雲資料庫([!DNL Snowflake])。 計畫每小時執行一次。 如果 **上次修改時間** 欄位存在，複製以增量方式進行，否則複製整個表。 下面陣列中表的順序是複製工作流使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流複製統一調用的暫存資料。 計畫每小時執行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流將立即部署到雲資料庫。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流複製給定外部帳戶的XS資料。

這些技術工作流可從 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** 市場活動瀏覽器的節點。 **不得更改它們。**

如果需要，可以手動啟動資料同步。 要執行此操作，請按一下右鍵 **調度程式** 活動和選擇 **立即執行掛起的任務**。

## 資料複製{#data-replication}

某些內置表從市場活動本地資料庫複製到 [!DNL Snowflake] 通過上述專用工作流實現雲資料庫。

瞭解Adobe Campaignv8使用的資料庫、複製資料的原因、複製資料的方式以及複製過程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 資料複製策略

複製策略基於表的大小。 一些表將即時複製，另一些表將按小時複製。 某些表在替換其他表時將具有增量更新。

除了內置 **複製引用表** 技術工作流，您可以在工作流中強制資料複製。

您可以：

* 添加特定 **Javascript代碼** 活動，代碼如下：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 添加特定 **nl模組** 活動，使用以下命令：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)



**相關主題**

![](../assets/do-not-localize/book.png) 瞭解如何開始使用中的工作流 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;

![](../assets/do-not-localize/glass.png) 訪問中的資料保留期 [此部分](../dev/datamodel-best-practices.md#data-retention)
