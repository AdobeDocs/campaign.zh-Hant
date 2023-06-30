---
title: 技術使用者移轉至Adobe Developer主控台
description: 瞭解如何在Adobe Developer主控台上將Campaign技術操作員移轉至技術帳戶
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---

# Campaign技術運運算元移轉至Adobe Developer主控台 {#migrate-tech-users-to-ims}

自Campaign v8.5開始，改善對Campaign v8的驗證程式。 技術操作員必須使用 [AdobeIdentity Management系統(IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} 以連線至Campaign。 技術運運算元是為API整合明確建立的Campaign使用者設定檔。 本文詳細說明將技術運運算元移轉至Adobe Developer主控台上的技術帳戶所需的步驟。

## 哪些部分有所變更？{#ims-changes}

Campaign一般使用者已透過AdobeIdentity Management System (IMS)，使用其Adobe ID連線至Adobe Campaign主控台。 為了強化安全性和驗證程式，Adobe Campaign使用者端應用程式現在會直接使用IMS技術帳戶權杖呼叫Campaign API。

深入瞭解中的新伺服器對伺服器驗證程式 [Adobe Developer Console檔案](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

此變更適用於從Campaign v8.5開始，且將 **強制** 從Campaign v8.6開始。


## 您有受到影響嗎？{#ims-impacts}

如果您使用Campaign API，則需要將技術運運算元移轉至Adobe Developer主控台，如下所述。

## 如何移轉？{#ims-migration-procedure}

### 必要條件{#ims-migration-prerequisites}

在開始移轉程式之前，您必須聯絡您的Adobe代表，以便Adobe技術團隊可以移轉您現有的操作員群組和已命名的許可權來AdobeIdentity Management System (IMS)。

### 步驟1 — 在Adobe Developer主控台中建立/更新Campaign專案{#ims-migration-step-1}

整合是作為一部分建立的 **專案** 在Adobe Developer Console中。 進一步瞭解中的專案 [Adobe Developer Console檔案](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

身為Campaign v8使用者，您應已在Adobe Developer Console擁有專案。 如果沒有，則必須建立專案。 建立專案的步驟已詳細說明 [在Adobe Developer Console檔案中](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

存取您的Campaign專案後，您可以新增服務，包括API、Adobe Campaign和I/O管理API。 針對此移轉，您必須在專案中新增以下API： **I/O管理API** 和 **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### 步驟2 — 使用「伺服器對伺服器」驗證新增API至您的專案{#ims-migration-step-2}

在Adobe Developer主控台中建立專案後，請新增使用伺服器對伺服器驗證的API。 瞭解如何在中設定OAuth伺服器對伺服器認證 [Adobe Developer Console檔案](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

成功連線API後，您可以存取新產生的認證（包括使用者端ID和使用者端密碼），並產生存取權杖。

### 步驟3 — 將產品設定檔新增至專案{#ims-migration-step-3}

您現在可以將Campaign產品設定檔新增至專案，如下所述：

1. 開啟Adobe Campaign API。
1. 按一下 **編輯產品設定檔** 按鈕

   ![](assets/do-not-localize/ims-edit-api.png)

1. 將所有相關產品設定檔指派至API （例如「messagecenter」），然後儲存變更。
1. 瀏覽至 **認證詳細資料** 標籤中，並複製 **技術帳戶電子郵件** 值。

### 步驟4 — 更新使用者端主控台中的技術運運算元 {#ims-migration-step-4}


只有在已為此運運算元（而不是透過運運算元的群組）定義特定檔案夾許可權或命名許可權時，才需要執行此步驟。

您現在需要更新Adobe Campaign使用者端主控台中新建立的技術運運算元。 您必須將現有技術操作員檔案夾許可權套用至新的技術操作員。
若要更新此運運算元，請遵循下列步驟：

1. 從Campaign Client Console檔案總管，瀏覽至 **管理>存取管理>操作員**.
1. 存取用於API的現有技術運運算元。
1. 瀏覽至檔案夾許可權，然後檢查許可權。
1. 將相同的許可權套用至新建立的技術操作員。 此操作員的電子郵件是 **技術帳戶電子郵件** 值先前已複製。
1. 儲存您的變更。


>[!CAUTION]
>
>新的技術操作員必須至少發出一個API呼叫，才能新增至Campaign使用者端主控台。
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### 步驟5 — 驗證設定 {#ims-migration-step-5}

若要嘗試連線，請依照以下詳細步驟操作： [Adobe Developer Console認證指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} 以產生存取權杖並複製提供的範例cURL命令。


### 步驟6 — 更新協力廠商API整合 {#ims-migration-step-6}

您必須更新API與協力廠商系統的整合。

如需API整合步驟的詳細資訊，包括順利整合的範常式式碼，請參閱 [Adobe Developer Console驗證檔案](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### 步驟7 — 移除舊的技術操作員 {#ims-migration-step-7}


移轉與技術帳戶使用者整合的所有API/自訂程式碼後。 您可以從Campaign使用者端主控台刪除舊的技術運運算元。

### Soap呼叫範例{#ims-migration-samples}

實現並驗證移轉程式後，Soap呼叫會更新如下：

* 移轉前

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* 移轉後

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  Authorization: Bearer <IMS_Technical_Token_Token>
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken></urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```
