---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 14%
---
# getElementsByTagNameNS

傳回具有指定名稱和名稱空間的所有檔案元素清單。

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## 參數

**名稱空間URI**&#x200B;名稱空間URI。

**localName**&#x200B;搜尋專案的名稱。

## 傳回值

包含元素清單的表格。

## 備註

此方法會為每個呼叫建立新表格。 因此，最好將表格保留在區域變數中，而非進行數個呼叫。

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
