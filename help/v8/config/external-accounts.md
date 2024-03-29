---
title: Campaign外部帳戶
description: Campaign外部帳戶
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 4%

---


# 設定外部帳戶 {#config-external-accounts}

Adobe Campaign 隨附一組預先定義的外部帳戶。若要設定與外部系統的連線，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流程中或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，您需要選取外部帳戶。

您可以從Adobe Campaign存取外部帳戶 **[!UICONTROL Explorer]**：瀏覽至 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* 作為Managed Cloud Service使用者，外部帳戶是根據Adobe為您的執行個體設定的，且不得修改。
>
>* 在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，特定 **[!UICONTROL Full FDA]** (ffda)外部帳戶管理Campaign本機資料庫和雲端資料庫之間的連線([!DNL Snowflake])。
>

## 促銷活動特定外部帳戶 {#ac-external-accounts}

Adobe Campaign使用下列技術帳戶來啟用及執行特定流程。

### 退回郵件 {#bounce-mails-external-account}

>[!NOTE]
>
>自Campaign v8.3開始，即可使用適用於POP3功能的Microsoft Exchange Online OAuth 2.0驗證。若要檢查您的版本，請參閱 [本節](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

此 **退回郵件** 外部帳戶指定要用來連線至電子郵件服務的外部POP3帳戶。 所有設定為POP3存取的伺服器都可以用來接收傳回郵件。

進一步瞭解中的傳入電子郵件 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}.

![](assets/bounce_external_1.png)

若要設定 **[!UICONTROL Bounce mails (defaultPopAccount)]** 外部帳戶：

* **[!UICONTROL Server]** - POP3伺服器的URL。

* **[!UICONTROL Port]** - POP3連線埠號碼。 預設連線埠為110。

* **[!UICONTROL Account]**  — 使用者名稱。

* **[!UICONTROL Password]**  — 使用者帳戶密碼。

* **[!UICONTROL Encryption]**  — 選擇的加密型別，介於 **[!UICONTROL By default]**， **[!UICONTROL POP3 + STARTTLS]**， **[!UICONTROL POP3]** 或 **[!UICONTROL POP3S]**.

  此 **退回郵件** 外部帳戶指定要用來連線至電子郵件服務的外部POP3帳戶。 所有設定為POP3存取的伺服器都可以用來接收傳回郵件。

* **[!UICONTROL Function]**  — 傳入電子郵件或SOAP路由器

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>使用Microsoft OAuth 2.0設定POP3外部帳戶之前，您必須先在Azure入口網站中註冊應用程式。 如需詳細資訊，請參閱此 [頁面](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

若要使用Microsoft OAuth 2.0設定POP3外部介面，請檢查 **[!UICONTROL Microsoft OAuth 2.0]** 並填入下列欄位：

* **[!UICONTROL Azure tenant]**  — 可在以下位置找到Azure ID (或目錄（租使用者） ID)： **Essentials** Azure入口網站中應用程式概觀的下拉式清單。

* **[!UICONTROL Azure Client ID]**  — 使用者端ID (或應用程式（使用者端） ID)可在以下位置找到： **Essentials** Azure入口網站中應用程式概觀的下拉式清單。

* **[!UICONTROL Azure Client secret]**  — 使用者端密碼ID可在 **使用者端密碼** 欄來自 **憑證和密碼** Azure入口網站中的應用程式功能表。

* **[!UICONTROL Azure Redirect URL]**  — 重新導向URL可在以下網址找到： **驗證** Azure入口網站中的應用程式功能表。 結尾應是下列語法 `nl/jsp/oauth.jsp`，例如 `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  輸入不同的認證後，您可以按一下 **[!UICONTROL Setup the connection]** 以完成外部帳戶設定。

### 路由 {#routing}

此 **[!UICONTROL Routing]** 外部帳戶可讓您根據安裝的套件，設定Adobe Campaign中可用的每個管道。

### 執行執行個體 {#execution-instance}

在交易式訊息環境中，執行例項會連結至控制例項並加以連結。 將異動訊息範本部署至執行例項。 瞭解更多關於訊息中心架構的資訊，請參閱 [此頁面](../architecture/architecture.md#transac-msg-archi).

## 存取外部系統外部帳戶 {#external-syst-external-accounts}

* **外部資料庫(FDA)** - **外部資料庫** 型別外部帳戶用於透過同盟資料存取(FDA)連線至外部資料庫。 進一步瞭解中的同盟資料存取(FDA)選項 [本節](../connect/fda.md).

  與Adobe Campaign v8相容的外部資料庫列於 [相容性矩陣](../start/compatibility-matrix.md)

* **X (先前稱為Twitter)** - **twitter** 型別外部帳戶用於將Campaign連線至您的X帳戶，以代表您張貼訊息。 進一步瞭解X整合，於 [本節](../connect/ac-tw.md).

## Adobe解決方案整合外部帳戶 {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - **[!UICONTROL Adobe Experience Cloud]** 外部帳戶用於實作AdobeIdentity Management服務(IMS)以連線至Adobe Campaign。 進一步瞭解中的AdobeIdentity Management服務(IMS) [本節](../start/connect.md#logon-to-ac).

* **網站分析** - **[!UICONTROL Web Analytics (Adobe Analytics)]** 外部帳戶可用來設定從Adobe Analytics到Adobe Campaign的資料傳輸。 進一步瞭解Adobe Campaign - Adobe Analytics整合，位於 [此頁面](../connect/ac-aa.md).

* **Adobe Experience Manager** - **[!UICONTROL AEM]** 外部帳戶可讓您直接在Adobe Experience Manager中管理電子郵件傳遞內容以及表單。 進一步瞭解Adobe Campaign - Adobe Analytics整合，位於 [此頁面](../connect/ac-aem.md).


## CRM聯結器外部帳戶 {#crm-external-accounts}

* **Microsoft Dynamics CRM** - **[!UICONTROL Microsoft Dynamics CRM]** 外部帳戶可讓您將Microsoft Dynamics資料匯入和匯出至Adobe Campaign。 進一步瞭解Adobe Campaign - Microsoft Dynamics CRM整合，位於 [此頁面](../connect/ac-ms-dyn.md).

* **Salesforce.com** - **[!UICONTROL Salesforce CRM]** 外部帳戶可讓您將Salesforce資料匯入和匯出至Adobe Campaign。 深入瞭解Adobe Campaign - Salesforce.com CRM整合，位於 [此頁面](../connect/ac-sfdc.md).

## 傳輸資料外部帳戶 {#transfer-data-external-accounts}

這些外部帳戶可用於匯入或匯出資料至Adobe Campaign，使用如下 **[!UICONTROL Transfer file]** 工作流程活動。 進一步瞭解 **檔案傳輸** 在工作流程中 [此頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}.

* **FTP和SFTP** - **FTP** 外部帳戶可讓您設定並測試對Adobe Campaign外部伺服器的存取權。 若要設定與外部系統（例如用於檔案傳輸的SFTP或FTP伺服器898）的連線，您可以建立自己的外部帳戶。

  若要這麼做，請在此外部帳戶中指定用來建立與SFTP或FTP伺服器連線的位址和認證。

  >[!NOTE]
  >
  >從版本8.5開始，您現在可以在設定SFTP外部帳戶時，使用私密金鑰安全地驗證。 [進一步瞭解金鑰管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}.

* **Amazon簡單儲存服務(S3)** - **AWS S3** 聯結器可用來匯入或匯出資料至Adobe Campaign，使用如下 **[!UICONTROL Transfer file]** 工作流程活動。 當您設定此新外部帳戶時，您必須提供下列詳細資訊：

   * **[!UICONTROL AWS S3 Account Server]**：伺服器的URL，填入如下：   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**：瞭解如何在中尋找您的AWS存取金鑰ID [Amazon檔案](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**：瞭解如何在中尋找AWS的秘密存取金鑰 [Amazon檔案](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**：進一步瞭解中的AWS地區 [Amazon檔案](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * 此 **[!UICONTROL Use server side encryption]** 核取方塊可讓您將檔案儲存為S3加密模式。 瞭解如何在中尋找存取金鑰ID和機密存取金鑰 [Amazon檔案](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Azure Blob儲存體** - **Azure** 外部帳戶可用於匯入或匯出資料至Adobe Campaign，使用如下 **[!UICONTROL Transfer file]** 工作流程活動。 若要設定 **Azure** 若要使用Adobe Campaign，您必須提供下列詳細資料：

   * **[!UICONTROL Server]**：Azure Blob儲存伺服器的URL。

   * **[!UICONTROL Encryption]**：加密型別，介於 **[!UICONTROL None]** 或 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**：瞭解如何尋找您的 **[!UICONTROL Access key]** 在 [Microsoft檔案](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
