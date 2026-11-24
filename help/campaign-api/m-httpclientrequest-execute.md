---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# 執行

執行HTTP查詢。

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## 參數

如果您需要使用HTTP Proxy，**hasProxy** Boolean設為true。 預設為false。

如果查詢為非同步，**非同步**&#x200B;布林值會設為true。 預設為false。

如果基礎通訊端應該允許重複使用本機位址，則&#x200B;**reuseaddr**&#x200B;布林值會設為true。 預設為false。

**內容**&#x200B;內容是任何物件，在非同步查詢的情況下，會轉送至[complete](p-httpclientrequest-complete.md)函式的第二個引數。預設為null。

**逾時**&#x200B;非同步查詢的最長等待時間（毫秒）。 如果此引數未定義，則等待時間為5分鐘。

## 傳回值

無。

## 備註

如果HTTP連線失敗，則會引發例外狀況。 [回應](p-httpclientrequest-response.md)屬性只有在成功呼叫執行函式之後才會生效。 範例：

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
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
