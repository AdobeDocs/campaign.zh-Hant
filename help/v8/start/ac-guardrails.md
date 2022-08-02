---
title: Campaign v8 護欄
description: Campaign v8 護欄
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# 產品護欄{#guardrails}

權利、產品限制和效能護欄列於 [Adobe Campaign Managed Cloud Services 產品說明頁面](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}。

當使用 [!DNL Adobe Campaign] 時，您將找到下面其他護欄和限制。

護欄及限制可識別此版本產品不支援的功能、架構或流程，或無法正確與其相互操作的功能、架構或流程。 請仔細檢閱這些限制。

* Adobe Campaign v8 不適用於內部部署/混合部署，僅以 Adobe 管理的 Cloud Service 發行。
* 現有客戶無法從現有的 Adobe Campaign 環境移轉至 Adobe Campaign v8
* 在 [企業 (FFDA) 部署](../architecture/enterprise-deployment.md)的情境下，不提供雙向資料複製：只會從 Campaign 本機資料庫複製到雲端資料庫
* [此區段](v7-to-v8.md#gs-unavailable-features)中列出的功能，不適用於目前的 Campaign v8 版本編號
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 在 [企業 (FFDA) 部署](../architecture/enterprise-deployment.md)的情境下，訂閱 (選擇加入) 和取消訂閱 (選擇退出) 機制，以及行動註冊為非同步流程。每小時都會透過特定的技術工作流程處理請求。 [深入瞭解](../architecture/replication.md#tech-wf)
* 重複項目需要由終端使用者手動處理。 [深入瞭解](../architecture/keys.md)
* Adobe Campaign v8 不支援 API 和 Web 應用程式的額外輸送量 — 若有特定需求，請聯絡 Adobe 以取得指引
* Adobe Campaign Campaign 最佳化模組並未考慮已在壓力類型規則中排程的傳遞。 在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html?lang=zh-Hant)中瞭解更多。