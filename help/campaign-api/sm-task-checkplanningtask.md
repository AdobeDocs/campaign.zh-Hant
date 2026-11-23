---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# 檢查計畫任務

內部函式，用於檢查任務運運算元排程內的多載（如果多載則傳回「true」）。 此功能也會檢查相關工作排程的一致性，並在必要時更新。

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## 參數

**taskId**&#x200B;工作識別碼。

## 傳回值

**workloadAlert**&#x200B;資源超載警告

## 功能

**結構描述：** [nms:task](s-nms-task.md)

**靜態：**

是
