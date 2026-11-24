---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# serverPort

傳回用於連絡伺服器的連線埠號碼。

```text
serverPort
```

## 備註

範例：下列URL的serverPort：

```javascript
http://adobe.com/tw:8080/nms/test.jst
```

傳回下列字串：

```javascript
8080
```

下列URL的serverPort：

```javascript
http://adobe.com/nms/test.jst
```

傳回下列字串：

```javascript
80
```

## 功能

類別的&#x200B;**屬性：** [HttpServletRequest](c-httpservletrequest.md)

**唯讀：**

是

**可用於：**

* JSSP
* WebApp
