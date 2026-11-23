---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# 執行

同步執行工作 (在此模式下，進度資訊和取消無法使用)。

```text
String id = job.Execute ( String methodName ) const
```

## 參數

要在實體上呼叫的方法的&#x200B;**methodName**&#x200B;名稱

## 傳回值

**id**&#x200B;已建立工作的識別碼（如果在資料庫中建立的話，即使工作失敗也會傳回）

## 功能

**結構描述：** [xtk:job](s-xtk-job.md)

**靜態：**

否

**常數：**

是

僅&#x200B;**機碼：**

否
