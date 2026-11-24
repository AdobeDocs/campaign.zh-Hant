---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

複製伺服器上的檔案後，如有必要，在上傳資料夾中傳回檔案名稱。

```text
String serverFileName = fileRes.GetServerFileName ()
```

## 參數

無。

## 傳回值

**serverFileName**&#x200B;伺服器上檔案的完整名稱（如果找不到檔案，則為空白）。

## 範例

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## 功能

**結構描述：** [xtk:fileRes](s-xtk-fileres.md)

**靜態：**

否

**常數：**

否

僅&#x200B;**機碼：**

否
