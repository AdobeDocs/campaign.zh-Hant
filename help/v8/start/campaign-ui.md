---
title: 探索 Campaign 使用者介面
description: 了解如何瀏覽及使用 Campaign 使用者介面
feature: Overview
role: User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 9d5a2ca1e9858a727377b8afa6bdd7e3761c1b56
workflow-type: ht
source-wordcount: '1072'
ht-degree: 100%

---

# 探索使用者介面 {#ui-client-console}

您可以透過其用戶端主控台或 Web 使用者介面存取 Adobe Campaign。您也可以使用 API 來管理資料，並在 Campaign 平台中執行工作。

>[!CAUTION]
>
>本文件著重於 Campaign 用戶端主控台使用情形。如果您使用 Campaign Web 使用者介面，請參閱[本文件](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=zh-Hant){target="_blank"}。

* **用戶端主控台** - Campaign 用戶端主控台是原生應用程式，可透過標準網際網路通訊協定 (例如 SOAP 和 HTTP) 與 Adobe Campaign 應用程式伺服器通訊。Campaign 用戶端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。Campaign 用戶端控制台旨在實現輕鬆部署，可從網路瀏覽器部署、可自動更新，且不需要任何特定網路設定，因為它只會產生 HTTP 流量。[了解更多](#ui-access)

  如需了解如何安裝和設定 Campaign 用戶端主控台，請參閱[本章節](../start/connect.md)。

* **Web 使用者介面** - 作為 Campaign v8 使用者，自 v8.6.1 版本起，您現在可以透過中央 Adobe Experience Cloud 使用者介面存取網頁環境。接著，您就可以從網頁瀏覽器連線至 Adobe Campaign。此新介面可讓您建立、管理及執行重要的行銷動作。不過，並非所有 Campaign 功能都可使用。[了解更多](#ac-web-ui)。

  >[!AVAILABILITY]
  >
  >Campaign Web 使用者介面僅適用於使用 Adobe ID 連線至 Adobe Campaign 的使用者。深入瞭解 [Adobe 身分管理系統 (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}。
  >

* **網頁存取** - Adobe Campaign 網頁存取功能可讓您使用 HTML 使用者介面，透過網頁瀏覽器存取 Campaign 功能的子集。使用此網頁介面存取報告、控制和驗證訊息、存取監控儀表板等。在[本章節](../start/connect.md#web-access)中進一步瞭解 Campaign Web Access。

* **API** - 若要解決更多使用案例，可使用透過 SOAP 通訊協定公開的網頁服務 API，從外部應用程式呼叫系統。在[本頁面](../dev/api.md)中進一步瞭解 Campaign API。


## 使用用戶端主控台 {#ui-access}

Campaign 用戶端主控台是原生應用程式，可透過標準網際網路通訊協定 (例如 SOAP 和 HTTP) 與 Adobe Campaign 應用程式伺服器通訊。Campaign 用戶端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。Campaign 用戶端控制台旨在實現輕鬆部署，可從網路瀏覽器部署、可自動更新，且不需要任何特定網路設定，因為它只會產生 HTTP 流量。[進一步瞭解 Campaign 用戶端主控台](../start/connect.md)。您可以從用戶端主控台首頁的專用卡片切換至 Campaign Web 使用者介面。

![](assets/web-ui.png)


>[!NOTE]
>
>如果未顯示新的存取卡片，請確定在您的 Adobe Experience Cloud 外部帳戶中，下列欄位不是空的：**伺服器**、**租用戶**、**回呼伺服器**&#x200B;以及&#x200B;**關聯標籤**。


您也可以使用網頁瀏覽器來存取 Campaign。在這種情況下，僅可使用 Campaign 功能的子集。[了解更多](#web-browser)

### 瀏覽介面 {#ui-browse}

連線至 Campaign 用戶端主控台後，即可存取首頁。瀏覽連結以存取功能。介面中可用的功能集取決於您的選項和權限。

在首頁的中央，請透過連結存取 Campaign 說明材料、社群及支援網站。使用中央卡片來瀏覽新的 Campaign Web 使用者介面和 Campaign 控制面板。

瀏覽上半區段中的索引標籤，以存取 Campaign 主要功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可存取的核心功能清單取決於您的權限和實施。

對於每個功能，您都可以存取 **[!UICONTROL Browsing]** 區段中的一組主要功能。**[!UICONTROL More]** 連結可讓您存取所有其他元件。

例如，瀏覽至 **[!UICONTROL Profiles and targets]** 索引標籤時，您可以存取收件者清單、訂閱服務、現有的目標工作流程，以及建立所有這些元件的捷徑。

![](assets/overview-list.png)

當您在畫面中選取元素時，該元素會載入新的索引標籤中，以便您輕鬆瀏覽內容。

![](assets/new-tab.png)

### 建立新元素 {#create-an-element}

使用畫面左側 **[!UICONTROL Create]** 區段中的捷徑來新增元素。使用清單上方的 **[!UICONTROL Create]** 按鈕，將新元素新增至目前的清單中。

例如，在傳遞頁面上，使用 **[!UICONTROL Create]** 按鈕來建立新的傳遞。

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### 存取 Campaign Explorer {#ac-explorer-ui}

瀏覽 Campaign Explorer 以存取所有 Adobe Campaign 功能和設定。

![](assets/explorer.png)

此工作區可讓您存取 Explorer 樹狀結構以瀏覽所有功能和選項。

* 左側區段顯示 Campaign Explorer 樹狀結構，並讓您根據權限瀏覽執行個體的所有元件和設定。您可以新增和自訂資料夾，如[此頁面](../audiences/folders-and-views.md)中所述。

* 上半部分顯示目前資料夾中的記錄清單。這些清單皆可完全自訂。[了解更多](../config/ui-settings.md)

* 下半區段會顯示所選記錄的詳細資訊。


## Campaign Web 使用者介面 {#ac-web-ui}

作為 Campaign v8 用戶端主控台使用者，自 v8.6.1 版本起，您現在可以透過中央 Adobe Experience Cloud 使用者介面存取網頁環境。Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。

![Adobe Campaign Web 使用者介面首頁](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>Campaign Web 使用者介面僅適用於使用 Adobe ID 連線至 Adobe Campaign 的使用者。深入瞭解 [Adobe 身分管理系統 (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}。
>

在[此文件](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=zh-Hant){target="_blank"}中，深入了解新的 Campaign Web 使用者介面。您也可以在 Campaign Web 使用者介面文件中瀏覽專屬的[常見問題集頁面](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/faq){target="_blank"}。

其他和進階功能、組態和設定只能在用戶端主控台中取得。在 [Campaign Web 使用者介面文件](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=zh-Hant){target="_blank"}中進一步瞭解兩種使用者介面中可用的功能。


## 支援的語言 {#languages}

支援的語言取決於使用者介面。

* 對於 Campaign v8 用戶端主控台介面，支援的語言為：

   * 英文 (英國)
   * 英文 (美國)
   * 法文
   * 德文
   * 日文


  >[!CAUTION]
  >
  >語言是在安裝過程中選取的，之後無法變更。

* 對於 Campaign Web 使用者介面支援的語言，[請參考此頁面](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html?lang=zh-Hant#language-pref){target="_blank"}。


語言會影響日期和時間格式。

英文 (US) 和英文 (EN) 的主要差異如下：

<table> 
 <thead> 
  <tr> 
   <th> 格式<br /> </th> 
   <th> 英文 (US)<br /> </th> 
   <th> 英文 (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 日期<br /> </td> 
   <td> 一週開始於星期日<br /> </td> 
   <td> 一週開始於星期一<br /> </td> 
  </tr> 
  <tr> 
   <td> 簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>範例：09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>範例：25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 帶時間的簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>例如：2018 年 9 月 25 日晚上 10:47:25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>例如：2018 年 9 月 25 日 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
