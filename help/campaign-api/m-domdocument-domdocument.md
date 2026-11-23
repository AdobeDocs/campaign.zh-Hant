---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# DOMDocument

建立新檔案。

```text
DOMDocument (name [, namespaceURI ])
```

## 參數

**名稱**&#x200B;檔名稱。

**namespaceURI**&#x200B;檔案名稱空間URI。

## 傳回值

無。

## 備註

範例：

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
```

## 功能

**類別的方法：** [DOMDocument](c-domdocument.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
