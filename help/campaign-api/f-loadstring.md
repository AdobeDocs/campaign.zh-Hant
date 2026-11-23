---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 14%
---
# loadString

這個命令已被取代，請使用⌐[loadFile()](f-loadfile.md)。 傳回文字檔的內容

```text
loadString (filename [, codePage ])
```

## 參數

**filename**&#x200B;要載入的檔案全名。

**codePage**&#x200B;此選用引數可讓您指定字元編碼。 範例：

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 傳回值

與文字檔內容對應的字元字串。

## 備註

如果未指定字元編碼，則會使用伺服器預設值。

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
