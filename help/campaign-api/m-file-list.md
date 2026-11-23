---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# 清單

列出目錄的內容。

```text
list ( [mask ] [, sort ] [, noCase ])
```

## 參數

**遮罩**&#x200B;搜尋遮罩（\*依預設）。

**排序** true以排序結果（預設為false）。

**noCase** true可在排序時忽略類別（預設為false）。

## 傳回值

包含符合指定路徑與遮罩之檔案（ [檔案](c-file.md) ）清單的資料表。

## 備註

在Linux中，目錄名稱必須以/結尾，在Windows中必須以\\結尾。 範例：

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
```

## 功能

**類別的方法：** [檔案](c-file.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
