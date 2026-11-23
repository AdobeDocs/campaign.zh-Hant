---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# open

以讀取或寫入模式開啟檔案。

```text
open ( [mode ] [, codepage ])
```

## 參數

**模式**&#x200B;檔案開啟模式。 模式可以是下列其中一個值：

* &quot;r&quot; — 以唯讀模式開啟檔案。 此模式為預設模式。
* 「w」 — 以寫入模式開啟檔案。
* &quot;a&quot; — 以「附加」模式開啟檔案，寫入檔案的資料會附加在末尾。

**codepage**&#x200B;檔案編碼。 編碼可以是下列其中一個值：

* File.CODEPAGE\_CURRENT — 這是預設的程式碼頁。
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_OEMLATIN1
* File.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## 傳回值

無。

## 備註

如果無法開啟檔案，則會引發例外狀況。

## 功能

**類別的方法：** [檔案](c-file.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
