---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode （類別）

DOMNode是構成檔案的不同元件的父類別。

## 方法

| 方法 | 說明 |
| --- | --- |
| [插入在](m-domnode-insertbefore.md)之前 | 在特定位置之前插入節點。 |
| [replaceChild](m-domnode-replacechild.md) | 取代節點。 |
| [removeChild](m-domnode-removechild.md) | 刪除節點。 |
| [appendChild](m-domnode-appendchild.md) | 在子資料夾清單的結尾插入節點。 |
| [hasChildNodes](m-domnode-haschildnodes.md) | 測試節點是否至少有一個子資料夾。 |
| [標準化](m-domnode-normalize.md) | 標準化節點：合併相鄰的文位元組點，並刪除空白文位元組點。 |
| [hasAttribute](m-domnode-hasattributes.md) | 測試節點是否至少具有一個屬性。 |
| [isSameNode](m-domnode-issamenode.md) | 測試給定的參考是否代表相同的節點。 |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | 測試指定的名稱空間是否為預設值。 |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | 已搜尋連結至指定首碼的名稱空間URI。 |
| [isEqualNode](m-domnode-isequalnode.md) | 比較兩個節點。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | 合格的節點名稱。 名稱取決於節點型別。 |
| [nodeValue](p-domnode-nodevalue.md) | 節點值。 該值取決於節點的型別。 |
| [nodeType](p-domnode-nodetype.md) | 節點型別。 |
| [parentNode](p-domnode-parentnode.md) | 父節點或Null。 |
| [childNodes](p-domnode-childnodes.md) | 以表格的形式傳回子節點清單。 |
| [firstChild](p-domnode-firstchild.md) | 此節點的第一個子節點；若沒有子節點，則為null。 |
| [lastChild](p-domnode-lastchild.md) | 此節點的最後一個子節點；如果它沒有子節點，則為null。 |
| [下一個同層級](p-domnode-nextsibling.md) | 此節點之後的節點或Null。 |
| [previousSibling](p-domnode-previoussibling.md) | 立即前置於此節點或null的節點。 |
| [屬性](p-domnode-attributes.md) | 如果節點是元素，則傳回包含屬性清單的表格，否則為null。 |
| [namespaceURI](p-domnode-namespaceuri.md) | 節點名稱空間的URI。 |
| [前置詞](p-domnode-prefix.md) | 此節點的名稱空間前置詞，如果未指定，則留空。 |
| [localName](p-domnode-localname.md) | 節點限定名稱的本機部分。 |
| [baseURI](p-domnode-baseuri.md) | 此節點的基底URI。 |
| [textContent](p-domnode-textcontent.md) | 節點的文字內容。 該值取決於節點的型別。 |
| [ownerDocument](p-domnode-ownerdocument.md) | 此節點所屬的檔案。 |

## 功能

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
