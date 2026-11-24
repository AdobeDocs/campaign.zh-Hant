---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%
---
# Simulatewithparameters

在模擬模式下啟動工作流程並提供引數給它。

```text
SimulateWithParameters ( String workflowId, XML parameters )
```

## 參數

**workflowId**&#x200B;工作流程的識別碼或內部名稱。

**引數**&#x200B;要傳遞至執行個體的引數。 這些引數將成為工作流程的執行個體變數。 此引數是XML元素，其名稱必須是變數，而且只能包含屬性。 範例：

```xml
<variables foo="abc" bar="def">
```

工作流程中的JavaScript指令碼可從instance.vars物件存取這些變數：

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## 傳回值

無。

## 備註

非同步執行命令，在方法傳回後不會立即生效。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
