---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

傳回在伺服器上找到且由此傳輸使用的檔案清單

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## 參數

**jobId**&#x200B;傳輸識別碼

## 傳回值

**filesToDownload**&#x200B;傳回可以元素形式下載的檔案清單\[dataTransfer/properties/filesToDownload\]

**filesNotToDownload**&#x200B;傳回無法以元素\[dataTransfer/properties/filesNotToDownload\]下載的檔案清單

## 功能

**結構描述：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**靜態：**

是
