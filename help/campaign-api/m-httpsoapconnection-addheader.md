---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 19%
---
# addHeader

新增HTTP標頭

```text
addHeader (headerName, headerValue)
```

## 參數

**headerName**&#x200B;字元字串，是HTTP標頭的名稱。

**headerValue**&#x200B;字元字串，是HTTP標頭的內容。

## 傳回值

無。

## 備註

在SOAP呼叫期間，以這種方式指定的標頭會優先於預設標頭。 範例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.addHeader("Authorization","Basic " + memBuf.toBase64());
```

## 功能

**類別的方法：** [HttpSoapConnection](c-httpsoapconnection.md)

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
