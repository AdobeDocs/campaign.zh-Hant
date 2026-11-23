---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# 下載

將檔案從伺服器下載至本機檔案或記憶體。

```text
download (URL [, append ])
```

## 參數

要下載的檔案的&#x200B;**URL** URL。

**附加**&#x200B;依預設，如果下載的檔案已存在於本機磁碟上，則會被收到的新檔案覆寫。 如果啟動布林值，Adobe Campaign會將下載的內容與現有內容一起以相同名稱寫入檔案中。

## 傳回值

無。

## 備註

若要復原本機檔案中的檔案，請使用setFile方法啟動。 範例：

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
