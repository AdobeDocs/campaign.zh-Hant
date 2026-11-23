---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

從封存中擷取檔案。

```text
getEntry (filename)
```

## 參數

**檔案名稱**&#x200B;封存中的檔案名稱。

## 傳回值

包含檔案內容的⌐ [MemoryBuffer](c-memorybuffer.md)。

## 備註

您必須先使用⌐[open()](m-zipfile-open.md)方法開啟封存，才能使用此方法。 否則，會引發例外狀況。 範例：下列範例會從封存中擷取dir/content.xml檔案，並將其儲存至/tmp/資料夾。

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
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
