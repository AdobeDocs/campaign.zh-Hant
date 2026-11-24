---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# 終止

無條件停止工作流程。

```text
Kill ( String workflowId )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

## 傳回值

無。

## 備註

如果工作流程無法正常停止，則此方法相當實用。 如果工作流程或任務有特定的相似性，或如果處理此相似性的wfserver模組不再執行，就可能發生這種情況。 在此情況下，工作流程仍會標籤為「已要求停止」，且只能由Kill命令停止。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
