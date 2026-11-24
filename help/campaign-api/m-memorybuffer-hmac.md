---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

計算緩衝區的MD5、SHA-1或SHA-256雜湊。

```text
hmac (key [, algo ])
```

## 參數

**key** Key，以緩衝區的形式。

要使用的&#x200B;**演演算法**&#x200B;雜湊型別。 可能的值包括「MD5」、「SHA1」或「SHA256」。 這些值不區分大小寫，因此可輸入小寫或大寫的值。 如果未指定引數，預設會選取「SHA1」值。

## 傳回值

緩衝區的雜湊MD5、SHA-1或SHA-256 （根據選擇的雜湊型別）。

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
