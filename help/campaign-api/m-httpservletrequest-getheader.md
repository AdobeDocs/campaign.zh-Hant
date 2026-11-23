---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

傳回查詢標頭中定義的屬性。

```text
getHeader (name)
```

## 參數

**name**&#x200B;標頭屬性的名稱。

## 傳回值

無。

## 備註

範例：

```javascript
Host: <%= request.getHeader("host") %>
```

## 功能

**類別的方法：** [HttpServletRequest](c-httpservletrequest.md)

**可用於：**

* JSSP
* WebApp
