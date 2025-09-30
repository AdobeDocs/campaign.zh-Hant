---
product: campaign
title: 技術檔案 — Adobe Campaign中的非對稱加密與解密
description: 技術說明 — Adobe Campaign中的非對稱加密與解密
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# 技術檔案：Adobe Campaign中的非對稱加密與解密 {#asymetric-encryption}

公開金鑰密碼編譯或非對稱密碼編譯是使用相關金鑰組的密碼編譯系統欄位。 每個金鑰組都包含&#x200B;**公開金鑰**&#x200B;和對應的&#x200B;**私密金鑰**。

* **公開金鑰**&#x200B;是公開共用的，用來加密資料。

* **私密金鑰**&#x200B;是保密的，用來解密資料。

此方法可確保即使某人擁有公開金鑰，若沒有私密金鑰，他們也無法解密訊息。 它提供重要的安全性功能，例如機密性、驗證和完整性。

自Adobe Campaign v8.8.3開始，已新增兩個新的Javascript函式以進行加密和解密：

* 使用公開金鑰加密： `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* 使用私密金鑰解密： `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


範例：

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**其他資源**

* [開始使用 [!DNL Campaign] API](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=zh-Hant){target="_blank"}
