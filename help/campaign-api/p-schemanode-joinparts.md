---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinParts

傳回SchemaNode執行個體的表格，其中每個元素代表聯結的條件。

```text
joinParts
```

## 備註

表格中的每個元素都有兩個屬性：

* source — 代表來源表格欄位的元素。
* destination — 代表目的地表格欄位的元素。

範例：

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## 功能

類別的&#x200B;**屬性：** [SchemaNode](c-schemanode.md)

**唯讀：**

是

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
