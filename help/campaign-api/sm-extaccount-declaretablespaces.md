---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

在 Adobe Campaign 資料庫中宣告選項，這些選項是使用可透過外部帳戶存取的遠端資料庫中的特定表格空間所必需。

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## 參數

**extAccountId**&#x200B;外部帳戶的內部名稱或主索引鍵

**tableSpace**&#x200B;用於遠端工作表的表格空間名稱

**tableSpaceIndex**&#x200B;用於索引的表格空間名稱

## 傳回值

無。

## 功能

**結構描述：** [nms:extAccount](s-nms-extaccount.md)

**靜態：**

是
