---
title: 連線至Campaign v8
description: 了解如何連接到 Adobe Campaign v8 並在您的機器上安裝主控台以易於存取。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 13%

---

# 連線至Adobe Campaign v8{#gs-ac-connect}

若要開始使用Campaign，您必須安裝並設定使用者端主控台。

使用者端主控台是原生應用程式，可透過標準網際網路通訊協定(例如SOAP和HTTP)與Adobe Campaign應用程式伺服器通訊。 Campaign使用者端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。 Campaign使用者端主控台專為輕鬆部署而設計，可從網際網路瀏覽器部署、自動更新，且不需要任何特定網路設定，因為它只會產生HTTP(S)流量。

開始之前，您需要：

* 在[相容性矩陣](compatibility-matrix.md)中檢查您的系統與工具與Adobe Campaign的相容性
* 取得您的Campaign伺服器URL
* 建立您的Adobe ID，或從您的公司取得使用者認證
* 在您的系統上安裝Microsoft Edge Webview2執行階段。 [了解更多](#webview)

## 安裝使用者端主控台{#download-ac-console}

### Microsoft Edge Webview2執行階段 {#webview}

從Campaign Classic 8.4建置版本開始，任何使用者端主控台安裝都需要安裝Microsoft Edge Webview 2執行階段。

Web View預設會安裝為Windows 11作業系統的一部分。 如果您的系統上尚未有該檔案，Campaign使用者端主控台安裝程式會提示您從[Microsoft開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}下載該檔案。 請注意，下載連結在Internet Explorer 11瀏覽器上無法運作，因為Microsoft已停止支援。 請確定您使用不同的瀏覽器來存取連結。

### 下載主控台{#install-ac-console}

第一次使用Campaign時，您需要下載並安裝使用者端主控台。

下載使用者端主控台有兩個選項：

1. 以Campaign管理員身分，連線至Adobe [軟體發佈](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}。

1. 身為一般使用者，您的Campaign管理員會為您部署使用者端主控台，並透過專用的URL提供使用。

下載Client Console安裝程式後，請將其安裝在您的本機電腦上。

請注意，使用者端主控台語言安裝後，您就無法變更。

## 建立您的連線{#create-your-connection}

安裝「使用者端主控台」後，請依照下列步驟建立與應用程式伺服器的連線：

1. 啟動Console並瀏覽右上角的連結以存取連線設定畫面。

1. 按一下&#x200B;**[!UICONTROL Add > Connection]**&#x200B;並輸入Adobe Campaign應用程式伺服器的標籤和URL。

1. 指定透過URL連線至您的Adobe Campaign應用程式伺服器。 請使用電腦的DNS或別名，或您的IP位址。

   例如，您可以使用`https://<machine>.<domain>.com`型別URL。

1. 核取選項&#x200B;**[!UICONTROL Connect with an Adobe ID]**。

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;儲存您的設定。

例如，您可以視需要新增許多連線，以連線至您的測試、中繼和生產環境。

>[!NOTE]
>
>「**[!UICONTROL Add]**」按鈕可讓您建立&#x200B;**[!UICONTROL folders]**&#x200B;以組織所有連線。 只需將每個連線拖放到資料夾中即可。

## 登入Adobe Campaign {#logon-to-ac}

Campaign使用者透過Adobe Campaign Identity Management System (IMS)，使用其Adobe ID連線至Adobe主控台。 他們可以在所有Adobe解決方案中使用相同的ID。 將Adobe Campaign與其他解決方案搭配使用時，會儲存連線。 在[此頁面](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}中進一步瞭解Adobe IMS。

若要登入執行個體，請遵循下列步驟：

1. 啟動Console並瀏覽右上角的連結以存取連線設定畫面。

   ![](assets/connectToCampaign.png)

1. 選取您需要登入的Campaign執行個體。

1. 按一下&#x200B;**[!UICONTROL Ok]**。

接著，您可以使用您的Adobe ID登入Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由於Microsoft Edge Webview2不會儲存Proxy認證，所以主控台可能會要求您在第一次連線時驗證兩次。

## 升級您的使用者端主控台{#upgrade-ac-console}

當您的系統升級至較新版本時，您必須將使用者端主控台更新至相同版本。 此為最佳實務，且對於某些版本，此升級為強制性。 在這種情況下，[發行說明](release-notes.md)中會提及它。

作為「受管理的Cloud Services」使用者，Adobe會為您部署使用者端主控台。 當您連線到升級後的環境時，系統會提示您從快顯視窗中下載最新的使用者端主控台版本。 您必須接受此升級，並根據要求更新使用者端主控台。

>[!CAUTION]
>
>Adobe建議取消選取選項&#x200B;**[!UICONTROL No longer ask this question]**，以確保在新版本的主控台可用時通知您。 如果選取此選項，則不會通知使用者需要升級Console。
>



## 授予使用者存取許可權{#grant-access}

Adobe Campaign可讓您定義並管理指派給各種運運算元的許可權。

身為Campaign管理員，您必須負責建立操作者，並與使用者共用其認證。

在[本節](gs-permissions.md)中進一步瞭解使用者以及如何定義其許可權。


## 使用網頁瀏覽器存取Campaign {#connect-web-ac}

### 網頁使用者介面 {#connect-web-ui}

自 Campaign v8.6 版本起，您可存取可透過中央 Adobe Experience Cloud 環境使用的新的 **Campaign Web 使用者介面**。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。

>[!AVAILABILITY]
>
>Campaign Web使用者介面僅適用於使用Adobe ID連線至Adobe Campaign的使用者。 深入瞭解[Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}。
>

[在此頁面中](campaign-ui.md#ac-web-ui)了解如何連線至 Adobe Experience Cloud，以及存取 Adobe Campaign Web 介面。

在[Adobe Campaign Web使用者介面檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/campaign-web-home){target="_blank"}中進一步瞭解。

### 網路存取 {#web-access}

您可以透過HTML使用者介面的網頁瀏覽器，存取應用程式的某些部分：報告、傳遞核准、執行個體監控等。

網路存取介面與主控台的介面類似，但是功能有所減少。

例如，對於指定的運運算元，行銷活動會在主控台中顯示以下選項：

![](assets/campaign-from-console.png)

而網路存取介面上，主要啟用檢視選項：

![](assets/campaign-from-web.png)

Web存取也用於驗證程式：操作員可以按一下核准請求電子郵件，並透過其網頁瀏覽器連線至Campaign，以驗證或拒絕傳遞內容或預算。

若要從網頁存取您的Campaign執行個體，URL為： `https://<your adobe campaign server>:<port number>/view/home`。
