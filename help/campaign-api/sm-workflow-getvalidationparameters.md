---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

傳回進行中工作流程任務的引數。

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**taskIdentifier**&#x200B;核准型別任務的識別碼（@taskIdentifier欄位）。

## 傳回值

**content**&#x200B;包含引數的XML檔案。

## 備註

傳回的檔案包含有關驗證的所有資訊、回應者以及仍可能回應者。

* 標題、creationDate、processingDate、timeout、status、abortReason和completionDate屬性對應至驗證作業中的屬性。
* isAssignee：目前運運算元位於指派給此任務的群組中。
* hasResponded：目前的運運算元已經回應。
* canReply：目前操作員可以回應(可能尚未有任何人回應，或是有多個已授權的回應。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
