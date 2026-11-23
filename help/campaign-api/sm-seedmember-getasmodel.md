---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## 參數

**refIdName**&#x200B;包含要關聯的實體識別碼（例如「delivery-id」）的屬性

要關聯的實體的&#x200B;**refIdValue**&#x200B;識別碼（「refIdName」的值）

**selection**&#x200B;包含所選範本識別碼的元素

包含現有種子地址的&#x200B;**parentIn**&#x200B;元素

## 傳回值

**parentOut**&#x200B;傳回新增了新範本的元素

## 功能

**結構描述：** [nms:seedMember](s-nms-seedmember.md)

**靜態：**

是
