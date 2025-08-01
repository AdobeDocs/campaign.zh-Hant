---
title: 使用API建立設定檔
description: 進一步瞭解如何使用API建立設定檔。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---

# 使用API建立設定檔 {#creating-profiles-api}

在設定檔資源上使用&#x200B;**POST**&#x200B;要求執行建立設定檔。

>[!CAUTION]
>
>如果您想要將<b>orgUnit</b>與建立的設定檔建立關聯，您必須使用這個欄位擴充設定檔資源，並在擴充功能發佈之後，在<b>ProfileAndServicesExt</b>端點上執行POST要求。
>
>如需設定檔資源擴充功能的詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign檔案</a>。

<br/>

***範例要求***

使用電子郵件「john.doe@mail.com」建立設定檔的範例POST請求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它會傳回新建立的設定檔，並帶有「john.doe@mail.com」電子郵件地址。

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
