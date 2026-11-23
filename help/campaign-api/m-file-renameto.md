---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 24%
---
# renameTo

重新命名檔案。

```text
renameTo (fileName)
```

## 參數

**檔案名稱**&#x200B;新檔案名稱（必須是完整路徑）。

## 傳回值

無。

## 備註

範例：

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
```

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
