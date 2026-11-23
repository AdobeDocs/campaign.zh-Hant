---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> 警告：
>
> 此函式已完全淘汰。 如需詳細資訊，請參閱此[頁面](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions)。

使用例項的鍵或任何其他鍵加密字元字串。

```text
cryptString (str [, key ] [, useSalt ])
```

## 參數

**str**&#x200B;要加密的字元字串。

**key** AES加密金鑰是以base 64編碼：如果金鑰長度為32，則為256位元；如果金鑰長度為24，則為192位元；如果金鑰長度為16或未指定金鑰，則為128位元。

**useSalt**&#x200B;使用資料的Salt進行加密。 預設為True。

## 傳回值

傳回加密的字元字串

## 備註

加密會根據下列方法進行：

* unicode字元字串會轉換為UTF-8字串。
* 在結尾新增一個核取字元。
* 此字串會使用Cipher Block Chaining (CBC)模式中的AES演演算法加密，且初始化向量為Null。 如果未提供索引鍵作為引數，則會使用例項索引鍵。
* 然後加密區塊會轉換為基底64。

使用[decryptString](f-decryptstring.md)函式執行解密。

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
