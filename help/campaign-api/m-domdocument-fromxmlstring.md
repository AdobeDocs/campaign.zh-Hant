---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

從XML字元字串建立新檔案。

```text
fromXMLString (string)
```

## 參數

**字串** XML字元的字串。

## 傳回值

無。

## 備註

如果引數不是有效的XML檔案，則會引發例外狀況。 此函式適用於DOMDocument類別。 範例：

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
