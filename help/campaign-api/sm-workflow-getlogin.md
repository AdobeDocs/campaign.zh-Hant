---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

傳回執行帳戶的資訊。

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

## 傳回值

**id**&#x200B;運運算元的識別碼，如果沒有運運算元與此工作流程相關聯，則為0。

**登入**&#x200B;操作員的登入，如果沒有操作員與此工作流程相關聯，則為空字串。

**cs**&#x200B;運運算元的描述字串，或如果無運運算元與此工作流程相關聯，則是空字串。

## 備註

與工作流程相關聯的執行帳戶可以強制特定運運算元（而非啟動工作流程的運運算元）具有執行許可權。 複製工作流程時不會傳播執行帳戶。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
