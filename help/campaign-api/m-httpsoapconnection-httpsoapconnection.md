---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# HttpSoapConnection

建立與SOAP伺服器的HTTP連線。

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## 參數

包含路徑之伺服器的&#x200B;**url** URL。

**codepage** SOAP呼叫序列化的編碼。 此選用引數可讓您指定字元編碼。 依預設，編碼為UTF-8。 範例：

* iso-8859-1
* utf-8
* utf-16

**通訊協定**&#x200B;使用的SOAP通訊協定型別。 此選用引數可讓您指定使用的SOAP通訊協定，預設為SOAP\_11。可能值：

* SOAP\_11： SOAP通訊協定1.1。
* SOAP\_12： SOAP通訊協定1.2。
* 0： Adobe Campaign內部的SOAP通訊協定。

如果連線預定要執行非同步查詢，**非同步**&#x200B;布林值會設為true。 預設為false。

## 傳回值

無。

## 備註

範例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
