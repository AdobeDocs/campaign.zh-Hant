---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 9%
---
# HttpClientResponse （類別）

一個物件，代表對HTTP查詢的回應。

只能在`response`屬性執行HTTP查詢後取得。

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [內文](p-httpclientresponse-body.md) | 以MemoryBuffer物件形式顯示的HTTP回應內文。 |
| [代碼](p-httpclientresponse-code.md) | HTTP回應的傳回碼，以JavaScript整數的形式表示。 |
| [codePage](p-httpclientresponse-codepage.md) | 回應的codePage值。 用於解碼HTTP回應的內文。 |
| [標頭](p-httpclientresponse-header.md) | 包含所有HTTP標題的物件。 |
| [標頭](p-httpclientresponse-headers.md) | 依名稱分組的HTTP回應標頭清單。 |
| [訊息](p-httpclientresponse-message.md) | 由HTTP回應傳送的訊息。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
