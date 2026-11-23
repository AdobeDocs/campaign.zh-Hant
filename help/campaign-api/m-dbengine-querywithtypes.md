---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithType

執行具有資料行型別規格的SELECT型別SQL查詢。

```text
queryWithTypes (command, types [, value1, ... ])
```

## 參數

**命令** SQL命令。

**型別**&#x200B;包含資料行型別的資料表。

**value1， ...**&#x200B;命令變數。

## 傳回值

可讓您反複查詢結果的游標。

## 備註

警告：與「功能」區段中的說明相反，WebApp中不提供queryWithTypes函式。 此函式與[query](m-dbengine-query.md)相同，且有新增的資料行型別。 在大多數情況下，不會使用欄型別，因為它可以自動推斷。 這就是應該偏好[查詢](m-dbengine-query.md)的原因。 但在某些情況下，尤其是使用Oracle和日期型別欄時，可能必須明確型別。 欄型別是下列清單中的字元字串：

* 字串
* 日期時間
* 日期
* 時間
* 時間範圍
* 雙精度浮點數
* 浮點數
* 布林值
* 位元組
* 短整數
* 長整數
* 64 位元整數
* 備忘錄
* blob
* 連結
* 分類箱

範例：

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

運運算元必須有&#39;sql&#39;許可權才能使用此函式，否則會引發例外狀況。

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
