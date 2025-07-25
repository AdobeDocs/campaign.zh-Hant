---
title: 中繼資料機制
description: 進一步瞭解中繼資料機制。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# 中繼資料機制 {#metadata-mechanism}

您可以在GET要求中使用&#x200B;**resourceType**&#x200B;擷取資源中繼資料：

`GET /profileAndServices/resourceType/<resourceName>`

回應會從資源傳回主要中繼資料（所有其他欄位均為描述性或內部）：

* **Content**&#x200B;節點會傳回資源的欄位。 對於&#x200B;**content**&#x200B;節點中的每個欄位，我們可以找到下列欄位：

   * &quot;apiName&quot;： API中使用的屬性名稱。
   * &quot;type&quot;：這是高階型別定義（字串、數字、連結、集合、列舉……）。
   * &quot;dataPolicy&quot;：欄位的值必須符合指定的原則規則。 例如，如果dataPolicy規則設為「電子郵件」，該值必須是有效的電子郵件。 在PATCH或POST期間，dataPolicy可以檢查值或修改值以進行轉換（例如smartCase）。
   * &quot;category&quot;：提供查詢編輯器中的欄位類別。
   * &quot;resType&quot;：這是技術型別。

     如果「type」是以值「link」或「collection」完成，則resTarget值是連結所定位的資源名稱。
如果「type」以「enumeration」值完成，則會新增「values」欄位，且每個列舉值都會在&#x200B;**values**&#x200B;節點中詳細說明。

* **篩選器**&#x200B;節點會傳回URL以擷取關聯的篩選器。 如需篩選的詳細資訊，請參閱[本區段](sorting.md#filtering)。

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***範例要求***

對資源執行GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回設定檔資源的完整說明。

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
