---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 34%
---
# Executequery

從查詢中檢索資料

```text
XML output = queryDef.ExecuteQuery () const
```

## 參數

無。

## 傳回值

**輸出**&#x200B;輸出XML檔案

## 備註

查詢支援四種型別的作業：

* 選取
* get
* getIfExists
* count

## 範例

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## 功能

**結構描述：** [xtk:queryDef](s-xtk-querydef.md)

**靜態：**

否

**常數：**

是

僅&#x200B;**機碼：**

否
