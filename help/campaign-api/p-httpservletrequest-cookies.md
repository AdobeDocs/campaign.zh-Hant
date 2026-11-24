---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# Cookie

傳回查詢的Cookie。

```text
cookies
```

## 備註

Cookie屬性會傳回物件，其每個屬性都有相符的Cookie。 範例：

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
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
