---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

轉換以base 64編碼的緩衝區或字元字串的一部分。

```text
toBase64 ( [start ] [, length ])
```

## 參數

**start**&#x200B;在緩衝區開頭要略過的位元組數。 第一個位元組對應至值0 （預設值）。

**length**&#x200B;要轉換的位元組數。 依預設，會考慮剩餘的所有位元組。

## 傳回值

以base 64編碼的緩衝區內容。

## 功能

**類別的方法：** [MemoryBuffer](c-memorybuffer.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
