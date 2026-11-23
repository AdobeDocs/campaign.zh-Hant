---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

使用指令碼中儲存的樣本行來測試計算欄位。

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## 參數

已定義計算欄位的&#x200B;**dataTransferStep**&#x200B;資料傳輸步驟

**calcFieldName**&#x200B;要測試的計算欄位

## 傳回值

**calcFieldValues**&#x200B;傳回每個樣本行的值清單(calcFieldValues/line)和欄位名稱(calcFieldValues/@name)

## 功能

**結構描述：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**靜態：**

是
