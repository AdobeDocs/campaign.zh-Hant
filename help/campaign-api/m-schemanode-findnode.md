---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

傳回[SchemaNode](c-schemanode.md)的執行個體，如果節點不存在且mustExist引數設定為false，則傳回null。

```text
findNode (name [, strict ] [, mustExist ])
```

## 參數

**name** XPath代表要搜尋之節點的名稱

**strict**&#x200B;布林值，指出路徑中最後一個專案的名稱是否不存在（嚴格為false），應該做為屬性或元素來搜尋。 預設為true。

**mustExist**&#x200B;布林值，指出如果節點不存在是否必須引發例外狀況。 預設為true。

## 傳回值

如果可以找到節點，則傳回[SchemaNode](c-schemanode.md)執行個體；如果mustExist引數設為false，則傳回null。

## 備註

範例：

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

結果：

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## 功能

**類別的方法：** [SchemaNode](c-schemanode.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
