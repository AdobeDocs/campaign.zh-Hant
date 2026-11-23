---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

評估JavaScript範本(&lt;%= ... %>)。

```text
evaluateTemplate (template)
```

## 參數

**範本**&#x200B;要評估的範本。

## 傳回值

取代&lt;%和%>之間的運算式後的字串。

## 備註

範例：

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## 功能

**可用於：**

* 工作流程
