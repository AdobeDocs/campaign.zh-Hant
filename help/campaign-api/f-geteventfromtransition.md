---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

傳回要經歷指定轉變的最後一個事件。

```text
getEventFromTransition (transitionName)
```

## 參數

**transitionName**&#x200B;轉換的內部名稱。

## 傳回值

已經歷指定轉變或Null的最後一個事件。 物件對應至&#39;xtk:workflowEvent&#39;結構描述中的實體。

## 功能

**可用於：**

* 工作流程
