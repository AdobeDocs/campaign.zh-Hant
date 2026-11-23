---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# 檔案存在

檢查檔案是否已存在於伺服器上 (作為檔案或在資源表中)。

```text
XML exist = FilesExist ( XML files )
```

## 參數

**檔案**&#x200B;檔案清單(@name)及其MD5金鑰(@md5)和布林值，指出它是否可為資源(@checkResource)。

## 傳回值

**存在**&#x200B;結果清單（@md5和@exists）

## 功能

**結構描述：** [xtk:job](s-xtk-job.md)

**靜態：**

是
