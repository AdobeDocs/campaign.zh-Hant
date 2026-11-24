---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

產生用於建立或更新 autoPk 結構描述序列的 SQL 指令碼

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## 參數

**schemaId**&#x200B;結構描述識別碼

**新序列**&#x200B;新序列

**oldSequence**&#x200B;舊序列

## 傳回值

**sqlDDL** SQL指令碼

## 功能

**結構描述：** [xtk:builder](s-xtk-builder.md)

**靜態：**

是
