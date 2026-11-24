---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# complete

非同步查詢完成時要呼叫的函式。

```text
complete
```

## 備註

函式必須接受三個引數：

* 查詢
* 內容
* 狀態： 「success」、「error」或「timeout」

「成功」狀態表示已收到回應，但回應可包含任何代碼（200、404、503等）。 「錯誤」狀態可能表示結構不良之回應的通訊中斷。 「逾時」狀態表示無法建立連線，或在設定的期限內未收到任何回應。 範例：

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
```

## 功能

類別的&#x200B;**屬性：** [HttpClientRequest](c-httpclientrequest.md)

**唯讀：**

否

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
