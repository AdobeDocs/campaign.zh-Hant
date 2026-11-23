---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

在資料來源上執行SQL指令碼。

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## 參數

**查詢** SQL查詢。

**資料來源**&#x200B;資料來源。

**value1， ...** SQL查詢的變數。

## 傳回值

在UPDATE或INSERT SQL命令中更新或插入的記錄數。

## 備註

資料來源的授權值可以是：

* 「」或「預設」指向Adobe Campaign資料庫

* 「nms:extAccount:InternalName」指向Adobe Campaign外部帳戶(FDA)中定義的資料來源

* 「名稱」（資料來源的名稱）指向執行個體組態檔(config-instance.xml)中定義的資料來源，格式如下：

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

範例：

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

設定為此函式之引數的選用變數定義於[sqlGetString(query， value1， ...)](f-sqlgetstring.md)

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
