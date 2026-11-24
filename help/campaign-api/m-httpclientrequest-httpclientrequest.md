---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# HttpClientRequest

建立新物件以執行HTTP使用者端查詢。

```text
HttpClientRequest ( [URL ])
```

## 參數

**URL**&#x200B;查詢收件者的URL。

## 傳回值

無。

## 備註

如果FTP命令失敗，則會引發例外狀況。 範例：

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

## 功能

**類別的方法：** [HttpClientRequest](c-httpclientrequest.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
