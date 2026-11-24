---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# SoapService

建立服務以呼叫Web服務的函式。

```text
SoapService (cnx, namespace)
```

## 參數

**cnx** ([HttpSoapConnection](c-httpsoapconnection.md)) HTTP連線。

**名稱空間**&#x200B;服務的名稱空間。

## 傳回值

無。

## 備註

範例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## 功能

**類別的方法：** [SoapService](c-soapservice.md)

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
