---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

更新傳遞記錄的狀態、執行錯誤處理並更新傳遞計數器。

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## 參數

**deliveryId**&#x200B;傳遞識別碼

**記錄檔**&#x200B;包含要更新之nms:broadLog記錄的集合（必須指定@id、@status、@eventDate和@lastModified）

**deliveryMustExist**&#x200B;指定是否針對無效的傳遞識別碼引發錯誤。

## 傳回值

無。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
