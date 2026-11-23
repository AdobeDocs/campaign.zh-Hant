---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# 載入

> 警告：
>
> 透過檔案API的存取權僅限於&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的暫存資料夾。

從XML檔案建立新檔案。

```text
load (filename [, allowEmpty ])
```

## 參數

**檔案名稱**&#x200B;要載入的檔案名稱。

**allowEmpty**&#x200B;如果為True，則檔案為空白時不會引發例外狀況（預設值=false）。

## 傳回值

無。

## 備註

如果無法載入檔案或檔案內容不是有效的XML檔案，則會引發例外狀況。 此函式適用於DOMDocument類別。 範例：

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## 功能

**類別的方法：** [DOMDocument](c-domdocument.md)

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
