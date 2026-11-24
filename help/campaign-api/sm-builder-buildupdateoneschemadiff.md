---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

產生描述實體資料庫中的表格與此表格的邏輯描述之間差異的文件。

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## 參數

**schemaId**&#x200B;結構描述識別碼

**useNamingConventions**&#x200B;使用SQL命名慣例來計算新欄位的路徑。

## 傳回值

**sqlSchemaDiff**&#x200B;產生的結構描述

## 功能

**結構描述：** [xtk:builder](s-xtk-builder.md)

**靜態：**

是
