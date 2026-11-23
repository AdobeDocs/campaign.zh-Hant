---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService （類別）

可讓您在Web服務上執行SOAP呼叫。

## 封鎖呼叫

以下是典型的使用範例：您必須先建立連線，然後使用此連線的服務，最後為此服務宣告SOAP方法。 SOAP方法會以服務物件的JavaScript方法的形式公開。

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## 非封鎖呼叫

您可以執行非封鎖（非同步）呼叫，亦即對伺服器執行SOAP查詢，並繼續執行指令碼，而不等待結果。 與封鎖模式的主要差異如下：

* 必須以非同步模式建立連線

* 使用

  [開始](m-soapservice-start.md)

  函式。

* 定義

  [complete](p-soapservice-complete.md)

  服務上的函式，將在收到回應時呼叫。

* 此

  [SoapService.wait](m-soapservice-wait.md)

  函式用於等待一組查詢的處理結束。

以下範例指令碼會透過同時開啟3個連線，對Adobe Campaign伺服器發出一連串「GetOption」SOAP呼叫。

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## 方法

| 方法 | 說明 |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | 建立服務以呼叫Web服務的函式。 |
| [addMethod](m-soapservice-addmethod.md) | 在服務上宣告函式。 |
| [處置](m-soapservice-dispose.md) | 釋放物件使用的資源。 |
| [開始](m-soapservice-start.md) | 以非同步模式啟動查詢。 |
| [等待](m-soapservice-wait.md) | 會等待非同步SOAP查詢清單的結尾。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [完成](p-soapservice-complete.md) | 非同步查詢完成時要呼叫的函式。 |
| [標頭](p-soapservice-header.md) | 在SOAP標頭中逐字複製的字元字串。 |
| [逾時](p-soapservice-timeout.md) | 非同步查詢的最大等待時間（毫秒）。 如果此引數未定義，則等待時間為5分鐘。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
