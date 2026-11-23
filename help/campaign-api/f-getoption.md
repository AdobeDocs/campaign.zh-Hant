---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 13%
---
# getOption

傳回選項表格中選項的值。

```text
getOption (name [, useCache ])
```

## 參數

**名稱**&#x200B;選項的名稱。

**useCache**&#x200B;使用選項值快取（預設為不使用）。

## 傳回值

如果選項存在，則為選項的值，否則為未定義。 值的型別取決於選項的型別。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
