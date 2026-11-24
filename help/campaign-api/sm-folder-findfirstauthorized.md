---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

為目前使用者尋找滿足 folderFilter 條件的第一個合格資料夾。

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## 參數

**資料夾篩選器**&#x200B;資料夾篩選器

**writeAccess**&#x200B;傳回的資料夾必須是可寫入的

**orgUnit**&#x200B;傳回的資料夾必須與指定的組織實體相容

## 傳回值

**folderEntity**&#x200B;傳回關聯的資料夾實體（null表示找不到資料夾）

## 功能

**結構描述：** [xtk:folder](s-xtk-folder.md)

**靜態：**

是
