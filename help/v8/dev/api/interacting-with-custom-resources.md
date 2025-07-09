---
title: 與自訂資源互動
description: 進一步瞭解使用API進行自訂資源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
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
