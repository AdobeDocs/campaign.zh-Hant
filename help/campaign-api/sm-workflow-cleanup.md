---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# 清理

清除工作流程歷史記錄。

```text
Cleanup ( String workflowId )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

## 傳回值

無。

## 備註

刪除所有已處理的事件、完成的工作、失敗的工作和記錄訊息。 如果工作流程已完成，也會從圖表中刪除進度。 此方法僅會刪除工作流程引擎不再使用的資料，不會影響工作流程的行為。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
