---
title: 促銷活動外部帳戶
description: 促銷活動外部帳戶
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# 設定外部帳戶

Adobe Campaign 隨附一組預先定義的外部帳戶。若要設定與外部系統的連線，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流程中設定檔案傳輸，或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，您需要選取外部帳戶。

您可以從Adobe Campaign存取外部帳戶 **[!UICONTROL Explorer]**:瀏覽 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>特定 **[!UICONTROL Full FDA]** (ffda)外部帳戶管理Campaign本機資料庫和雲端資料庫([!DNL Snowflake])。
>
>作為「受管理Cloud Services」使用者，此外部帳戶會依Adobe為您的執行個體設定。 不得修改。


## 促銷活動專用外部帳戶

Adobe Campaign會使用下列技術帳戶來啟用及執行特定程式。

![](../assets/do-not-localize/speech.png)  以「受管理Cloud Services」使用者的身分，Adobe會為您設定所有促銷活動專用的外部帳戶。

* **退回郵件(POP3)**

   此 **退回郵件** 外部帳戶指定用於連接到電子郵件服務的外部POP3帳戶。 所有為POP3訪問配置的伺服器都可用於接收返回郵件。

   ![](../assets/do-not-localize/book.png) 進一步了解傳入電子郵件(位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **路由**

   此 **[!UICONTROL Routing]** 外部帳戶可讓您根據安裝的套件，設定Adobe Campaign中可用的每個管道。

   >[!CAUTION]
   >
   >此 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk)外部帳戶 **不能** 在Adobe Campaign v8中啟用。

* **執行實例**

   在交易式訊息傳送的內容中，執行例項會連結至控制例項並加以連結。 交易式訊息範本會部署至執行例項。

   ![](../assets/do-not-localize/glass.png) 進一步了解訊息中心架構，位於 [本頁](../dev/architecture.md#transac-msg-archi).

## 訪問外部系統外部帳戶

* **外部資料庫(FDA)**

   使用 **外部資料庫** 輸入外部帳戶以透過FDA連線至外部資料庫。

   與Adobe Campaign v8相容的外部資料庫列於 [相容性矩陣](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) 深入了解同盟資料存取(FDA)選項，位於 [本節](../connect/fda.md).

## Adobe解決方案整合外部帳戶

* **Adobe Experience Cloud**

   此 **[!UICONTROL Adobe Experience Cloud]** 外部帳戶會實作Adobe IMS，以使用Adobe ID連線至Adobe Campaign主控台。

   ![](../assets/do-not-localize/glass.png) 進一步了解AdobeIdentity Management服務(IMS)，位於 [本節](../start/connect.md#connect-ims).

* **網站分析**

   使用 **[!UICONTROL Web Analytics (Adobe Analytics)]** 外部帳戶，以設定從Adobe Analytics到Adobe Campaign的資料傳輸。

   ![](../assets/do-not-localize/glass.png) 深入了解Adobe Campaign - Adobe Analytics在 [本頁](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 將Adobe Analytics與Campaign整合。

   * **Adobe Experience Manager**
   此 **[!UICONTROL AEM]** 外部帳戶可讓您直接在Adobe Experience Manager中管理電子郵件傳送的內容以及表單。

   ![](../assets/do-not-localize/glass.png) 深入了解Adobe Campaign - Adobe Analytics在 [本頁](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 整合Adobe Experience Manager與Adobe Campaign。


## CRM連接器外部帳戶

* **Microsoft Dynamics CRM**

   此 **[!UICONTROL Microsoft Dynamics CRM]** 外部帳戶可讓您將Microsoft Dynamics資料匯入和匯出至Adobe Campaign。

   ![](../assets/do-not-localize/glass.png) 深入了解Adobe Campaign - Microsoft Dynamics CRM整合，位於 [本頁](../connect/crm.md).

   使用 **[!UICONTROL Web API]** 部署類型和 **[!UICONTROL Password credentials]** 驗證時，您需要提供下列詳細資料：

   * **[!UICONTROL Account]**:用來登入Microsoft CRM的帳戶。

   * **[!UICONTROL Server]**:Microsoft CRM伺服器的URL。

   * **[!UICONTROL Client identifier]**:用戶端ID，可從以下位置的Microsoft Azure管理入口網站找到： **[!UICONTROL Update your code]** 類別， **[!UICONTROL Client ID]** 欄位。

   * **[!UICONTROL CRM version]**:CRM版本，介於 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**.
   使用 **[!UICONTROL Web API]** 部署類型和 **[!UICONTROL Certificate]** 驗證時，您需要提供下列詳細資料：

   * **[!UICONTROL Server]**:Microsoft CRM伺服器的URL。

   * **[!UICONTROL Private Key (Base64 encoded)]**:編碼為Base64的私鑰

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**:用戶端ID，可從以下位置的Microsoft Azure管理入口網站找到： **[!UICONTROL Update your code]** 類別， **[!UICONTROL Client ID]** 欄位。

   * **[!UICONTROL CRM version]**:CRM版本，介於 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   此 **[!UICONTROL Salesforce CRM]** 外部帳戶可讓您將Salesforce資料匯入和匯出至Adobe Campaign。

   若要設定Salesforce CRM外部帳戶以搭配Adobe Campaign運作，您需要提供下列詳細資訊：

   * **[!UICONTROL Account]**:用於登入Salesforce CRM的帳戶。

   * **[!UICONTROL Password]**:用於登入Salesforce CRM的密碼。

   * **[!UICONTROL Client identifier]**:了解如何在 [本頁](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**:了解如何在 [本頁](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**:選取API的版本。 對於此外部帳戶，您需要使用配置嚮導配置Salesforce CRM。

## 傳輸資料外部帳戶

這些外部帳戶可用來匯入或匯出資料至Adobe Campaign，使用 **[!UICONTROL Transfer file]** 工作流程活動。

![](../assets/do-not-localize/book.png) 進一步了解中的工作流程中的檔案傳輸 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP和SFTP**

   此 **FTP** 外部帳戶可讓您設定及測試對Adobe Campaign以外之伺服器的存取權。 若要設定與外部系統（例如用於檔案傳輸的SFTP或FTP伺服器898）的連線，您可以建立自己的外部帳戶。
若要這麼做，請在此外部帳戶中指定用來建立與SFTP或FTP伺服器連線的位址和憑證。

* **Amazon Simple Storage Service(S3)**

   此 **AWS S3** 連接器可用來匯入或匯出資料至Adobe Campaign，使用 **[!UICONTROL Transfer file]** 工作流程活動。 當您設定此新外部帳戶時，您必須提供下列詳細資訊：

   * **[!UICONTROL AWS S3 Account Server]**:伺服器的URL，填入如下：   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**:了解如何在 [Amazon檔案](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**:了解如何在中找到您的AWS秘密存取金鑰 [Amazon檔案](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**:進一步了解AWS地區： [Amazon檔案](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * 此 **[!UICONTROL Use server side encryption]** 核取方塊可讓您以S3加密模式儲存檔案。 了解如何在 [Amazon檔案](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Azure Blob儲存**

   此 **Azure** 外部帳戶可用來匯入或匯出資料至Adobe Campaign，使用 **[!UICONTROL Transfer file]** 工作流程活動。 若要設定 **Azure** 外部帳戶才能與Adobe Campaign搭配使用，您需要提供下列詳細資料：

   * **[!UICONTROL Server]**:Azure Blob儲存伺服器的URL。

   * **[!UICONTROL Encryption]**:之間的加密類型 **[!UICONTROL None]** 或 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**:了解如何找到您的 **[!UICONTROL Access key]** in [Microsoft檔案](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
