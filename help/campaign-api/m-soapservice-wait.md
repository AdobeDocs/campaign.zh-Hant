---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# 等待

會等待非同步SOAP查詢清單的結尾。

```text
wait (requests)
```

## 參數

**要求**&#x200B;查詢資料表。

## 傳回值

無。

## 備註

此函式不適用於服務，但是SoapService bin的函式。 範例：

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

查詢完成後，就會自動從清單中刪除。 這表示當函式傳回控制項時，作為引數傳遞的表格將會是空的。 清單可由[complete](p-soapservice-complete.md)函式修改：例如，可以開始新的查詢並將其新增至清單。

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
