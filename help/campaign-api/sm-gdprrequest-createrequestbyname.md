---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

使用命名空間內部名稱來建立新的 GDPR 請求

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## 參數

**namespaceName**&#x200B;名稱空間內部名稱

**reconciliationValue**&#x200B;調解值

**型別**&#x200B;調解值

刪除資料前&#x200B;**confirmDeletePending**&#x200B;要求確認

## 傳回值

新建立請求的&#x200B;**id**&#x200B;識別碼

## 功能

**結構描述：** [nms:gdprRequest](s-nms-gdprrequest.md)

**靜態：**

是
