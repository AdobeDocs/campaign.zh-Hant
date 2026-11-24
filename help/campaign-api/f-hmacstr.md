---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# hmacStr

計算字元字串的MD5、SHA-1或SHA-256雜湊。 字串在計算之前會自動以UTF-8編碼。

```text
hmacStr (string [, key ] [, algo ])
```

## 參數

**字串**&#x200B;要計算雜湊的字串。

**key** Key，字元字串形式。 它會自動轉換為UTF-8。 如果金鑰遺失，則伺服器會使用相依於此執行個體的金鑰，且僅在此執行個體上有效。

**演演算法**&#x200B;要使用的雜湊型別。 可能的值包括「MD5」、「SHA1」或「SHA256」。 忽略大小寫，因此可輸入小寫或大寫的值。 若未指定引數，預設會選取「SHA1」值。

## 傳回值

作為引數傳遞的字串的MD5、SHA-1或SHA-256雜湊（視選取的雜湊型別而定）。

## 備註

對於MD5和SHA-1型別，轉換為UTF-8後，金鑰最多可以是64個字元（512位元）。 對於SHA-256型別，轉換為UTF-8後，金鑰最多可以是32個字元（256位元）。

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
