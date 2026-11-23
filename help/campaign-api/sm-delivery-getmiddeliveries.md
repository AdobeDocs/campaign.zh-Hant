---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

檢索上次在中間來源模式下修改的傳遞的狀態。

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## 參數

**startDate**&#x200B;擷取從這個日期以來的修改（在中間來源伺服器上）。

**maxCount**&#x200B;要擷取的傳遞數上限，前提是這些傳遞沒有在同一秒內更新。

發行伺服器的&#x200B;**emitterDate**&#x200B;參考日期。 用於調整傳遞日期。

## 傳回值

**結果**&#x200B;輸出檔案，傳遞清單已更新。

下一次通話的&#x200B;**nextDate**&#x200B;開始日期。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
