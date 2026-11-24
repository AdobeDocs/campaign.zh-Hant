---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# 回覆

回應進行中的驗證型別工作。

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**taskIdentifier**&#x200B;核准型別任務的識別碼（@taskIdentifier欄位）。

**回應**&#x200B;與回應相關聯的註解。

**choice**&#x200B;回應的選擇。 此選項必須符合要啟用的轉變名稱。

## 傳回值

無。

## 備註

目前運運算元必須在指派給任務的群組中。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
