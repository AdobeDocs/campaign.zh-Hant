---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# 內文

以MemoryBuffer物件形式顯示的HTTP回應內文。

```text
body
```

## 備註

可透過[codePage](p-httpclientresponse-codepage.md)屬性存取回應本文編碼。 HTTP回應的主體以[MemoryBuffer](c-memorybuffer.md)物件的形式提供。 因此，所有適用於[MemoryBuffer](c-memorybuffer.md)的方法都適用於HTTP回應的內文。 範例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

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
