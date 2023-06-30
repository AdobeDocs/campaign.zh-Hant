---
title: 連線至Campaign v8
description: 了解如何連接到 Adobe Campaign v8 並在您的機器上安裝主控台以易於存取。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 8%

---

# 連線至Adobe Campaign v8{#gs-ac-connect}

若要開始使用Campaign，您必須安裝並設定使用者端主控台。

使用者端主控台是原生應用程式，可透過標準網際網路通訊協定（例如SOAP和HTTP）與Adobe Campaign應用程式伺服器通訊。 Campaign使用者端主控台可集中所有功能和設定，且需要最少的頻寬，因為它需仰賴本機快取。 Campaign使用者端主控台專為輕鬆部署而設計，可從網際網路瀏覽器部署、自動更新，且不需要任何特定網路設定，因為它只會產生HTTP(S)流量。

開始之前，您需要：

* 在中檢查您的系統和工具與Adobe Campaign的相容性 [相容性矩陣](compatibility-matrix.md)
* 取得您的Campaign伺服器URL
* 建立您的Adobe ID，或從您的公司取得使用者認證
* 在您的系統上安裝Microsoft Edge Webview2執行階段。 [了解更多](#webview)

## 安裝使用者端主控台{#download-ac-console}

### Microsoft Edge Webview2執行階段 {#webview}

從Campaign Classic8.4建置版本，任何使用者端主控台安裝都需要安裝Microsoft Edge Webview 2執行階段。

Web View預設會安裝為Windows 11作業系統的一部分。 如果您的系統尚未安裝該應用程式，Campaign使用者端主控台安裝程式會提示您從下載 [Microsoft開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}. 請注意，下載連結在Internet Explorer 11瀏覽器上無法運作，因為Microsoft已停止支援。 請確定您使用不同的瀏覽器來存取連結。

### 下載主控台{#install-ac-console}

第一次使用Campaign時，您需要下載並安裝使用者端主控台。

有兩個選項可用來下載使用者端主控台：

1. 身為Campaign管理員，請連線至Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. 身為一般使用者，您的Campaign管理員會為您部署使用者端主控台，並透過專用的URL提供使用。

下載Client Console安裝程式後，請將其安裝在您的本機電腦上。

請注意，使用者端主控台語言安裝後即無法變更。

## 建立您的連線{#create-your-connection}

安裝使用者端主控台後，請依照下列步驟建立與應用程式伺服器的連線：

1. 啟動Console並瀏覽右上角的連結以存取連線設定畫面。

1. 按一下 **[!UICONTROL Add > Connection]** 並輸入Adobe Campaign應用程式伺服器的標籤和URL。

1. 透過URL指定與您的Adobe Campaign應用程式伺服器的連線。 使用電腦的DNS或別名，或您的IP位址。

   例如，您可以使用 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 輸入URL。

1. 核取選項 **[!UICONTROL Connect with an Adobe ID]**.

1. 按一下 **[!UICONTROL Ok]** 以儲存您的設定。

例如，您可以視需要新增許多連線，以連線至您的測試、中繼和生產環境。

>[!NOTE]
>
>此 **[!UICONTROL Add]** 按鈕可讓您建立 **[!UICONTROL folders]** 以組織所有連線。 只需將每個連線拖放到資料夾中即可。

## 登入Adobe Campaign {#logon-to-ac}

Campaign使用者透過AdobeAdobe Campaign System (IMS)，使用其Adobe ID連線至Identity Management主控台。 他們可以使用相同的ID所有Adobe解決方案。 將Adobe Campaign與其他解決方案搭配使用時，會儲存連線。 進一步瞭解Adobe IMS，請參閱 [此頁面](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

若要登入執行個體，請遵循下列步驟：

1. 啟動Console並瀏覽右上角的連結以存取連線設定畫面。

   ![](assets/connectToCampaign.png)

1. 選取您需要登入的Campaign執行個體。

1. 按一下&#x200B;**[!UICONTROL Ok]**。

接著，您可以使用Adobe ID登入Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由於Microsoft Edge Webview2不會儲存Proxy認證，所以主控台可能會要求您在第一次連線時驗證兩次。

## 升級您的使用者端主控台{#upgrade-ac-console}

當您的系統升級至較新版本時，您必須將使用者端主控台更新至相同版本。 此為最佳實務，且對於某些版本而言，此升級為強制性。 在此情況下，它會在以下連結中提及： [發行說明](release-notes.md).

Adobe身為Managed Cloud Services使用者，為您部署使用者端主控台。 當您連線到升級後的環境時，系統會提示您從快顯視窗中下載最新的使用者端主控台版本。 您必須接受此升級，並根據要求更新使用者端主控台。

>[!CAUTION]
>
>Adobe建議保留選項 **[!UICONTROL No longer ask this question]** 取消選取，以確保有新版的Console可用時收到警報。 如果選取此選項，則不會通知使用者需要升級Console。
>



## 授予使用者存取許可權{#grant-access}

Adobe Campaign可讓您定義和管理指派給各種運運算元的許可權。

身為Campaign管理員，您負責建立操作員並與使用者共用其認證。

進一步瞭解使用者以及如何在中定義其許可權 [本節](gs-permissions.md).


## 網路存取{#web-access}

使用HTML使用者介面，可以透過網頁瀏覽器存取應用程式的某些部分：報告、傳遞核准、執行個體監控等。

網路存取介面與主控台的介面類似，但是功能有所減少。

例如，對於指定的運運算元，行銷活動會在主控台中顯示以下選項：

![](assets/campaign-from-console.png)

而網路存取介面上，主要啟用檢視選項：

![](assets/campaign-from-web.png)

網路存取也用於驗證程式：操作員可以按一下核准請求電子郵件，並透過其網頁瀏覽器連線至Campaign，以驗證或拒絕傳遞內容或預算。

若要從網頁存取您的Campaign執行個體，URL為：  `https://<your adobe campaign server>:<port number>/view/home`.
