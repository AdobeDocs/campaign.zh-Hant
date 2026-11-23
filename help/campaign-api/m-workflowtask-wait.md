---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# 等待

等待訊號。

```text
wait (timeout)
```

## 參數

**逾時**&#x200B;等待時間（毫秒）。

## 傳回值

如果在等待時間到期之前收到訊號，則布林值為true。

## 備註

訊號是由[Wakeup](sm-workflow-wakeup.md)和[WakeupTask](sm-workflow-wakeuptask.md) SOAP方法發出。 使用的通訊協定(UDP)無法保證訊息接收。 此訊號只適用於更快速地執行作業。 警告：子工作流程永遠不會收到此訊號。 範例：以下是典型的使用範例：回圈處理來自佇列(poll())的作業，然後等待每個作業之間的特定時間量。 新增額外的延遲，以強制進行工作流程鈍化。

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## 功能

**類別的方法：** [WorkflowTask](c-workflowtask.md)

**可用於：**

* 工作流程
