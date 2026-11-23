---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask （類別）

工作流程任務的狀態。

⌐`WorkflowTask`是無法具現化的類別，而且名為`task`的工作流程活動中只有一個可存取的單一執行個體。

## 方法

| 方法 | 說明 |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | 將任務標示為已完成。 |
| [postEvent](m-workflowtask-postevent.md) | 啟動轉變。 |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | 強制任務處理作業的下一個日期。 |
| [doneTransition](m-workflowtask-donetransition.md) | 傳回活動的「完成」轉變。 |
| [errorTransition](m-workflowtask-errortransition.md) | 傳回活動的「錯誤」轉變。 |
| [transitionByType](m-workflowtask-transitionbytype.md) | 傳回與指定型別對應的轉變。 |
| [transitionByName](m-workflowtask-transitionbyname.md) | 傳回與指定名稱對應的轉變。 |
| [轉變](m-workflowtask-transitions.md) | 傳回活動的轉變清單。 |
| [等待](m-workflowtask-wait.md) | 等待訊號。 |

## 功能

**可用於：**

* 工作流程
