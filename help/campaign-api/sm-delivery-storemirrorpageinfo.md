---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

新增資訊以針對一組傳遞部分產生鏡像頁面。

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## 參數

**deliveryId**&#x200B;傳遞識別碼

**partsCount**&#x200B;部分數目

**firstPartId**&#x200B;第一部分識別碼

**lastPartId**&#x200B;最後部分識別碼

## 傳回值

**fatalError**&#x200B;傳回錯誤碼，導致呼叫者無法執行重試。 否則，錯誤可能是暫時的。

與「fatalError」錯誤碼相關的&#x200B;**fatalErrorMsg**&#x200B;錯誤訊息。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
