---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

從另一份檔案建立節點副本。

```text
importNode (importedNode, deep)
```

## 參數

**importedNode** Source節點。

如果必須複製完整節點，則為&#x200B;**deep** true，否則為false。

## 傳回值

節點的副本。

## 備註

範例：

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
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
