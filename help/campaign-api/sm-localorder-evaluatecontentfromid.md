---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 4%
---
# EvaluateContentFromId

評估連結至訂單的傳遞內容。 這項評估將在使用操作員許可權訂購時以及建立本機行銷活動之前執行。

```text
XML result = EvaluateContentFromId ( Number orderId, Number deliveryId, String contentType, Number seedMemberId )
```

## 參數

**orderId**&#x200B;訂單識別碼。

要評估的傳遞&#x200B;**deliveryId**&#x200B;識別碼。

**contentType**&#x200B;要傳回的內容型別（電子郵件為html或文字；其他管道為空字串）。

用於內容個人化的&#x200B;**seedMemberId**&#x200B;種子位址識別碼。

## 傳回值

**結果**&#x200B;評估的內容。

## 功能

**結構描述：** [nms:localOrder](s-nms-localorder.md)

**靜態：**

是
