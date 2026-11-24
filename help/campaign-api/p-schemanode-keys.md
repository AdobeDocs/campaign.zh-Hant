---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 28%
---
# 金鑰

傳回含有目前節點[SchemaKey](c-schemakey.md)索引鍵之定義的資料表。

```text
keys
```

## 備註

範例：

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
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
