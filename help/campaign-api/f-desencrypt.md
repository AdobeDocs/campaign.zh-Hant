---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%
---
# DESencry

> 警告：
>
> 此函式已過時，請使用[cryptString()](f-cryptstring.md)。

使用DES演演算法將字串數位化。

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## 參數

**value**&#x200B;要數位化的字串

**key**&#x200B;以十六進位表示的金鑰。 金鑰長度必須是64位元，或16個十六進位字元。 依預設，會使用資料庫的識別碼。

**加密模式**&#x200B;區塊編碼方法。 一個字元字串。 即「CBC」、「ECB」或「EDE」。 預設為「CBC」。

**初始化向量**&#x200B;以十六進位字串形式的初始化向量。 8個八位元，即16個字元。 預設為空字串。

**內距**&#x200B;內距型別。 字元字串，即「PKCS5PADDING」或「PKCS7PADDING」。 預設為空字串，這表示要加密的字串結尾會新增&#39;\\0&#39;。

## 傳回值

以Base 64表示的數位字串。

## 備註

* DES金鑰有56個有用的位元和8個用於同位檢查的位元；這些位元會被忽略。
* 由DES演演算法有效加密的值將會是8位元字串的Windows-1252表示法，以ASCII 0字元結束，並以二進位零填入64位元的倍數。
* 數位化值有多重長度的64位元值。

## 功能

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
