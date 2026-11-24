---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# 標頭

包含所有HTTP標題的物件。

```text
header
```

## 備註

屬性的名稱不區分大小寫。 範例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

若要復原多個具有相同名稱的標頭，請使用[標頭](p-httpclientresponse-headers.md)屬性，而不要使用header屬性。

## 功能

類別的&#x200B;**屬性：** [HttpClientResponse](c-httpclientresponse.md)

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
