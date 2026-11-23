---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

強制任務處理作業的下一個日期。

```text
setNextProcessingDate (timestamp)
```

## 參數

**時間戳記**&#x200B;下一個處理日期。 如果留空，系統會立即進行下一個處理。

## 傳回值

無。

## 備註

* 如果由排程器指定，則使用此方法會覆寫下一個處理日期。
* 下一個處理一律由\*\_recall()函式執行。

## 功能

**類別的方法：** [WorkflowTask](c-workflowtask.md)

**可用於：**

* 工作流程
