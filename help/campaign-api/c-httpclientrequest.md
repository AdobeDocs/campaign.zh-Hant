---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest （類別）

HttpClientRequest物件可讓您以HTTP使用者端身分執行某些作業。

範例：

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## 「保持連線」

物件可用於兩種不同的模式：標準模式或保持連線。 標準模式可讓您傳送單一查詢，保持連線開啟的狀態下，持續運作模式可讓您傳送數個查詢。 物件的狀態取決於方法使用順序。 如果呼叫connect()方法，物件會切換至「保持連線」模式。 範例

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## 非同步查詢

依預設，查詢會以封鎖模式執行，這表示

[執行](m-httpclientrequest-execute.md)

函式只會在傳送查詢及收到回應之後傳回控制項。 也可以在非同步模式下執行查詢。 在此案例中，

[執行](m-httpclientrequest-execute.md)

函式會立即傳回控制項，且在收到回應後會呼叫函式。 如此可讓您同時執行數個查詢。 以下程式是完整的範例，說明如何執行一連串同時開啟3個連線的HTTP上傳，其中每個上傳會在最後一個上傳完成後開始。

```text
var list = [ "http://www.adobe.com/tw/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## 方法

| 方法 | 說明 |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | 建立新物件以執行HTTP使用者端查詢。 |
| [連線](m-httpclientrequest-connect.md) | 開啟HTTP連線並將物件傳入「保持連線」模式 |
| [中斷連線](m-httpclientrequest-disconnect.md) | 在「保持連線」模式中關閉物件的HTTP連線。 |
| [執行](m-httpclientrequest-execute.md) | 執行HTTP查詢。 |
| [等待](m-httpclientrequest-wait.md) | 等到非同步查詢清單的結尾為止。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [內文](p-httpclientrequest-body.md) | HTTP查詢的正文。 |
| [完成](p-httpclientrequest-complete.md) | 非同步查詢完成時要呼叫的函式。 |
| [標頭](p-httpclientrequest-header.md) | 包含標頭的HTTP標頭的JavaScript物件。 |
| [方法](p-httpclientrequest-method.md) | HTTP方法，以字元字串形式表示 |
| [回應](p-httpclientrequest-response.md) | HTTP查詢的回應。 這是HttpClientResponse型別物件 |
| [url](p-httpclientrequest-url.md) | 遠端伺服器的位址。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
