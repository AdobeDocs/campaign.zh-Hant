---
title: 市場活動外部帳戶
description: 市場活動外部帳戶
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: c46eaa73deed643a4e92928b6ce2b1beb1596d73
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 4%

---


# 配置外部帳戶

Adobe Campaign 隨附一組預先定義的外部帳戶。為了設定與外部系統的連接，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流中設定檔案傳輸或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，需要選擇外部帳戶。

您可以從Adobe Campaign訪問外部帳戶 **[!UICONTROL Explorer]**:瀏覽 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

![](assets/external-accounts.png)


>[!CAUTION]
>
>* 作為托管Cloud Services用戶，外部帳戶按Adobe配置給您的實例，不得修改。
>
>* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，特定 **[!UICONTROL Full FDA]** (ffda)外部帳戶管理市場活動本地資料庫和雲資料庫之間的連接([!DNL Snowflake])。
>


## 特定於市場活動的外部帳戶

Adobe Campaign使用以下技術帳戶啟用和執行特定進程。

### 退回郵件 {#bounce-mails-external-account}

>[!NOTE]
>
>從8.3版活動開始，可使用MicrosoftExchange Online OAuth 2.0 POP3功能驗證。要檢查您的版本，請參閱 [此部分](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)。

的 **退回郵件** 外部帳戶指定用於連接到電子郵件服務的外部POP3帳戶。 為POP3訪問配置的所有伺服器都可用於接收返回郵件。

瞭解有關入站電子郵件的詳細資訊 [此頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html)。

![](assets/bounce_external_1.png)

配置 **[!UICONTROL Bounce mails (defaultPopAccount)]** 外部帳戶：

* **[!UICONTROL Server]** - POP3伺服器的URL。

* **[!UICONTROL Port]** - POP3連接埠號。 預設埠為110。

* **[!UICONTROL Account]**  — 用戶名。

* **[!UICONTROL Password]**  — 用戶帳戶密碼。

* **[!UICONTROL Encryption]**  — 選擇的加密類型 **[!UICONTROL By default]**。 **[!UICONTROL POP3 + STARTTLS]**。 **[!UICONTROL POP3]** 或 **[!UICONTROL POP3S]**。

   的 **退回郵件** 外部帳戶指定用於連接到電子郵件服務的外部POP3帳戶。 為POP3訪問配置的所有伺服器都可用於接收返回郵件。

* **[!UICONTROL Function]**  — 入站電子郵件或SOAP路由器

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>在使用MicrosoftOAuth 2.0配置POP3外部帳戶之前，您首先需要在Azure門戶中註冊您的應用程式。 如需關於此項目的詳細資訊，請參閱此[頁面](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

要使用MicrosoftOAuth 2.0配置POP3外部，請檢查 **[!UICONTROL Microsoft OAuth 2.0]** 的子菜單。

* **[!UICONTROL Azure tenant]** - Azure ID(或目錄（租戶）ID) **基本知識** Azure門戶中應用程式概述的下拉框。

* **[!UICONTROL Azure Client ID]**  — 客戶端ID(或應用程式（客戶端）ID)可在 **基本知識** Azure門戶中應用程式概述的下拉框。

* **[!UICONTROL Azure Client secret]**  — 在 **客戶端機密** 列 **證書和機密** Azure門戶中應用程式的菜單。

* **[!UICONTROL Azure Redirect URL]**  — 在 **驗證** Azure門戶中應用程式的菜單。 它應以以下語法結尾 `nl/jsp/oauth.jsp`，例如 `https://redirect.adobe.net/nl/jsp/oauth.jsp`。

   輸入不同的憑據後，可以按一下 **[!UICONTROL Setup the connection]** 完成外部帳戶配置。

### 路由 {#routing}

的 **[!UICONTROL Routing]** 外部帳戶允許您根據安裝的軟體包配置Adobe Campaign的每個可用通道。

>[!CAUTION]
>
>的 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk)外部帳戶 **不能** 在Adobe Campaignv8中啟用。

### 執行實例 {#execution-instance}

在事務性消息傳遞的上下文中，執行實例被連結到控制實例並連接它們。 事務性消息模板被部署到執行實例。 瞭解有關中消息中心體系結構的詳細資訊 [此頁](../architecture/architecture.md#transac-msg-archi)。

## 訪問外部系統外部帳戶

* **外部資料庫(FDA)** - **外部資料庫** 類型外部帳戶用於通過聯合資料存取(FDA)連接到外部資料庫。 瞭解有關聯合資料存取(FDA)選項的詳細資訊，請參閱 [此部分](../connect/fda.md)。

   與Adobe Campaignv8相容的外部資料庫列在 [相容性矩陣](../start/compatibility-matrix.md)

* **Twitter** - **Twitter** 鍵入external account（外部帳戶）用於將「市場活動」連接到您的twitter帳戶，以便代表您發佈消息。 瞭解有關Twitter整合的詳細資訊 [此部分](../connect/ac-tw.md)。

## Adobe解決方案整合外部客戶

* **Adobe Experience Cloud** - **[!UICONTROL Adobe Experience Cloud]** 外部帳戶用於實現AdobeIdentity Management服務(IMS)以連接到Adobe Campaign。 瞭解有關AdobeIdentity Management服務(IMS)的更多資訊 [此部分](../start/connect.md#logon-to-ac)。

* **Web分析** - **[!UICONTROL Web Analytics (Adobe Analytics)]** 外部帳戶用於配置從Adobe Analytics到Adobe Campaign的資料傳輸。 瞭解有關Adobe Campaign-Adobe Analytics在 [此頁](../connect/ac-aa.md)。

* **Adobe Experience Manager** - **[!UICONTROL AEM]** 外部帳戶允許您直接在Adobe Experience Manager管理電子郵件遞送的內容和表單。 瞭解有關Adobe Campaign-Adobe Analytics在 [此頁](../connect/ac-aem.md)。


## CRM連接器外部帳戶

* **Microsoft動力客戶關係管理** - **[!UICONTROL Microsoft Dynamics CRM]** 外部帳戶允許您將MicrosoftDynamics資料導入和導出到Adobe Campaign。 瞭解有關Adobe Campaign-MicrosoftDynamics CRM整合的詳細資訊 [此頁](../connect/ac-ms-dyn.md)。

* **Salesforce.com** - **[!UICONTROL Salesforce CRM]** 外部帳戶允許您將Salesforce資料導入和導出到Adobe Campaign。 瞭解有關Adobe Campaign- Salesforce.com CRM整合的詳細資訊 [此頁](../connect/ac-sfdc.md)。

## 傳輸資料外部帳戶

這些外部帳戶可用於使用 **[!UICONTROL Transfer file]** 工作流活動。 瞭解有關 **檔案傳輸** 在工作流中 [此頁](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html)。

* **FTP和SFTP** - **FTP** 外部帳戶允許您配置和test對Adobe Campaign以外的伺服器的訪問。 要設定與外部系統（如用於檔案傳輸的SFTP或FTP伺服器898）的連接，可以建立自己的外部帳戶。

   為此，請在此外部帳戶中指定用於建立與SFTP或FTP伺服器連接的地址和憑據。

* **Amazon簡單儲存服務(S3)** - **AWSS3** 連接器可使用 **[!UICONTROL Transfer file]** 工作流活動。 當您設定此新外部帳戶時，您必須提供下列詳細資訊：

   * **[!UICONTROL AWS S3 Account Server]**:伺服器的URL，填寫如下：   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**:瞭解如何在中查找您的AWS訪問密鑰ID [Amazon文檔](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}。

   * **[!UICONTROL Secret access key to AWS]**:瞭解如何在中查找到AWS的機密訪問密鑰 [Amazon文檔](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}。

   * **[!UICONTROL AWS Region]**:瞭解有關AWS地區的更多資訊 [Amazon文檔](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}。

   * 的 **[!UICONTROL Use server side encryption]** 複選框允許您將檔案儲存在S3加密模式下。 瞭解如何在中查找訪問密鑰ID和密鑰訪問密鑰 [Amazon文檔](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}。

* **Azure Blob儲存** - **Azure** 外部帳戶可使用 **[!UICONTROL Transfer file]** 工作流活動。 配置 **Azure** 要與Adobe Campaign合作，您需要提供以下詳細資訊：

   * **[!UICONTROL Server]**:Azure Blob儲存伺服器的URL。

   * **[!UICONTROL Encryption]**:加密類型 **[!UICONTROL None]** 或 **[!UICONTROL SSL]**。

   * **[!UICONTROL Access key]**:瞭解如何查找 **[!UICONTROL Access key]** 在 [Microsoft文檔](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}。
