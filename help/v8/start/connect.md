---
title: 連線至 Campaign v8
description: 了解如何連線至 Adobe Campaign v8 並在您的機器上安裝主控台以便於存取。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: ht
source-wordcount: '1006'
ht-degree: 100%

---

# 連線至 Adobe Campaign v8{#gs-ac-connect}

若要開始使用 Campaign，您必須安裝並設定用戶端主控台。

用戶端主控台是原生應用程式，可透過標準網際網路通訊協定 (例如 SOAP 和 HTTP) 與 Adobe Campaign 應用程式伺服器通訊。Campaign 用戶端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。Campaign 用戶端控制台旨在實現輕鬆部署，可從網路瀏覽器部署、可自動更新，且不需要任何特定網路設定，因為它只會產生 HTTP 流量。

開始之前，您需要：

* 在[相容性矩陣](compatibility-matrix.md)中檢查您的系統和工具與 Adobe Campaign 的相容性
* 取得 Campaign 伺服器 URL
* 建立您的 Adobe ID，或從您的公司取得使用者認證
* 在您的系統上安裝 Microsoft Edge Webview2 執行階段。[了解更多](#webview)

## 安裝用戶端主控台{#download-ac-console}

### Microsoft Edge Webview2 執行階段 {#webview}

從 Campaign Classic 8.4 建置版本開始，任何用戶端主控台安裝都需要安裝 Microsoft Edge Webview 2 執行階段。

Web View 預設會安裝為 Windows 11 作業系統的一部分。如果您的系統上尚未有該檔案，Campaign 用戶端主控台安裝程式會提示您從 [Microsoft 開發人員網站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_tw){target="_blank"}下載該檔案。請注意，下載連結在 Internet Explorer 11 瀏覽器上無法運作，因為 Microsoft 已停止支援。請確定您使用不同的瀏覽器來存取連結。

### 下載主控台{#install-ac-console}

第一次使用 Campaign 時，您需要下載並安裝用戶端主控台。

下載用戶端主控台有兩個選項：

1. 以 Campaign 管理員身分，連線至 Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/tw/campaign.html){target="_blank"}。

1. 身為一般使用者，您的 Campaign 管理員會為您部署用戶端主控台，並透過專用的 URL 供您使用。

下載用戶端主控台安裝程式後，請將其安裝在您的本機電腦上。

請注意，用戶端主控台安裝後，您就無法變更其語言。

## 建立連線{#create-your-connection}

安裝用戶端主控台後，請依照下列步驟建立與應用程式伺服器的連線：

1. 啟動主控台並瀏覽右上角的連結，以存取連線設定畫面。

1. 按一下 **[!UICONTROL Add > Connection]** 並輸入 Adobe Campaign 應用程式伺服器的標籤和 URL。

1. 指定透過 URL 連線至您的 Adobe Campaign 應用程式伺服器。請使用電腦的 DNS 或別名，或您的 IP 位址。

   例如，您可以使用 `https://<machine>.<domain>.com` 類型 URL。

1. 核取 **[!UICONTROL Connect with an Adobe ID]** 選項。

1. 按一下 **[!UICONTROL Ok]** 以儲存您的設定。

例如，您可以視需要新增許多連線，以連線至您的測試、階段和生產環境。

>[!NOTE]
>
>使用 **[!UICONTROL Add]** 按鈕，您可以建立 **[!UICONTROL folders]** 來管理所有連線。只需將每個連線拖放到資料夾中即可。

## 登入 Adobe Campaign {#logon-to-ac}

Campaign 使用者透過 Adobe 身分管理系統 (IMS)，使用其 Adobe ID 連線至 Adobe Campaign 主控台。他們可以在所有 Adobe 解決方案中使用相同的 ID。搭配其他解決方案使用 Adobe Campaign 時，可以儲存連線。在[此頁面](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}了解更多關於 Adobe IMS 的資訊。

若要登入執行個體，請遵循下列步驟：

1. 啟動主控台並瀏覽右上角的連結，以存取連線設定畫面。

   ![](assets/connectToCampaign.png)

1. 選取您需要登入的 Campaign 執行個體。

1. 按一下 **[!UICONTROL Ok]**。

接著，您可以使用您的 Adobe ID 登入 Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由於 Microsoft Edge Webview2 不會儲存 Proxy 認證，所以主控台可能會要求您在第一次連線時驗證兩次。

## 升級用戶端主控台{#upgrade-ac-console}

當您的系統升級至較新版本時，您必須將用戶端主控台更新至相同版本。此為最佳做法，且對於某些版本，此升級為強制性。在這種情況下，[發行說明](release-notes.md)中會提及這一點。

作為 Managed Cloud Services 使用者，Adobe 會為您部署用戶端主控台。當您連線到升級後的環境時，系統會提示您從快顯視窗中下載最新的用戶端主控台版本。您必須接受此升級，並根據要求更新用戶端主控台。

>[!CAUTION]
>
>Adobe 建議取消選取 **[!UICONTROL No longer ask this question]** 選項，以確保在新版本的主控台可用時通知您。如果選取此選項，則不會通知使用者需要升級主控台。
>



## 向使用者授予存取權{#grant-access}

Adobe Campaign 可讓您定義並管理指派給各個操作者的權限。

身為 Campaign 管理員，您必須負責建立操作者，並與使用者共用其認證。

在[本節](gs-permissions.md)中進一步了解使用者以及如何定義其權限。


## 使用網頁瀏覽器存取 Campaign {#connect-web-ac}

### Web 使用者介面 {#connect-web-ui}

自 Campaign v8.6 版本起，您可存取可透過中央 Adobe Experience Cloud 環境使用的新的 **Campaign Web 使用者介面**。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。

>[!AVAILABILITY]
>
>Campaign Web 使用者介面僅適用於使用 Adobe ID 連線至 Adobe Campaign 的使用者。深入瞭解 [Adobe 身分管理系統 (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}。
>

[在此頁面中](campaign-ui.md#ac-web-ui)了解如何連線至 Adobe Experience Cloud，以及存取 Adobe Campaign Web 介面。

在 [Adobe Campaign Web 使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}之中瞭解更多資訊。

### 網路存取 {#web-access}

您可以透過 HTML 使用者介面的網頁瀏覽器，存取應用程式的某些部分：報告、傳遞核准、執行個體監視等。

網路存取介面與主控台的介面類似，但是功能有所減少。

例如，針對指定的操作者，在主控台中將顯示下列行銷活動選項：

![](assets/campaign-from-console.png)

而網路存取介面上，主要啟用檢視選項：

![](assets/campaign-from-web.png)

網頁存取也用於驗證程序：操作員可以按一下核准請求電子郵件，並透過其網頁瀏覽器連線至 Campaign，以驗證或拒絕傳遞內容或預算。

若要從網頁存取您的 Campaign 執行個體，URL 為：`https://<your adobe campaign server>:<port number>/view/home`。
