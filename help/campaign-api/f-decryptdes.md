---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 8%
---
# decryptDES

> 警告：
>
> 此函式已過時，請使用[decryptString()](f-decryptstring.md)。

使用DES演演算法將字串解密。

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## 參數

**key**&#x200B;以十六進位表示的金鑰。 金鑰必須是64位元長度或16個十六進位字元。

**value**&#x200B;要加密的資料以基底64表示。

**加密模式**&#x200B;編碼區塊的方法。 字元字串。 即「CBC」、「ECB」或「EDE」。 預設為「CBC」。

**初始化向量**&#x200B;以十六進位字串形式的初始化向量。 8個八位元，即16個字元。 預設為空字串。

## 傳回值

純文字中的字元字串。

## 備註

* DES金鑰有56個有用的位元和8個用於同位檢查的位元；這些位元會被忽略。
* 在Windows-1252程式碼頁中，資料會以8位元字串形式解密。
* 加密資料的長度必須是64位元的倍數。

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
