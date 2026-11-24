---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

在中間來源模式下提交傳遞。

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## 參數

代表傳遞的&#x200B;**傳遞**&#x200B;檔案。

**routingMatch**&#x200B;已不再使用

**folderName**&#x200B;完整資料夾名稱（在寄件者資料庫中）。

## 傳回值

接收者資料庫中傳遞的&#x200B;**remoteId**&#x200B;識別碼。

**remoteMatchId**&#x200B;已不再使用

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
