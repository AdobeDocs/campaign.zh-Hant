---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# 上傳

從本機檔案下載檔案至FTP伺服器。

```text
upload (URL)
```

## 參數

**URL**&#x200B;伺服器網址。

## 傳回值

無。

## 備註

URL必須以「ftp:&#39;」開頭，範例：

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
```

## 功能

**類別的方法：** [FTP](c-ftp.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
