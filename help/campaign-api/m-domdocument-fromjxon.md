---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# fromJXON

從JXON物件建立新檔案。

```text
fromJXON (obj)
```

## 參數

**obj**&#x200B;代表要建立之XML檔案的JXON物件。

## 傳回值

無。

## 備註

傳遞DOMDocument或DOMElement作為引數的函式也直接接受JXON物件。 不需要使用此函式建置中介物件。 如果物件不是有效的JXON物件，則會引發例外狀況。 此函式適用於DOMDocument類別。 範例：

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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
