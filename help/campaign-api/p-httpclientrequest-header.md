---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# 標頭

包含標頭的HTTP標頭的JavaScript物件。

```text
header
```

## 備註

標頭物件的所有屬性都可在讀取/寫入模式中存取並可列舉。 標頭物件的每個擁有者都是查詢的HTTP標頭中的一個專案。 屬性名稱不區分大小寫（HTTP標頭也是如此）。 範例：

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## 功能

類別的&#x200B;**屬性：** [HttpClientRequest](c-httpclientrequest.md)

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
