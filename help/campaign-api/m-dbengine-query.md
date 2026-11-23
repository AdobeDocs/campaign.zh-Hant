---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# 查詢

執行SELECT型別SQL查詢。

```text
query (command [, value1, ... ])
```

## 參數

**命令** SQL命令。

**value1， ...**&#x200B;命令的變數。

## 傳回值

可讓您反複查詢結果的游標。

## 備註

警告：與「功能」區段中的說明相反，查詢函式在WebApp中無法使用。 變數會取代命令的引數。 變數型別必須符合命令中宣告的引數。 可使用下列型別：

* $(sz)字串
* $(m)備忘錄
* $(l)長
* $(s)短
* $(b)位元組
* $(d)雙
* $(f)浮點數
* $(ts)時間戳記
* $(dt)日期
* $(tm)時間
* $(dur) timespan

下列替代引數會自動取代為值，不需要連結變數。

* $(id)產生識別碼
* $(id:NmsTrackingLogId)依據特定順序產生識別碼
* $(curdate)目前的日期和時間

游標上的反複專案會透過「每個」進行，並傳回每個復原行的表格。 表格的每個元素都與查詢的欄位相符，元素的型別取決於欄位型別。 範例：

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

在此範例中，row\[0\]是與iOperatorId重合的數字，row\[1\]是與sName重合的字元字串，row\[2\]是與tsLastModified重合的日期。 運運算元需要&#39;sql&#39;許可權才能使用此函式，否則會發生例外狀況。

## 功能

**類別的方法：** [DBEngine](c-dbengine.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
