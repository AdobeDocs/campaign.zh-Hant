---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# SpawnWithParameters

從範本建立工作流程執行個體，然後叫用此執行個體上的[StartWithParameters](sm-workflow-startwithparameters.md)方法。

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## 參數

**工作流程識別碼**&#x200B;工作流程範本的識別碼或內部名稱。

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

從範本建立的執行個體的&#x200B;**instanceId**&#x200B;識別碼。

## 備註

命令在非同步模式下執行，且在方法傳回後不會立即生效。 工作流程從呼叫操作員的帳戶開始，除非特定的登入連結到工作流程登入表格中的範本，在這種情況下會使用此登入。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
