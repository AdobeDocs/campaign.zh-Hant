---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# 執行

立即執行工作流程並等待它完成。

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**simulationMode**&#x200B;執行模擬。

**keepResult**&#x200B;保留中期結果。

**logSQL**&#x200B;是否需要儲存SQL順序的追蹤？

## 傳回值

**工作流程**&#x200B;執行結果。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
