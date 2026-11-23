---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# connect

開啟HTTP連線並將物件傳入「保持連線」模式

```text
connect ( [hasProxy ] [, async ])
```

## 參數

如果您需要使用Proxy HTTP，請&#x200B;**hasProxy**&#x200B;布林值設為true。 預設為false。

如果連線預定要執行非同步查詢，**非同步**&#x200B;布林值會設為true。 預設為false。

## 傳回值

無。

## 備註

如果HTTP連線失敗，則會引發例外狀況。 回應屬性只有在成功呼叫執行函式後才會生效。 當您完成使用連線時，別忘了呼叫disconnect()。 範例：

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
