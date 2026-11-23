---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# WakeupTask

強制進階處理一或多個擱置中的工作。

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**taskIdentifier**&#x200B;工作（@taskIdentifier欄位）的識別碼或空字串，可強制提前處理與指定活動相關的所有擱置工作。

**activityName**&#x200B;強制提前處理所有關聯任務的活動名稱或空字串。

## 傳回值

無。

## 備註

如果未指定taskIdentifier或activityName，則會考慮所有擱置中的任務。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
