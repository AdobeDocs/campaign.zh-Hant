---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# 開始

以非同步模式啟動查詢。

```text
start (context, name, ...)
```

## 參數

**內容**&#x200B;任何將轉送至[complete](p-soapservice-complete.md)函式的使用者引數。

**名稱**&#x200B;要呼叫的方法名稱。

**...**&#x200B;函式引數。

## 傳回值

已建立的查詢。 此物件沒有屬性或函式，它對[wait](m-soapservice-wait.md)函式非常有用，可讓您等到作業結束。

## 備註

服務連線必須是非同步的。 如果連線阻塞，會發生例外狀況。 如果連線目前正在執行另一個查詢，則無法執行查詢。 在此情況下，會引發例外狀況。

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
