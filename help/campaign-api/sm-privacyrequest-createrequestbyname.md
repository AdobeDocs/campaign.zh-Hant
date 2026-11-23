---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

使用名稱空間內部名稱來建立新的隱私權請求

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## 參數

**namespaceName**&#x200B;名稱空間內部名稱

**reconciliationValue**&#x200B;調解值

**型別**&#x200B;調解值

刪除資料前&#x200B;**confirmDeletePending**&#x200B;要求確認

**規則**&#x200B;規則型別具有下列值：

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## 傳回值

新建立請求的&#x200B;**id**&#x200B;識別碼

## 功能

**結構描述：** [nms:privacyRequest](s-nms-privacyrequest.md)

**靜態：**

是
