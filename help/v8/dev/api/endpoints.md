---
title: 端點
description: 進一步瞭解API端點。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: 'https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 9%
---
# 端點 {#endpoints}

Adobe Campaign REST API的可用端點：

* **/profileAndServices**：與立即可用的欄位互動。 無法透過此端點存取延伸欄位。
* **/profileAndServicesExt**：與設定檔或服務自訂資源擴充期間新增的自訂欄位互動。 如需自訂資源的詳細資訊，請參閱[本節](custom-resources.md)。
* **/&lt;transactionalAPI>**：與交易式訊息API互動（交易式訊息API端點的名稱取決於您的執行個體設定）。 如需詳細資訊，請參閱[本章節](managing-transactional-messages.md)。
* **/工作流程/執行**：與工作流程互動。 如需詳細資訊，請參閱[本章節](controlling-a-workflow.md)。

依預設，**profileAndServices**&#x200B;與&#x200B;**profileAndServicesExt** API可用的主要資源為：

* **/設定檔**：與Campaign資料庫的設定檔互動。 若要將設定檔新增至服務，請使用&#x200B;**/服務**&#x200B;端點。 如需Campaign中設定檔的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/服務**：管理訂閱服務。 如需Campaign中服務的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>已擴充或建立的所有其他資源只能透過&#x200B;**ProfileAndServicesExt** API使用。 它們必須連結到&#x200B;**設定檔**&#x200B;資源才能存取。
