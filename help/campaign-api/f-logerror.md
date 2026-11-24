---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# logError

將錯誤訊息新增至工作流程執行個體的記錄檔，並暫停執行指令碼。

```text
logError (message)
```

## 參數

**訊息**&#x200B;要新增至記錄檔的訊息。

## 傳回值

無。

## 備註

進行中的任務行為就像發生錯誤一樣：標籤錯誤並暫停工作流程。 因此，此函式在明確引發工作流程錯誤並暫停它時非常有用。

## 功能

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
