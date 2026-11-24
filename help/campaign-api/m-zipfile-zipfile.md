---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# Zip檔案

> 警告：
>
> 透過檔案API的存取權僅限於&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的暫存資料夾。

建立與檔案關聯的新Zip物件。

```text
ZipFile (filename)
```

## 參數

**filename**&#x200B;要載入或建立的封存名稱。

## 傳回值

無。

## 備註

範例：

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## 功能

**類別的方法：** [ZipFile](c-zipfile.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
