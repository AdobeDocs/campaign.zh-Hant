---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

從範本中提交工作

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## 參數

**結構描述**&#x200B;工作範本結構描述

**where**&#x200B;範本選取運算式

**methodName**&#x200B;要呼叫的方法名稱

要新增至範本的&#x200B;**diff** XML內容

**非同步**&#x200B;執行非同步作業提交

## 傳回值

剛建立的&#x200B;**jobId**&#x200B;工作識別碼

## 功能

**結構描述：** [xtk:job](s-xtk-job.md)

**靜態：**

是
