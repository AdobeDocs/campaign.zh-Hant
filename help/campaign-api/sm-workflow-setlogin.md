---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 3%
---
# SetLogin

變更執行帳戶。

```text
SetLogin ( String workflowId, String login )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**登入**&#x200B;操作員的登入，如果沒有操作員與此工作流程相關聯，則為空字串。

## 傳回值

無。

## 備註

與工作流程相關聯的執行帳戶可以強制特定運運算元（而非啟動工作流程的運運算元）具有執行許可權。 複製工作流程時不會傳播執行帳戶。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
