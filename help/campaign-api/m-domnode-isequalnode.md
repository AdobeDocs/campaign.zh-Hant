---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

比較兩個節點。

```text
isEqualNode (arg)
```

## 參數

**arg**&#x200B;第二個節點。

## 傳回值

如果兩個節點相等，則為true，否則為false。

## 備註

如果下列條件已驗證，則兩個節點相等：

* 這兩個節點是型別型別。
* nodeName、localName、namespaceURI、prefix和nodeValue屬性必須相同。
* 這兩個節點是型別型別。
* 屬性必須相等。
* 節點必須相等。

由於標準化會影響平等，建議您先標準化再進行比較。

## 功能

**類別的方法：** [DOMNode](c-domnode.md)

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
