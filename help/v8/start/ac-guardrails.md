---
title: V8戰役護欄
description: V8戰役護欄
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 35%

---

# 產品護欄{#guardrails}

權利、產品限制和效能保護欄列於 [Adobe Campaign Managed Cloud Services產品說明頁](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}。

使用時，您將在下面找到其他護欄和限制 [!DNL Adobe Campaign]。

護欄和限制可確定本產品版本不支援或無法與其正確互操作的功能、體系結構或進程。 請仔細檢閱這些限制。

* Adobe Campaignv8不可用於本地/混合部署 — 僅作為Adobe托管Cloud Service發佈
* 現有客戶無法從現有的 Adobe Campaign 環境移轉至 Adobe Campaign v8
* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，未提供雙向資料複製：複製僅從市場活動本地資料庫到雲資料庫
* 此區段](v7-to-v8.md#gs-unavailable-features)中列出的功能，不適用於目前的 Campaign v8 版本編號[
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)、訂閱(opt-in)和取消訂閱(opt-out)機制，以及移動註冊是非同步進程。 每小時都會透過特定的技術工作流程處理請求。 [深入瞭解](../architecture/replication.md#tech-wf)
* 重複項目需要由終端使用者手動處理。 [深入瞭解](../architecture/keys.md)
* Adobe Campaignv8不支援API和Web應用程式的擴展吞吐量 — 在特定需要時，請與Adobe聯繫以獲得指導
* Adobe Campaign市場活動優化模組沒有在壓力類型規則中考慮預定交貨。 深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=zh-Hant#setting-the-period){target=&quot;_blank&quot;} 