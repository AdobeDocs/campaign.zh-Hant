---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

完成中間來源模式下的傳遞分析。

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## 參數

**deliveryId**&#x200B;傳遞識別碼

**errorCode**&#x200B;行銷資料庫分析傳回的錯誤碼（此方法不會使用方法層級的錯誤碼）

**屬性**&#x200B;要更新的傳遞屬性

**重試**&#x200B;指定這是否為方法呼叫的重試。

## 傳回值

**fatalError**&#x200B;傳回錯誤碼，導致呼叫者無法執行重試。 否則，錯誤可能是暫時的。

與「fatalError」錯誤碼相關的&#x200B;**fatalErrorMsg**&#x200B;錯誤訊息。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
