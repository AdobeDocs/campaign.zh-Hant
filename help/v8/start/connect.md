---
title: 連線至Campaign v8
description: 了解如何連接到 Adobe Campaign v8 並在您的機器上安裝主控台以易於存取。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 7f27dbdd0ff53cd7437f956ccfef3d792020893b
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 8%

---

# 連線至Adobe Campaign v8{#gs-ac-connect}

若要開始使用Campaign，您必須安裝並設定用戶端主控台。

用戶端主控台是原生應用程式，可透過標準網際網路通訊協定（例如SOAP和HTTP）與Adobe Campaign應用程式伺服器通訊。 Campaign用戶端主控台會集中所有功能和設定，因需最低頻寬，因為它需仰賴本機快取。 Campaign用戶端主控台可從網際網路瀏覽器部署，且可自動更新，且不需要任何特定的網路設定，因為它只會產生HTTP(S)流量。

開始之前，您需要：

* 在 [相容性矩陣](compatibility-matrix.md)
* 取得您的Campaign伺服器URL
* 建立Adobe ID，或從公司取得使用者認證
* 在您的系統上安裝Microsoft Edge Webview2執行階段。 [了解更多](#webview)

## 安裝客戶端控制台{#download-ac-console}

### Microsoft Edge Webview2執行階段 {#webview}

從Campaign Classic8.4版本建置版本，安裝任何用戶端主控台都需要安裝Microsoft Edge Webview 2執行階段。

預設情況下，Web視圖是Windows 11作業系統的一部分。 如果系統上尚未出現，Campaign用戶端主控台安裝程式會提示您從下載 [Microsoft開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}. 請注意，下載連結在Internet Explorer 11瀏覽器上無法運作，因為Microsoft已不再支援。 請確定您使用不同的瀏覽器來存取連結。

### 下載主控台{#install-ac-console}

第一次使用Campaign時，您需要下載用戶端主控台並加以安裝。

下載用戶端主控台有兩個選項：

1. 身為Campaign管理員，請連線至Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. 身為一般使用者，您的Campaign管理員會為您部署用戶端主控台，並透過專用URL使用。

下載客戶端控制台安裝程式後，將其安裝在本地電腦上。

請注意，在安裝客戶端控制台語言後，您就無法更改該語言。

## 建立連線{#create-your-connection}

安裝客戶端控制台後，請按照以下步驟建立與應用程式伺服器的連接：

1. 啟動Console並瀏覽右角的連結以存取連線設定畫面。

1. 按一下 **[!UICONTROL Add > Connection]** 並輸入Adobe Campaign應用程式伺服器的標籤和URL。

1. 透過URL指定與Adobe Campaign應用程式伺服器的連線。 使用電腦的DNS、別名或IP地址。

   例如，您可以使用 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 類型URL。

1. 核取選項 **[!UICONTROL Connect with an Adobe ID]**.

1. 按一下 **[!UICONTROL Ok]** 來儲存設定。

例如，您可以視需要新增連線，以連線至您的測試、預備和生產環境。

>[!NOTE]
>
>此 **[!UICONTROL Add]** 按鈕可讓您建立 **[!UICONTROL folders]** 來組織所有連線。 只需將每個連線拖放到資料夾中即可。

## 登入Adobe Campaign {#logon-to-ac}

Campaign使用者使用其Adobe ID，透過AdobeIdentity Management系統(IMS)連線至Adobe Campaign主控台。 所有Adobe解決方案都可使用相同的ID。 將Adobe Campaign與其他解決方案搭配使用時，會儲存連線。 深入了解Adobe IMS，位於 [本頁](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

若要登入執行個體，請遵循下列步驟：

1. 啟動Console並瀏覽右角的連結以存取連線設定畫面。

   ![](assets/connectToCampaign.png)

1. 選取您需要登入的Campaign執行個體。

1. 按一下&#x200B;**[!UICONTROL Ok]**。

然後，您可以使用Adobe ID登入Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由於Microsoft Edge Webview2不會儲存代理憑證，因此主控台可能會要求您在第一個連線時執行兩次驗證。

## 升級您的客戶端控制台{#upgrade-ac-console}

當您的系統升級到較新版本時，您必須將用戶端主控台更新為相同版本。 這是最佳實務，對於某些版本，此升級為強制性。 在此情況下， [發行說明](release-notes.md).

作為「受管理的Cloud Services」用戶，Adobe會為您部署客戶端控制台。 當您連接到升級環境時，系統會提示您在彈出窗口中下載最新的客戶端控制台版本。 您必須接受此升級，並根據要求更新客戶端控制台。

>[!CAUTION]
>
>Adobe建議保留選項 **[!UICONTROL No longer ask this question]** 未選取，以確保在有新版本的Console可用時收到警報。 如果選取此選項，系統不會通知使用者需要進行主控台升級。


## 授予使用者存取權{#grant-access}

Adobe Campaign可讓您定義及管理指派給各種運算子的權限。

身為Campaign管理員，您負責建立運算子，並與使用者共用其認證。

進一步了解使用者，以及如何在 [本節](gs-permissions.md).


## 網路存取{#web-access}

應用程式的某些部分可通過Web瀏覽器使用HTML用戶介面進行訪問：報告、傳送核准、執行個體監控等。

網路存取介面與主控台的介面類似，但是功能有所減少。

例如，對於指定運算子，促銷活動在主控台中會顯示下列選項：

![](assets/campaign-from-console.png)

而網路存取介面上，主要啟用檢視選項：

![](assets/campaign-from-web.png)

驗證程式中也會使用Web存取：運算子可以按一下核准請求電子郵件，並透過其網頁瀏覽器連線至Campaign，以驗證或拒絕傳送內容或預算。

若要從網路存取您的Campaign執行個體，URL為：  `https://<your adobe campaign server>:<port number>/view/home`.
