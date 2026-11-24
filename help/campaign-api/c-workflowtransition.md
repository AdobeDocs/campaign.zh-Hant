---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition （類別）

代表工作流程轉變。

轉變是不透明物件，會使用如或等方法來復原，並用來啟用工作轉變。

範例：

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## 功能

**可用於：**

* 工作流程
