---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

傳回伺服器上與傳遞相關聯的檔案清單。

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## 參數

**deliveryId**&#x200B;傳遞識別碼

## 傳回值

**filesToDownload**&#x200B;傳回可以元素形式下載的檔案清單\[properties/filesToDownload\]

**filesNotToDownload**&#x200B;傳回無法當作元素\[properties/filesNotToDownload\]下載的檔案清單

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
