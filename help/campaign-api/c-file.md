---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# 檔案（類別）

檔案類別

> 警告：
>
> 透過檔案API的存取權僅限於&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的暫存資料夾。

以下是如何使用類別來依序讀取及處理檔案所有行的範例。

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## 方法

| 方法 | 說明 |
| --- | --- |
| [檔案](m-file-file.md) | 建立與檔案關聯的新物件。 |
| [關閉](m-file-close.md) | 關閉檔案。 |
| [複製到](m-file-copyto.md) | 複製檔案。 |
| [處置](m-file-dispose.md) | 釋放物件使用的資源。 |
| [排清](m-file-flush.md) | 強制寫入磁碟 |
| [清單](m-file-list.md) | 列出目錄的內容。 |
| [mkdir](m-file-mkdir.md) | 以目前[檔案](c-file.md)物件的路徑建立目錄。 |
| [開啟](m-file-open.md) | 以讀取或寫入模式開啟檔案。 |
| [移除](m-file-remove.md) | 刪除檔案。 |
| [重新命名為](m-file-renameto.md) | 重新命名檔案。 |
| [readln](m-file-readln.md) | 讀取文字檔的一行。 |
| [rmdir](m-file-rmdir.md) | 刪除目錄（非重疊顯示）。 |
| [writeln](m-file-writeln.md) | 將文字行寫入檔案。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [canRead](p-file-canread.md) | 如果檔案可以讀取，則傳回true。 |
| [canWrite](p-file-canwrite.md) | 如果檔案可以修改，則傳回true。 |
| [存在](p-file-exists.md) | 如果存在使用此名稱的檔案或資料夾，則傳回true。 |
| [完整名稱](p-file-fullname.md) | 以絕對值傳回檔案名稱。 |
| [isDirectory](p-file-isdirectory.md) | 如果檔案是目錄，則傳回true。 |
| [isFile](p-file-isfile.md) | 如果檔案存在且是檔案，則傳回true。 |
| [isOpen](p-file-isopen.md) | 如果檔案已開啟，則傳回true。 |
| [lastModified](p-file-lastmodified.md) | 以Date物件的形式傳回上次修改日期。 |
| [名稱](p-file-name.md) | 傳回副檔名為但沒有路徑的檔案名稱。 |
| [路徑](p-file-path.md) | 傳回以分隔符號結尾的檔案完整路徑。 |
| [大小](p-file-size.md) | 傳回檔案大小（位元組）。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
