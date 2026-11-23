---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest （類別）

代表轉送至servlet的使用者端查詢。

此位址只有一個執行個體可透過`request`存取。 變數中。

## 方法

| 方法 | 說明 |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | 傳回查詢標頭中定義的屬性。 |
| [getParameter](m-httpservletrequest-getparameter.md) | 傳回查詢引數的值。 |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | 傳回使用者端或上次傳送要求的Proxy的IP位址。 |
| [getUTF8引數](m-httpservletrequest-getutf8parameter.md) | 傳回查詢引數的值（以UTF-8編碼）。 |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | 使用查詢編碼以字元字串形式傳回查詢內文。 |
| [轉寄](m-httpservletrequest-forward.md) | 無需透過使用者端即可將查詢重新導向至其他頁面。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [引數](p-httpservletrequest-parameters.md) | 傳回查詢引數。 |
| [Cookie](p-httpservletrequest-cookies.md) | 傳回查詢的Cookie。 |
| [requestURI](p-httpservletrequest-requesturi.md) | 傳回查詢的URL。 |
| [queryString](p-httpservletrequest-querystring.md) | 傳回查詢URL中與引數相符的部分。 |
| [配置](p-httpservletrequest-scheme.md) | 傳回所使用的通訊協定名稱（HTTP、HTTPS等） 以存取此頁面。 |
| [伺服器名稱](p-httpservletrequest-servername.md) | 傳回查詢伺服器的名稱。 |
| [伺服器連線埠](p-httpservletrequest-serverport.md) | 傳回用於連絡伺服器的連線埠號碼。 |
| [serverURL](p-httpservletrequest-serverurl.md) | 傳回用於存取伺服器的URL。 |
| [servletPath](p-httpservletrequest-servletpath.md) | 傳回查詢URL中符合servlet的區段。 |
| [contextPath](p-httpservletrequest-contextpath.md) | 傳回查詢URL符合內容的區段。 |
| [pathInfo](p-httpservletrequest-pathinfo.md) | 傳回查詢URL的其他資訊。 |
| [方法](p-httpservletrequest-method.md) | 傳回字元字串，其中包含用於呼叫此查詢的HTTP方法（GET、HEAD、POST等）。 |

## 功能

**可用於：**

* JSSP
* WebApp
