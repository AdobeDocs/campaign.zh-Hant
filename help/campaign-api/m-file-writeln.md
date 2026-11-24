---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# 寫入

將文字行寫入檔案。

```text
writeln (line)
```

## 參數

**line**&#x200B;要寫入的文字行。

## 傳回值

無。

## 備註

範例：

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
