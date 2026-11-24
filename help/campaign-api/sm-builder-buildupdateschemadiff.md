---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

產生描述實際資料庫結構和其邏輯描述之間差異的文件。

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## 參數

**引數**&#x200B;更新引數

**useNamingConventions**&#x200B;使用SQL命名慣例來計算新欄位的路徑。

## 傳回值

**sqlSchemaDiff**&#x200B;產生的結構描述

## 功能

**結構描述：** [xtk:builder](s-xtk-builder.md)

**靜態：**

是
