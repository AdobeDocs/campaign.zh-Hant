---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 5%
---
# sqlGetDouble

傳回從SQL查詢產生的數字。

```text
sqlGetDouble (query [, value1, ... ])
```

## 參數

**查詢** SQL查詢。

**value1， ...** SQL查詢的變數。

## 傳回值

符合查詢的數值。

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
* $(dur)時間間隔（毫秒）

下列替代引數（僅對「更新」有效）會自動取代為值，不需要連結變數。

* $(id)產生識別碼
* $(id:NmsTrackingLogId)使用特定順序產生識別碼
* $(curdate)目前的日期和時間

使用變數不會改變Adobe Campaign效能。 SQL查詢必須選取單一行和單一數值型別欄位。 運運算元必須有&#39;sql&#39;許可權才能使用此函式，否則會引發例外狀況。 範例：

```javascript
      var number = sqlGetDouble('select price from priceTable where sTaxes =$(d) order by tsCreated DESC LIMIT 1', taxes)
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
