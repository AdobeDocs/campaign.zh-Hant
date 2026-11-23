---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 8%
---
# saveXmlString

這個命令已被取代，請使用[saveXmlFile()](f-savexmlfile.md)。 將與XML檔案對應的字元字串儲存至檔案。

```text
saveXmlString (text, filename [, codePage ])
```

## 參數

**文字**&#x200B;要儲存的字元字串形式的XML檔案。

**檔案名稱**&#x200B;要儲存的檔案全名。

**codePage**&#x200B;此選用引數可讓您指定字元編碼。 範例：

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 傳回值

無。

## 備註

如有必要，此函式會在檔案中插入XML序號，並指定檔案編碼。 如果未指定字元編碼，則會使用伺服器預設值。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
