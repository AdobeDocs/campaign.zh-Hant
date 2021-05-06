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
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 1%

---

# 技術工作流程與資料複製

## 技術工作流程

Adobe Campaign提供一套內建的技術工作流程。 技術工作流程會定期在伺服器上執行程式或工作。

這些工作流程會對資料庫執行維護作業、運用傳送記錄檔中的追蹤資訊、建立週期性促銷活動等。

:arrow_upper_right:[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)中詳細列出了技術工作流程

除了這些技術工作流程外，Campaign v8還依賴特定的技術工作流程來管理[資料複製](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流程會自動複製需要存在於Campaign本機資料庫(Postgres)和雲端資料庫(Snowflake)上的參考表。計畫每小時執行一次。 如果 
**** lastModified欄位存在，複製會以增量方式進行，否則會複製整個表。下面陣列中表的順序是複製工作流使用的順序。
* **[!UICONTROL Replicate Staging data]**
此工作流程會複製單一呼叫的測試資料。計畫每小時執行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流程會立即部署至雲端資料庫。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流程會複製特定外部帳戶的XS資料。

這些技術工作流程可從促銷活動總管的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;節點取得。

## 資料複製{#data-replication}

表格會透過上述說明的專屬工作流程，從Campaign資料庫複製至Snowflake雲端資料庫。

複製策略基於表的大小。 將複製某些表。 有些表格將即時複製，而有些表格則會每小時複製。 某些表在替換其他表時會有增量更新。

**我們應該列出所有表格嗎？**

要檢查

**相關主題**

:arrow_upper_right:瞭解如何開始使用[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)中的工作流

：球：存取[本節](../dev/datamodel-best-practices.md#data-retention)中的資料保留期
