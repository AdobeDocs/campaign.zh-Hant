---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# 等待

等候至非同步查詢清單結束。

```text
wait (requests,waitAll)
```

## 參數

**要求**&#x200B;查詢資料表。

**waitAll**&#x200B;布林值（預設為true），等待查詢清單中的所有要求完成。 當設為false時，如果完成至少一個要求，函式會離開接聽回圈。

## 傳回值

無。

## 備註

函式不適用於查詢，但是HttpClientRequest bin的函式。 範例：

```javascript
var req = new HttpClientRequest("http://www.adobe.com/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

只有在查詢為非同步且[execute](m-httpclientrequest-execute.md)呼叫未引發例外狀況時，才能將查詢新增至清單。 查詢完成後，就會自動從清單中刪除。 這表示當函式傳回控制項時，作為引數傳遞的表格將會是空的。 清單可由[complete](p-httpclientrequest-complete.md)函式修改：例如，可以開始新的查詢並將其新增至清單。

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
