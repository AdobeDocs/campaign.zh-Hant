---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

新增或更新封存中的檔案。

```text
setEntry (filename, buffer)
```

## 參數

**檔案名稱**&#x200B;來源檔案的名稱。

包含檔案的&#x200B;**buffer** MemoryBuffer。

## 傳回值

無。

## 備註

在呼叫[save()](m-zipfile-save.md)方法之前，不會有效修改磁碟上的封存。

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
