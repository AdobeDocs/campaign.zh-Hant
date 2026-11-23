---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

執行SQL查詢並以XML檔案的形式傳回結果。

```text
sqlSelect (format, query [, dataSource ])
```

## 參數

**format**&#x200B;以逗號分隔的字串，將預期的資料格式描述為名稱:type\[:length\]型別清單docName， \[fieldXPath:type，\]\*

**查詢** SQL查詢。

**資料來源**&#x200B;資料來源。

## 傳回值

XML物件，包含查詢結果每一行的元素清單。

## 備註

範例：

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
