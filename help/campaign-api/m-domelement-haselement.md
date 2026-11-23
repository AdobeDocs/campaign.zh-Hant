---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# hasElement

透過驗證給定的准則來測試元素是否有子元素。

```text
hasElement (tagName [, attrName ] [, attrValue ])
```

## 參數

**tagName**&#x200B;搜尋專案的名稱。

**attrName**&#x200B;必須驗證指定值的屬性名稱。

**attrValue**&#x200B;屬性值。

## 傳回值

如果元素具有子系，請透過驗證給定資料傳回true，否則傳回false。

## 功能

**類別的方法：** [DOMElement](c-domelement.md)

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
