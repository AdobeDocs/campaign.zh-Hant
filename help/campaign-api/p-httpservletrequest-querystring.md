---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# queryString

傳回查詢URL中與引數相符的部分。

```text
queryString
```

## 備註

範例：下列URL的queryString：

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

傳回下列字串：

```javascript
id=1234&param=dummy
```

## 功能

類別的&#x200B;**屬性：** [HttpServletRequest](c-httpservletrequest.md)

**唯讀：**

是

**可用於：**

* JSSP
* WebApp
