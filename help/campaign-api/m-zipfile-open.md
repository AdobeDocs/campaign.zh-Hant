---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# open

載入現有的封存。

```text
open ()
```

## 參數

無。

## 傳回值

無。

## 備註

若是現有的封存，您必須先呼叫⌐[fileCount](p-zipfile-filecount.md)方法來復原檔案數，或呼叫[getEntry()](m-zipfile-getentry.md)來擷取檔案。 如果檔案不存在或檔案不是有效的封存，則方法會引發例外狀況。

## 功能

**類別的方法：** [ZipFile](c-zipfile.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
