---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# 執行

執行SQL命令。

```text
execute (command [, value1, ... ])
```

## 參數

**命令** SQL命令。

**value1， ...**&#x200B;命令的變數。

## 傳回值

如果適用於執行的命令，則更新或插入的記錄數，否則為零。

## 備註

變數可用來取代指令的引數。 變數型別必須符合命令中宣告的型別。 型別如下：

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

下列替代引數會自動取代為值，不需要關聯的變數。

* $(id)產生識別碼
* $(id:NmsTrackingLogId)依據特定順序產生識別碼
* $(curdate)目前的日期和時間

運運算元需要&#39;sql&#39;許可權才能使用此函式，否則會發生例外狀況。

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
