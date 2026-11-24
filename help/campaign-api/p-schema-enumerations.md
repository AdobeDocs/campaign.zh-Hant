---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# 分項清單

傳回包含此結構描述中所定義[列舉](c-enumeration.md)清單的資料表。

```text
enumerations
```

## 備註

範例：

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## 功能

類別的&#x200B;**屬性：** [結構描述](c-schema.md)

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
