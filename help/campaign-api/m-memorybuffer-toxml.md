---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

傳回從[MemoryBuffer](c-memorybuffer.md)的內容取得的XML JavaScript物件。 此函式已過時，請使用[toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## 參數

**codePage**&#x200B;為所用字元頁編碼的整數。 預設為MemoryBuffer.CODEPAGE\_UTF8。

## 傳回值

以XML物件形式表示的印章內容。

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
