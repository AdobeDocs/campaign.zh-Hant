---
title: 市場活動外部帳戶
description: 市場活動外部帳戶
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# 配置外部帳戶

Adobe Campaign 隨附一組預先定義的外部帳戶。為了設定與外部系統的連接，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流中設定檔案傳輸或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，需要選擇外部帳戶。

您可以從Adobe Campaign訪問外部帳戶 **[!UICONTROL Explorer]**:瀏覽 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

![](assets/external-accounts.png)


>[!CAUTION]
>
>特定 **[!UICONTROL Full FDA]** (ffda)外部帳戶管理市場活動本地資料庫和雲資料庫之間的連接([!DNL Snowflake])。
>
>作為托管Cloud Services用戶，此外部帳戶按Adobe配置給您的實例。 不得修改。


## 特定於市場活動的外部帳戶

Adobe Campaign使用以下技術帳戶啟用和執行特定進程。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶，Adobe為您配置所有特定於市場活動的外部帳戶。

* **退回郵件(POP3)**

   的 **退回郵件** 外部帳戶指定用於連接到電子郵件服務的外部POP3帳戶。 為POP3訪問配置的所有伺服器都可用於接收返回郵件。

   ![](../assets/do-not-localize/book.png) 瞭解有關入站電子郵件的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;

* **路由**

   的 **[!UICONTROL Routing]** 外部帳戶允許您根據安裝的軟體包配置Adobe Campaign的每個可用通道。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk)外部帳戶 **不能** 在Adobe Campaignv8中啟用。

* **執行實例**

   在事務性消息傳遞的上下文中，執行實例被連結到控制實例並連接它們。 事務性消息模板被部署到執行實例。

   ![](../assets/do-not-localize/glass.png) 瞭解有關中消息中心體系結構的詳細資訊 [此頁](../dev/architecture.md#transac-msg-archi)。

## 訪問外部系統外部帳戶

* **外部資料庫(FDA)**

   使用 **外部資料庫** 鍵入外部帳戶以通過FDA連接到外部資料庫。

   與Adobe Campaignv8相容的外部資料庫列在 [相容性矩陣](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) 瞭解有關聯合資料存取(FDA)選項的詳細資訊，請參閱 [此部分](../connect/fda.md)。

## Adobe解決方案整合外部客戶

* **Adobe Experience Cloud**

   的 **[!UICONTROL Adobe Experience Cloud]** 外部帳戶用於實現Adobe IMS以使用Adobe ID連接到Adobe Campaign控制台。

   ![](../assets/do-not-localize/glass.png) 瞭解有關AdobeIdentity Management服務(IMS)的更多資訊 [此部分](../start/connect.md#connect-ims)。

* **網站分析**

   使用 **[!UICONTROL Web Analytics (Adobe Analytics)]** 外部帳戶，用於配置從Adobe Analytics到Adobe Campaign的資料傳輸。

   ![](../assets/do-not-localize/glass.png) 瞭解有關Adobe Campaign-Adobe Analytics在 [此頁](../connect/ac-aa.md)。

   ![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 把Adobe Analytics和競選結合起來。

   * **Adobe Experience Manager**
   的 **[!UICONTROL AEM]** 外部帳戶允許您直接在Adobe Experience Manager管理電子郵件遞送的內容和表單。

   ![](../assets/do-not-localize/glass.png) 瞭解有關Adobe Campaign-Adobe Analytics在 [此頁](../connect/ac-aem.md)。

   ![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 讓Adobe Experience Manager和Adobe Campaign融為一體。


## CRM連接器外部帳戶

* **Microsoft動力客戶關係管理**

   的 **[!UICONTROL Microsoft Dynamics CRM]** 外部帳戶允許您將MicrosoftDynamics資料導入和導出到Adobe Campaign。

   ![](../assets/do-not-localize/glass.png) 瞭解有關Adobe Campaign-MicrosoftDynamics CRM整合的詳細資訊 [此頁](../connect/crm.md)。

   與 **[!UICONTROL Web API]** 部署類型和 **[!UICONTROL Password credentials]** 驗證，您需要提供以下詳細資訊：

   * **[!UICONTROL Account]**:用於登錄MicrosoftCRM的帳戶。

   * **[!UICONTROL Server]**:您的MicrosoftCRM伺服器的URL。

   * **[!UICONTROL Client identifier]**:可從以下位置的MicrosoftAzure管理門戶中找到的客戶端ID **[!UICONTROL Update your code]** 類別， **[!UICONTROL Client ID]** 的子菜單。

   * **[!UICONTROL CRM version]**:CRM的版本 **[!UICONTROL Dynamics CRM 2007]**。 **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**。
   與 **[!UICONTROL Web API]** 部署類型和 **[!UICONTROL Certificate]** 驗證，您需要提供以下詳細資訊：

   * **[!UICONTROL Server]**:您的MicrosoftCRM伺服器的URL。

   * **[!UICONTROL Private Key (Base64 encoded)]**:編碼到Base64的私鑰

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**:可從以下位置的MicrosoftAzure管理門戶中找到的客戶端ID **[!UICONTROL Update your code]** 類別， **[!UICONTROL Client ID]** 的子菜單。

   * **[!UICONTROL CRM version]**:CRM的版本 **[!UICONTROL Dynamics CRM 2007]**。 **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**。


* **Salesforce.com**

   的 **[!UICONTROL Salesforce CRM]** 外部帳戶允許您將Salesforce資料導入和導出到Adobe Campaign。

   要配置Salesforce CRM外部帳戶以與Adobe Campaign協作，您需要提供以下詳細資訊：

   * **[!UICONTROL Account]**:用於登錄Salesforce CRM的帳戶。

   * **[!UICONTROL Password]**:用於登錄Salesforce CRM的密碼。

   * **[!UICONTROL Client identifier]**:瞭解如何在 [此頁](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL Security token]**:瞭解如何在 [此頁](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL API version]**:選擇API的版本。 對於此外部帳戶，您需要使用配置嚮導配置Salesforce CRM。

## 傳輸資料外部帳戶

這些外部帳戶可用於使用 **[!UICONTROL Transfer file]** 工作流活動。

![](../assets/do-not-localize/book.png) 瞭解有關中的工作流中檔案傳輸的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;

* **FTP和SFTP**

   的 **FTP** 外部帳戶允許您配置和test對Adobe Campaign以外的伺服器的訪問。 要設定與外部系統（如用於檔案傳輸的SFTP或FTP伺服器898）的連接，可以建立自己的外部帳戶。
為此，請在此外部帳戶中指定用於建立與SFTP或FTP伺服器連接的地址和憑據。

* **Amazon簡單儲存服務(S3)**

   的 **AWSS3** 連接器可使用 **[!UICONTROL Transfer file]** 工作流活動。 當您設定此新外部帳戶時，您必須提供下列詳細資訊：

   * **[!UICONTROL AWS S3 Account Server]**:伺服器的URL，填寫如下：   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**:瞭解如何在中查找您的AWS訪問密鑰ID [Amazon文檔](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) 。

   * **[!UICONTROL Secret access key to AWS]**:瞭解如何在中查找到AWS的機密訪問密鑰 [Amazon文檔](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/)。

   * **[!UICONTROL AWS Region]**:瞭解有關AWS地區的更多資訊 [Amazon文檔](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)。

   * 的 **[!UICONTROL Use server side encryption]** 複選框允許您將檔案儲存在S3加密模式下。 瞭解如何在中查找訪問密鑰ID和密鑰訪問密鑰 [Amazon文檔](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)。

* **Azure Blob儲存**

   的 **Azure** 外部帳戶可使用 **[!UICONTROL Transfer file]** 工作流活動。 配置 **Azure** 要與Adobe Campaign合作，您需要提供以下詳細資訊：

   * **[!UICONTROL Server]**:Azure Blob儲存伺服器的URL。

   * **[!UICONTROL Encryption]**:加密類型 **[!UICONTROL None]** 或 **[!UICONTROL SSL]**。

   * **[!UICONTROL Access key]**:瞭解如何查找 **[!UICONTROL Access key]** 在 [Microsoft文檔](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)。
