---
solution: Campaign Classic
product: campaign
title: 技術工作流程與資料複製
description: 技術工作流程與資料複製
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 54837c7da2382696718ace7ec0ebde956efd33f4
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# 技術工作流程與資料複製

## 技術工作流程

Adobe Campaign提供一套內建的技術工作流程。 技術工作流程會定期在伺服器上執行程式或工作。

這些工作流程會對資料庫執行維護作業、運用傳送記錄檔中的追蹤資訊、建立週期性促銷活動等。

:arrow_upper_right:[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)中詳細列出了技術工作流程

除了這些技術工作流程外，Campaign v8還依賴特定的技術工作流程來管理[資料複製](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流程會自動複製需要存在於Campaign本機資料庫(Postgres)和雲端資料庫([!DNL Snowflake])上的參考表。計畫每小時執行一次。 如果&#x200B;**lastModified**&#x200B;欄位存在，則複製將以增量方式進行，否則將複製整個表。 下面陣列中表的順序是複製工作流使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流程會複製單一呼叫的測試資料。計畫每小時執行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流程會立即部署至雲端資料庫。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流程會複製特定外部帳戶的XS資料。

這些技術工作流程可從促銷活動總管的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;節點取得。


**相關主題**

:arrow_upper_right:瞭解如何開始使用[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)中的工作流

：球：存取[本節](../dev/datamodel-best-practices.md#data-retention)中的資料保留期


## 資料複製{#data-replication}

表格會透過上述描述的專屬工作流程從Campaign資料庫複製到[!DNL Snowflake]雲端資料庫。

複製策略基於表的大小。 將複製某些表。 有些表格將即時複製，而有些表格則會每小時複製。 某些表在替換其他表時將具有增量更新。

| 命名空間 | 表格 | 工作流複製 | 即時複製 |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK** | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:operator<br>xtk:group<br>xtk:report<br>xtk:olapCube<br>xtk:olapDimensimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br><br> | 是（增量） | 是 |
| **XTK** | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | 是（完整） | 是 |
| **NMS** | nms:budget<br>nms:program<br>nms:operation<br>nms:plan<br>nms:pryposticRule<br>nms:prypostic<br>nms:extAccount<br>nms:deliveryMapping<br>nms:delivery（立即複製）<br>nms:nms:seedMems:s:s:seripermerember&lt;a9:nms:nms:nms&lt;a9:nms:nms:nmswebApp<br>nms:trackingUrl（立即複製）<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offer<br>nmsofferView<br>nms:recipient(incremental?)<br><br>nms:<br>groupnms:<br>dlvExclusionnms:stock | 是（增量） | 是 |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp<br>:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:expenseLine<br>nms costLine<br><br> | 是（完整） | 是 |
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:broadLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms:apSubscription<br>nms:composition<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:compositionRcp<br>nms:localValidationRcp<br>nms:visitor<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>:nms:compositionVisitor<br>:nms webAppLogRcp&lt;a20/nms:appSubscriptionRcp<br>nms:broadLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms:eventHisto&lt;anms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:subscription<br>nms:subHisto<br>nms:trackingStats(僅Snowflake使用)<br>nmpsBroadcast(僅限Snowflake使用)<br>nms:tmpBroadcastExclusion(僅限Snowflake使用)<br>nms:tmpBroadcastPaper(僅限Snowflake使用)<br><br> | 否 | 否 |

