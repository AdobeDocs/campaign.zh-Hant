---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

產生暫存檔案名稱。

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## 參數

暫存檔的&#x200B;**目錄**&#x200B;目錄。 如果為空，則使用系統定義的暫存目錄。

**首碼**&#x200B;首碼最多4個字元。 如果留空，則使用tmp前置詞。

**副檔名**&#x200B;副檔名。

## 傳回值

檔案的完整名稱。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
