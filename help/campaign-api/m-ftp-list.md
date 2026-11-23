---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# 清單

傳回伺服器上指定目錄中的檔案清單。

```text
list (URL, pattern [, max ])
```

## 參數

FTP伺服器的&#x200B;**URL**&#x200B;位址做為URL。

**pattern**&#x200B;要擷取之檔案清單的檔案和遮罩。

**最多**&#x200B;個要傳回的檔案數上限。 如果缺少此引數，方法會傳回檔案的完整清單。

## 傳回值

包含與指定路徑和遮罩相對應的檔案名稱的表格。

## 備註

如果FTP命令失敗，則會引發例外狀況。 範例：

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
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
