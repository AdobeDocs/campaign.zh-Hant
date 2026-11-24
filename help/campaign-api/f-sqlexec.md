---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# sqlExec

執行SQL指令碼。

```text
sqlExec (query [, value1, ... ])
```

## 參數

**查詢** SQL查詢。

**value1， ...** SQL查詢的變數。

## 傳回值

更新或插入的記錄數（如果是UPDATE ou INSERT SQL命令）。

## 備註

變數會取代命令中的引數。 變數型別必須與命令中宣告的引數一致。 這些變數可在&#39;select&#39;或&#39;update&#39;型別宣告中使用。 我們有以下型別：

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
* $(dur)時間跨度en毫秒(ms)

下列替代引數（僅對「更新」有效）會自動取代為值，不需要連結變數。

* $(id)產生識別碼
* $(id:NmsTrackingLogId)使用特定順序產生識別碼
* $(curdate)目前日期和小時

運運算元必須有&#39;sql&#39;許可權才能使用此函式，否則會引發例外狀況。 範例：

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
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
