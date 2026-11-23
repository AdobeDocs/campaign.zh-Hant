---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> 警告：
>
> 透過檔案API的存取權僅限於&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的暫存資料夾。

此函式已過時，請使用[DOMDocument.load()](m-domdocument-load.md)。 以XML檔案物件的形式載入檔案

```text
loadXmlFile (filename [, noErr ])
```

## 參數

**filename**&#x200B;要載入的檔案全名。

**noErr**&#x200B;如果為True，則檔案為空白時不會發生錯誤（預設=false）。

## 傳回值

xml檔案。

## 備註

由於偵測到BOM和XML序號，此函式支援偵測檔案的程式碼頁。

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
