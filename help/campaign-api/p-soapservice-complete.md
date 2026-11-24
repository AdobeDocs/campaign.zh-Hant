---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# complete

非同步查詢完成時要呼叫的函式。

```text
complete
```

## 備註

函式必須接受四個引數：

* 服務
* 結果
* 內容：這是傳遞至[start](m-soapservice-start.md)函式的引數
* 狀態

狀態可以有下列值：

* 「success」表示已收到結果。
* 「錯誤」可能表示通訊已中斷、回應結構錯誤或發生HTTP錯誤。
* 如果傳回SOAP錯誤，則為「fault」。 在此案例中，結果包含描述錯誤的物件。
* 「逾時」表示無法建立連線，或在設定的期限內未收到任何回應。

當結果為「success」時，結果會取決於傳回的引數數量：

* 如果查詢未傳回任何值，則無效
* 如果查詢傳回單一引數的值
* 表格（如果查詢傳回數個引數）

當狀態為「fault」時，結果會是包含以下屬性的物件：

* 訊息：錯誤說明訊息。
* 物件：包含錯誤詳細資訊的XML物件。

範例：

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## 功能

類別的&#x200B;**屬性：** [SoapService](c-soapservice.md)

**唯讀：**

否

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
