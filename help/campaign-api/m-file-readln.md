---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# readln

讀取文字檔的一行。

```text
readln ()
```

## 參數

無。

## 傳回值

包含檔案下一行的字串，如果達到檔案結尾，則為⌐null。

## 備註

範例：

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
f.close()
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
