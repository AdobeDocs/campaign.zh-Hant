---
title: Campaign v8 護欄
description: Campaign v8 護欄
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 84%

---

# 產品護欄{#guardrails}

權利、產品限制和效能護欄列於 [Adobe Campaign Managed Cloud Services 產品說明頁面](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}。

當使用 [!DNL Adobe Campaign] 時，您將找到下面其他護欄和限制。

護欄及限制可識別此版本產品不支援的功能、架構或流程，或無法正確與其相互操作的功能、架構或流程。 請仔細檢閱這些限制。

* Adobe Campaign v8 不適用於內部部署/混合部署，僅以 Adobe 管理的 Cloud Service 發行。
* 現有客戶無法自動移轉至 Adobe Campaign v8
* 在 [企業 (FFDA) 部署](../architecture/enterprise-deployment.md)的情境下，不提供雙向資料複製：只會從 Campaign 本機資料庫複製到雲端資料庫
* [此區段](v7-to-v8.md#gs-unavailable-features)中列出的功能，不適用於目前的 Campaign v8 版本編號
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 在 [企業 (FFDA) 部署](../architecture/enterprise-deployment.md)的情境下，訂閱 (選擇加入) 和取消訂閱 (選擇退出) 機制，以及行動註冊為非同步流程。每小時都會透過特定的技術工作流程處理請求。 [深入瞭解](../architecture/replication.md#tech-wf)
* 在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，重複專案需要由一般使用者手動處理。 [了解更多](../architecture/keys.md)
* Adobe Campaign v8 不支援 API 和 Web 應用程式的額外輸送量 — 若有特定需求，請聯絡 Adobe 以取得指引
* 在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，Adobe Campaign行銷活動最佳化模組沒有將壓力型別規則中已排程的傳遞考慮在內。 在[本頁](../../automation/campaign-opt/pressure-rules.md)中了解更多