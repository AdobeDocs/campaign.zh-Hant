---
title: 篩選
description: 瞭解如何執行篩選作業。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: cdb050b7-d327-42f7-b534-d32d988c8ffb
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# 篩選 {#filtering}

## 擷取篩選器中繼資料

每個資源都可使用篩選器。 若要識別與資源相關聯的篩選器，您需要對資源中繼資料執行GET要求。 此請求會傳回URL，其中針對指定資源定義了所有篩選器。 如需中繼資料的詳細資訊，請參閱[本節](metadata-mechanism.md)。

若要識別篩選器的中繼資料並決定其使用方式，您必須在先前傳回的URL上執行GET要求。

<br/>

***範例要求***

以下範例裝載顯示如何擷取「設定檔」資源的「byText」篩選中繼資料。 首先對「設定檔」資源中繼資料執行GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回描述篩選器的URL。

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

在URL上執行GET要求。 它會傳回設定檔資源的篩選器清單，以及與每個篩選器相關聯的中繼資料。

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## 篩選中繼資料結構

每個篩選器皆可使用相同的中繼資料結構：

* **@formType**&#x200B;和&#x200B;**@webPage**&#x200B;欄位是技術欄位。
* **資料**&#x200B;欄位提供如何使用篩選器的範例。
* **中繼資料**&#x200B;節點說明篩選引數。
* **條件**&#x200B;節點說明篩選的用途。 中繼資料節點中所述的篩選引數是用來建立篩選條件。 對於每個篩選條件，如果&#x200B;**enabledIf**&#x200B;為true，將會套用&#x200B;**expr**。

<br/>

篩選中繼資料結構範例：

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## 使用篩選器

篩選會針對下列請求執行：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

可以在單一請求中合併多個篩選器：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***範例要求***

* 擷取型別為「電子郵件」之「服務」資源的範例GET請求。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  對要求的回應。

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "created": "2019-09-25 23:20:35.000Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
              "label": "Marketing Newsletter",
              "lastModified": "2019-09-25 23:20:35.000Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              ...
          },
          ...
      ],
      ...
  }
  ```

* 擷取包含「Doe」的「profile」資源的GET要求範例
電子郵件或姓氏欄位（byText篩選器會搜尋電子郵件和姓氏欄位）。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  對要求的回應。

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          }
          ...
      ],
      ...
  }
  ```

* 擷取型別為「email」且標籤為「sport」之服務資源的範例GET請求。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  對要求的回應。

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "created": "2019-09-26 09:36:01.014Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
              "label": "sport",
              "lastModified": "2019-09-26 09:36:01.014Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              "name": "SVC13",
              ...
          }
      ],
      ...
  }
  ```

## 自訂篩選器

如果您想使用自訂篩選器，必須在Adobe Campaign Standard介面中建立和自訂篩選器。 之後，自訂篩選器將與現成篩選器具有相同的行為：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

如需詳細資訊，請參閱Campaign Standard檔案：

* [正在設定篩選定義](https://helpx.adobe.com/tw/campaign/standard/developing/using/configuring-filter-definition.html)。
* [使用案例：使用複合識別索引鍵](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html?lang=zh-Hant)呼叫資源。

<br/>

***範例要求***

擷取交易金額為100$或以上之「設定檔」資源的範例GET請求。 請注意，「byAmount」篩選器已先在Adobe Campaign Standard介面中定義，並連結至「交易」自訂表格。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
