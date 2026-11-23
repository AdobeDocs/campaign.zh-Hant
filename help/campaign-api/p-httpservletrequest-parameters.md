---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 15%
---
# 引數

傳回查詢引數。

```text
parameters
```

## 備註

parameters屬性會傳回物件，其屬性符合查詢的引數。 範例：

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
document.write(name + " : " + value + "<br>")
}
```

## 功能

類別的&#x200B;**屬性：** [HttpServletRequest](c-httpservletrequest.md)

**唯讀：**

是

**可用於：**

* JSSP
* WebApp
