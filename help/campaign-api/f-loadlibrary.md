---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

載入JavaScript程式庫。

```text
loadLibrary (filename [, boolean ])
```

## 參數

**檔案名稱**&#x200B;要載入的JavaScript程式庫名稱。

**布林值**&#x200B;啟用或停用載入快取。 預設為true。

> 注意：當引數設為false時，您需要在loadLibrary呼叫被驗證為運運算元之前使用logon()函式。

## 傳回值

無。

## 備註

快取預設為啟用。 如果快取已停用，則會針對每次呼叫查詢資料庫。 此查詢可讓您載入最新版本的程式庫。 範例： loadLibrary(&#39;xtk:shared/nl.js&#39;)

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
