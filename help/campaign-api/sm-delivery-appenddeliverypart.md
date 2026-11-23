---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

將部分新增到正在準備的傳遞中。

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## 參數

代表傳遞部分（或傳遞部分集合）的&#x200B;**deliveryPart**&#x200B;檔案。

**重試**&#x200B;指定這是否為提交此傳遞部分的新嘗試。

## 傳回值

資料庫中的&#x200B;**deliveryPartId**&#x200B;傳遞部分識別碼（當它不是集合時）。

**fatalError**&#x200B;傳回錯誤碼，導致呼叫者無法執行重試。 否則，錯誤可能是暫時的。

與「fatalError」錯誤碼相關的&#x200B;**fatalErrorMsg**&#x200B;錯誤訊息。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
