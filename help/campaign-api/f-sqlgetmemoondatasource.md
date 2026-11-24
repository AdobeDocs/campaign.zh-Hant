---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 11%
---
# sqlGetMemoOnDataSource

傳回資料來源上的SQL查詢所產生的備忘錄欄位。

```text
sqlGetMemoOnDataSource (query, dataSource [, value1, ... ])
```

## 參數

**查詢** SQL查詢。

**資料來源**&#x200B;資料來源。

**value1， ...** SQL查詢的變數。

## 傳回值

符合查詢的備忘錄欄位。

## 備註

已在[sqlExecOnDataSource(query， dataSource， value1， ...)](f-sqlexecondatasource.md)中定義「資料來源」引數 函式設定為此函式之引數的選用變數定義於[sqlGetString(query， value1， ...)](f-sqlgetstring.md)

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
