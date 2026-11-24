---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

宣告實體不再有衝突。

```text
SetResolved ( String conflictId )
```

## 參數

**conflictId**&#x200B;衝突識別碼。

## 傳回值

無。

## 備註

解決所有衝突後，此方法可讓您將圖元放回其正常位置。 在叫用此方法之前，必須解決所有衝突的屬性和元素。

## 功能

**結構描述：** [xtk:conflict](s-xtk-conflict.md)

**靜態：**

是
