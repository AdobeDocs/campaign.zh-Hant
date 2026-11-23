---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# 匯出

產生和匯出報告

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## 參數

**reportName**&#x200B;報告的內部名稱

**內容**&#x200B;執行內容。

**exportFormat**&#x200B;可能的值為：XLS、OOXML\_SS、ODF\_SS、PDF

XLS會產生Excel 94-2003檔案\
 OOXML\_SS會產生Excel 2007檔案\
 ODF\_SS會產生Open檔案

**檔案名稱**&#x200B;輸出檔案名稱

**isAdHoc**&#x200B;指定匯出是否涉及臨時報告

## 傳回值

無。

## 功能

**結構描述：** [xtk:report](s-xtk-report.md)

**靜態：**

是
