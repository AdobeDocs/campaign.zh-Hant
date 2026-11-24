---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# encryptDES

> 警告：
>
> 此函式已過時，請使用[cryptString()](f-cryptstring.md)。

使用DES演演算法加密字串。

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## 參數

**key**&#x200B;以十六進位表示的金鑰。 金鑰必須是64位元長，即16個十六進位字元。

**value**&#x200B;要加密的字串

**加密模式**&#x200B;編碼區塊的方法。 字元字串。 即「CBC」、「ECB」或「EDE」。 預設為「CBC」。

**初始化向量**&#x200B;以十六進位字串形式的初始化向量。 8個八位元，即16個字元。 預設為空字串。

**內距**&#x200B;內距的型別。 字元字串，即「PKCS5PADDING」或「PKCS7PADDING」。 預設為空字串，這表示在要加密的字串結尾新增&#39;\\0&#39;。

## 傳回值

以Base 64表示的加密字串。

## 備註

* DES金鑰有56個有用的位元和8個用於同位檢查的位元；這些位元會被忽略。
* 由DES演演算法有效加密的值將會是8位元字串的Windows-1252表示法，以ASCII 0字元結束，並以二進位零填入64位元的倍數。
* 加密值將為64位元字的倍數。

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
