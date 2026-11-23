---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

檢索上次在中間來源模式下修改的傳遞記錄。

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## 參數

**startDate**&#x200B;擷取從這個日期以來修改的記錄（在中間來源伺服器上）。

**logCount**&#x200B;要擷取的記錄數上限，前提是這些記錄沒有在同一秒內更新。

發行伺服器的&#x200B;**emitterDate**&#x200B;參考日期。 用於調整傳遞記錄日期。

## 傳回值

**結果**&#x200B;輸出檔案，傳遞記錄清單。

**nextDate**&#x200B;擷取到的第一個記錄檔的日期（大於startDate）。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
