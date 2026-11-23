---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 10%
---
# 配置

傳回所使用的通訊協定名稱（HTTP、HTTPS等） 以存取此頁面。

```text
scheme
```

## 備註

範例：下列URL的配置：

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

傳回下列字串：

```javascript
http
```

## 功能

類別的&#x200B;**屬性：** [HttpServletRequest](c-httpservletrequest.md)

**唯讀：**

是

**可用於：**

* JSSP
* WebApp
