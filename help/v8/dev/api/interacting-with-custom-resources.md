---
title: 與自訂資源互動
description: 進一步瞭解使用API進行自訂資源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
TQID: 'https://experienceleague.adobe.com/w8FCKOzUXzquVrDL2R6BJkkKWN-S1BaXZ4-sKl93iRI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
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
source-wordcount: '146'
ht-degree: 0%
---
# 與自訂資源互動 {#interacting-with-custom-resources}

**/customResources**&#x200B;端點可讓您在REST中公開Campaign自訂資源。 根據此API，可整合自訂實體和外部端點。

/customResources端點的行為與/profileAndServices端點完全相同。

此API中公開的自訂資源為：

* 所有未在/profileAndServicesExt底下公開的實體
* 所有未連結至設定檔的實體，以及這些實體的子系與孫系。
* 依預設，所有未連結至任何專案的實體，及其子系與孫系。

>[!NOTE]
>/profileAndServicesExt底下可用的自訂資源不會在/customResources API中公開。


以下是從自訂資源擷取中繼資料的範例：

```
GET /customResources/resourceType/<customResourceName>
```

若要執行建立、更新或刪除，會使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```
