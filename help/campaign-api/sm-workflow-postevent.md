---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# PostEvent

從任何種類的活動產生事件。

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**活動**&#x200B;事件開始的活動名稱

**轉變**&#x200B;要啟動的轉變名稱。 如果此名稱是空的，將會在第一次有效轉換時發佈事件（會忽略到期型別事件）。

**引數**&#x200B;事件引數採用XML元素的形式。 元素的名稱必須是變數。 如果您不想傳遞變數，可以使用空白元素&lt;variables/>或空白字串「」。

**完成**&#x200B;指定活動的所有擱置工作已完成。

## 傳回值

無。

## 備註

* 命令在非同步模式下執行，且在方法傳回後不會立即生效。
* 呼叫此方法時必須啟動目標工作流程。 如果未啟動，則會將錯誤寫入對應的記錄檔。
* 如果呼叫方法時暫停目標工作流程，則命令會保留在佇列中，直到工作流程恢復為止。
* 活動沒有限制：不需要有進行中的任務或甚至已經完成任務。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
