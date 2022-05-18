---
title: Campaign v8 已知限制
description: 已知限制
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 72%

---

# 已知限制

已知限制可識別此版本的產品不支援的功能、架構或流程，或無法正確與其相互操作的功能、架構或流程。 請仔細檢閱這些限制。

若為 Adobe Campaign v8，則有下列限制：

* Adobe Campaign v8 不適用於內部部署/混合部署，僅以 Adobe 管理的 Cloud Service 發行。
* 現有客戶無法從現有的 Adobe Campaign 環境移轉至 Adobe Campaign v8
* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，未提供雙向資料複製：複製僅從市場活動本地資料庫到雲資料庫
* 此區段](capability-matrix.md#gs-unavailable-features)中列出的功能，不適用於目前的 Campaign v8 版本編號[
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)、訂閱(opt-in)和取消訂閱(opt-out)機制，以及移動註冊是非同步進程。 每小時都會透過特定的技術工作流程處理請求。 [深入瞭解](../architecture/replication.md#tech-wf)
* 重複項目需要由終端使用者手動處理。 [深入瞭解](../architecture/keys.md)
* Adobe Campaign v8 不支援 API 和 Web 應用程式的延長輸送量。 若有特定需求，請聯絡 Adobe 以取得指引。
* Adobe Campaign市場活動優化模組沒有在壓力類型規則中考慮預定交貨。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=zh-Hant#setting-the-period)中進一步瞭解。