---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

計算查詢第一行的輸出檔案欄預覽

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## 參數

已定義計算欄位的&#x200B;**dataTransferStep**&#x200B;傳輸步驟。

**lineCount**&#x200B;要傳回的行數

**countMode**&#x200B;行計數模式

**calcFieldName**&#x200B;觀察到的計算欄位名稱。 如果為空，則為輸出檔案的全域預覽。

## 傳回值

**resultColumns**&#x200B;傳回匯出檔案資料行的值(line/col/val、line/col/errors)。

**resultXML**&#x200B;傳回查詢的輸出XML檔案。

**resultSQLRequest**&#x200B;傳回執行的SQL查詢。

## 功能

**結構描述：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**靜態：**

是
