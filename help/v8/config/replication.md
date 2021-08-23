---
product: Adobe Campaign
title: 技術工作流程和資料復寫
description: 技術工作流程和資料復寫
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 6334178f6e5d0ad0a33975838be6cf663862d892
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# 技術工作流程和資料復寫

## 技術工作流程{#tech-wf}

Adobe Campaign隨附一組內建的技術工作流程。 技術工作流程會執行定期在伺服器上排程的程式或作業。

這些工作流程會在資料庫上執行維護作業、運用傳送記錄檔中的追蹤資訊、建立週期性促銷活動等。

↗️[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}中詳細說明了技術工作流的完整清單


除了這些技術工作流程外，Campaign v8還仰賴特定技術工作流程來管理[資料復寫](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流程會自動復寫需要存在於Campaign本機資料庫(Postgres)和雲端資料庫([!DNL Snowflake])上的內建表格。排程每小時執行一次。 如果&#x200B;**lastModified**&#x200B;欄位存在，則複製會以增量方式進行，否則將複製整個表。 以下陣列中的表的順序是複製工作流使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流程會複製統一呼叫的中繼資料。排程每小時執行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流程會立即部署至雲端資料庫。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流將複製給定外部帳戶的XS資料。

這些技術工作流程可從Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;節點取得。 **不得更改它們。**

如有需要，您可以手動啟動資料同步。 要執行此操作，請按一下右鍵&#x200B;**調度程式**&#x200B;活動，然後選擇&#x200B;**立即執行掛起任務**。

## 資料複製{#data-replication}

有些內建表格會透過上述專用工作流程，從Campaign本機資料庫複製到[!DNL Snowflake]雲端資料庫。

了解Adobe Campaign v8使用的資料庫、複製資料的原因、正在複製的資料以及複製過程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 資料複製策略

複製策略基於表的大小。 有些表將即時複製，有些表將按小時複製。 某些表在替換其他表時將進行增量更新。

除了內建的&#x200B;**複製參考表**&#x200B;技術工作流之外，您還可以在工作流中強制進行資料複製。

您可以：

* 使用下列程式碼新增特定&#x200B;**Javascript程式碼**&#x200B;活動：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 使用以下命令添加特定的&#x200B;**nlmodule**&#x200B;活動：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)



**相關主題**

↗️了解如何開始使用[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}中的工作流程

??存取[此區段](../dev/datamodel-best-practices.md#data-retention)中的資料保留期
