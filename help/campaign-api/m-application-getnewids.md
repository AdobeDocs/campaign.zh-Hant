---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

傳回內部資料庫金鑰的ID清單。

```text
getNewIds (count [, sequence ])
```

## 參數

**count**&#x200B;方法必須傳回的ID數目。

**序列**&#x200B;要使用的序列名稱。

## 傳回值

包含ID清單的表格：

## 備註

此方法等同於NLWS.xtkSession.GetNewIds()和NLWS.xtkSession.GetNewIdsEx() SOAP方法，但效率較高。

## 功能

**類別的方法：** [應用程式](c-application.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
