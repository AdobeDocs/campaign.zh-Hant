---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

從日誌和傳遞狀態中檢索上次的記錄。

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## 參數

**deliveryId**&#x200B;傳遞識別碼

**lastLogId**&#x200B;上次呼叫中傳回的最後一個日誌專案的識別碼

## 傳回值

**deliveryState**&#x200B;傳遞狀態

**returnLogs**&#x200B;日誌訊息

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
