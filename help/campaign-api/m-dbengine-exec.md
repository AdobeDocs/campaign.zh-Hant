---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%
---
# 執行

執行命令的別名。 此函式已過時，請使用[execute()](m-dbengine-execute.md)

```text
exec (command [, value1, ... ])
```

## 參數

**命令** SQL命令。

**value1， ...**&#x200B;命令的變數。

## 傳回值

如果這適用於已執行的指令，則更新或插入的錄製數目（如果不等於零）。

## 功能

**類別的方法：** [DBEngine](c-dbengine.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
