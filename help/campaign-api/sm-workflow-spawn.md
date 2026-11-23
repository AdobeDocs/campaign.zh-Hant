---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# 繁殖

從範本建立工作流程執行個體、套用修補程式，然後啟動此工作流程。

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## 參數

**工作流程識別碼**&#x200B;工作流程範本的識別碼或內部名稱。

**patch**&#x200B;必須先與模型合併以取得執行個體的XML專案，才能執行它。 範例：

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

此範例取代&#39;notepad&#39;活動的引數。 如果您不想套用此修補程式，請使用空的&lt;workflow/>元素或空字串。

## 傳回值

從範本建立的執行個體的&#x200B;**instanceId**&#x200B;識別碼。

## 備註

命令在非同步模式下執行，且在方法傳回後不會立即生效。 工作流程是以呼叫操作員的帳戶開始。

## 功能

**結構描述：** [xtk:workflow](s-xtk-workflow.md)

**靜態：**

是
