---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 17%
---
# setcontenttype

變更回應的檔案型別。

```text
setContentType (name)
```

## 參數

**名稱**&#x200B;檔案的MIME型別。

## 傳回值

無。

## 備註

範例：

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## 功能

**類別的方法：** [HttpServletResponse](c-httpservletresponse.md)

**可用於：**

* JSSP
* WebApp
