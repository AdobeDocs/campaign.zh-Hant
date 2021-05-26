---
solution: Campaign v8
product: Adobe Campaign
title: 促銷活動外部帳戶
description: 促銷活動外部帳戶
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 4%

---


# 設定外部帳戶

Adobe Campaign 隨附一組預先定義的外部帳戶。若要設定與外部系統的連線，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流程中設定檔案傳輸，或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，您需要選取外部帳戶。

您可以從Adobe Campaign **[!UICONTROL Explorer]**&#x200B;存取外部帳戶：瀏覽至&#x200B;**[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

![](assets/external-accounts.png)


>[!CAUTION]
>
>特定的&#x200B;**[!UICONTROL Full FDA]**(ffda)外部帳戶管理Campaign本機資料庫和雲端資料庫([!DNL Snowflake])之間的連線。
>
>作為「受管理Cloud Services」使用者，此外部帳戶會依Adobe為您的執行個體設定。 不得修改。


## 促銷活動專用外部帳戶

Adobe Campaign會使用下列技術帳戶來啟用及執行特定程式。

:speech_balloon:以「受管理Cloud Services」使用者的身分，Adobe會為您設定所有促銷活動專用的外部帳戶。

* **退回郵件(POP3)**

   **退回郵件**&#x200B;外部帳戶指定用於連接到電子郵件服務的外部POP3帳戶。 所有為POP3訪問配置的伺服器都可用於接收返回郵件。

   :[!DNL :arrow_upper_right:]:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html)中深入了解傳入電子郵件

* **路由**

   **[!UICONTROL Routing]**&#x200B;外部帳戶可讓您根據安裝的套件，設定Adobe Campaign中可用的每個通道。

   >[!CAUTION]
   >
   >**[!UICONTROL Internal email delivery routing]**(defaultEmailBulk)外部帳戶&#x200B;**不得**&#x200B;在Adobe Campaign v8中啟用。

* **執行實例**

   在交易式訊息傳送的內容中，執行例項會連結至控制例項並加以連結。 交易式訊息範本會部署至執行例項。

   [!DNL :bulb:] 在本頁面中了解更多訊息中 [心架構](../dev/architecture.md#transac-msg-archi)。

## 訪問外部系統外部帳戶

* **外部資料庫(FDA)**

   使用&#x200B;**外部資料庫**&#x200B;鍵入外部帳戶以通過FDA連接到外部資料庫。

   與Adobe Campaign v8相容的外部資料庫列在[相容性矩陣](../start/compatibility-matrix.md)中

   [!DNL :bulb:] 了解更多同盟資料存取(FDA)選項，請參 [閱本節](../connect/fda.md)。

## Adobe解決方案整合外部帳戶

* **Adobe Experience Cloud**

   若要使用Adobe ID連線至Adobe Campaign主控台，您必須設定&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帳戶。

   [!DNL :bulb:] 了解更多AdobeIdentity Management服務(IMS)，請參 [閱本節](../start/connect.md#connect-ims)。

   :speech_balloon:以「受管理的Cloud Services」使用者身分，[聯絡Adobe](../start/campaign-faq.md#support)以透過促銷活動實作AdobeIMS。

* **網站分析**

   使用&#x200B;**[!UICONTROL Web Analytics (Adobe Analytics)]**&#x200B;外部帳戶來設定從Adobe Analytics到Adobe Campaign的資料傳輸。

   [!DNL :bulb:] 深入了解Adobe Campaign - Adobe Analytics在本頁 [的整合](../connect/ac-aa.md)。

   :speech_balloon:以「受管理的Cloud Services」使用者身分，[聯絡Adobe](../start/campaign-faq.md#support)以將Adobe Analytics與Campaign整合。

   * **Adobe Experience Manager**
   **[!UICONTROL AEM]**&#x200B;外部帳戶可讓您直接在Adobe Experience Manager中管理電子郵件傳送的內容以及表單。

   [!DNL :bulb:] 深入了解Adobe Campaign - Adobe Analytics在本頁 [的整合](../connect/ac-aem.md)。

   :speech_balloon:以「受管Cloud Services」使用者身分，[聯絡Adobe](../start/campaign-faq.md#support)以整合Adobe Experience Manager與Adobe Campaign。


## CRM連接器外部帳戶

* **Microsoft Dynamics CRM**

   **[!UICONTROL Microsoft Dynamics CRM]**&#x200B;外部帳戶可讓您將Microsoft Dynamics資料匯入和匯出至Adobe Campaign。

   [!DNL :bulb:] 深入了解Adobe Campaign — 本頁提供Microsoft Dynamics CRM整 [合](../connect/crm.md)。

   使用&#x200B;**[!UICONTROL Web API]**&#x200B;部署類型和&#x200B;**[!UICONTROL Password credentials]**&#x200B;身份驗證時，您需要提供以下詳細資訊：

   * **[!UICONTROL Account]**:用於登入Microsoft CRM的帳戶。

   * **[!UICONTROL Server]**:Microsoft CRM伺服器的URL。

   * **[!UICONTROL Client identifier]**:可從類別「 」欄位中的Microsoft Azure管理入口網站找 **[!UICONTROL Update your code]** 到用 **[!UICONTROL Client ID]** 戶端ID。

   * **[!UICONTROL CRM version]**:介於、或之間 **[!UICONTROL Dynamics CRM 2007]**&#x200B;的 **[!UICONTROL Dynamics CRM 2015]** CRM版 **[!UICONTROL Dynamics CRM 2016]**&#x200B;本。
   使用&#x200B;**[!UICONTROL Web API]**&#x200B;部署類型和&#x200B;**[!UICONTROL Certificate]**&#x200B;身份驗證時，您需要提供以下詳細資訊：

   * **[!UICONTROL Server]**:Microsoft CRM伺服器的URL。

   * **[!UICONTROL Private Key (Base64 encoded)]**:編碼為Base64的私鑰

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**:可從類別「 」欄位中的Microsoft Azure管理入口網站找 **[!UICONTROL Update your code]** 到用 **[!UICONTROL Client ID]** 戶端ID。

   * **[!UICONTROL CRM version]**:介於、或之間 **[!UICONTROL Dynamics CRM 2007]**&#x200B;的 **[!UICONTROL Dynamics CRM 2015]** CRM版 **[!UICONTROL Dynamics CRM 2016]**&#x200B;本。


* **Salesforce.com**

   **[!UICONTROL Salesforce CRM]**&#x200B;外部帳戶可讓您將Salesforce資料匯入和匯出至Adobe Campaign。

   若要設定Salesforce CRM外部帳戶以搭配Adobe Campaign運作，您需要提供下列詳細資訊：

   * **[!UICONTROL Account]**:用於登入Salesforce CRM的帳戶。

   * **[!UICONTROL Password]**:用於登入Salesforce CRM的密碼。

   * **[!UICONTROL Client identifier]**:在本頁面中了解如何尋找您的用 [戶端識別碼](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL Security token]**:在本頁面中了解如何尋找您的安 [全權杖](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL API version]**:選取API的版本。對於此外部帳戶，您需要使用配置嚮導配置Salesforce CRM。

## 傳輸資料外部帳戶

這些外部帳戶可用於使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流程活動將資料匯入或匯出至Adobe Campaign。

:[!DNL :arrow_upper_right:]:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html)中進一步了解工作流程中的檔案傳輸

* **FTP和SFTP**

   **FTP**外部帳戶可讓您設定並測試對Adobe Campaign以外伺服器的存取。 若要設定與外部系統（例如用於檔案傳輸的SFTP或FTP伺服器898）的連線，您可以建立自己的外部帳戶。
若要這麼做，請在此外部帳戶中指定用來建立與SFTP或FTP伺服器連線的位址和憑證。

* **Amazon Simple Storage Service(S3)**

   **AWS S3**&#x200B;連接器可用來使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流程活動將資料匯入或匯出至Adobe Campaign。 當您設定此新外部帳戶時，您必須提供下列詳細資訊：

   * **[!UICONTROL AWS S3 Account Server]**:伺服器的URL，填入如下：    ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**:在Amazon檔案中了解如何找到您的AWS存取 [密鑰ID](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) 。

   * **[!UICONTROL Secret access key to AWS]**:在Amazon檔案中了解如何找到AWS的秘密存 [取金鑰](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/)。

   * **[!UICONTROL AWS Region]**:在Amazon檔案中進一步了 [解AWS地區](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)。

   * **[!UICONTROL Use server side encryption]**&#x200B;核取方塊可讓您以S3加密模式儲存檔案。 在[Amazon檔案](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)中了解如何尋找存取金鑰ID和秘密存取金鑰。

* **Azure Blob儲存**

   **Azure**&#x200B;外部帳戶可用於使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流程活動將資料匯入或匯出至Adobe Campaign。 若要設定&#x200B;**Azure**&#x200B;外部帳戶以搭配Adobe Campaign運作，您需要提供下列詳細資料：

   * **[!UICONTROL Server]**:Azure Blob儲存伺服器的URL。

   * **[!UICONTROL Encryption]**:或之間的加 **[!UICONTROL None]** 密類 **[!UICONTROL SSL]**&#x200B;型。

   * **[!UICONTROL Access key]**:在Microsoft文檔中了 **[!UICONTROL Access key]** 解 [如何查找](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)。

