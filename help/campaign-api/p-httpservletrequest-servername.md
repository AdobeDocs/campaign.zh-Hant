---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 12%
---
# serverName

傳回查詢伺服器的名稱。

```text
serverName
```

## 備註

範例：下列URL的serverName：

```javascript
      http://adobe.com/tw:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

傳回下列字串：

```javascript
adobe.com
```

## 功能

類別的&#x200B;**屬性：** [HttpServletRequest](c-httpservletrequest.md)

**唯讀：**

是

**可用於：**

* JSSP
* WebApp
