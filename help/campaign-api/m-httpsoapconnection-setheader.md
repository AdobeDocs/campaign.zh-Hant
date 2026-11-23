---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# setheader

指定HTTP標頭。

```text
setHeader (headerName, headerValue)
```

## 參數

**headerName**&#x200B;字元字串，是HTTP標頭的名稱。

**headerValue**&#x200B;字元字串，是HTTP標頭的內容。

## 傳回值

無。

## 備註

SOAP小酒館的酒莊酒莊。 範例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
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
