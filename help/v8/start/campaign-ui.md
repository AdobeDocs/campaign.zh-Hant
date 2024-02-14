---
title: 探索Campaign使用者介面
description: 瞭解如何瀏覽及使用Campaign使用者介面
feature: Overview
role: User
level: Beginner
source-git-commit: 8666c04f0e98cd6444af831d47056c46019c6088
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 6%

---

# 探索使用者介面 {#ui-client-console}

您可以透過其使用者端主控台或網頁使用者介面存取Adobe Campaign。 您也可以使用API來管理資料，並在Campaign平台中執行工作。

>[!CAUTION]
>
>本檔案著重於Campaign使用者端主控台使用情形。 如果您使用Campaign Web使用者介面，請參閱 [本檔案](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.

* **使用者端主控台** - Campaign使用者端主控台是原生應用程式，可透過標準網際網路通訊協定（例如SOAP和HTTP）與Adobe Campaign應用程式伺服器通訊。 Campaign使用者端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。 Campaign使用者端主控台專為輕鬆部署而設計，可從網際網路瀏覽器部署、自動更新，且不需要任何特定網路設定，因為它只會產生HTTP(S)流量。 [了解更多](#ui-access)

  瞭解如何在中安裝和設定Campaign使用者端主控台 [本節](../start/connect.md).

<!--    ![](assets/home-page.png) -->

* **網頁使用者介面**  — 自8.6.1版開始，身為Campaign v8使用者，您現在可以透過Adobe Experience Cloud中央使用者介面存取網路環境。 接著，您就可以從網頁瀏覽器連線至Adobe Campaign。 此新介面可讓您建立、管理及執行重要的行銷動作。 不過，並非所有Campaign功能都可使用。 [了解更多](#ac-web-ui)。

  Campaign Campaign網頁使用者介面可透過使用者端主控台首頁取得。

  ![](assets/web-ui.png)

  >[!NOTE]
  >
  >如果未顯示新的存取卡，請確定Adobe Experience Cloud外部帳戶中的下列欄位不會留空： **伺服器**， **租使用者**， **回呼伺服器**、和 **關聯標籤**.

* **網頁存取** - Adobe Campaign網頁存取功能可讓您使用HTML使用者介面，透過網頁瀏覽器存取Campaign功能的子集。 使用此Web介面存取報告、控制和驗證訊息、存取監控儀表板等。  進一步瞭解Campaign網頁存取 [在本節中](../start/connect.md#web-access).

* **API**  — 為了解決更多使用案例，可使用透過SOAP通訊協定公開的網站服務API，從外部應用程式呼叫系統。 進一步瞭解Campaign API [在此頁面中](../dev/api.md).


## 使用使用者端主控台 {#ui-access}

Campaign使用者端主控台是原生應用程式，可透過標準網際網路通訊協定（例如SOAP和HTTP）與Adobe Campaign應用程式伺服器通訊。 Campaign使用者端主控台會集中所有功能和設定，且需要最少的頻寬，因為它依賴本機快取。 Campaign使用者端主控台專為輕鬆部署而設計，可從網際網路瀏覽器部署、自動更新，且不需要任何特定網路設定，因為它只會產生HTTP(S)流量。  [深入瞭解Campaign使用者端主控台](../start/connect.md).

![](assets/home-page.png)

您也可以使用網頁瀏覽器來存取Campaign。 在這種情況下，僅可使用Campaign功能的子集。 [了解更多](#web-browser)

### 瀏覽介面 {#ui-browse}

連線至Campaign使用者端主控台後，即可存取首頁。 瀏覽連結以存取功能。 介面中可用的功能集取決於您的選項和許可權。

從首頁的中央區段，使用連結來存取Campaign說明教材、社群和支援網站。 使用中央卡片來瀏覽新的Campaign Web使用者介面和Campaign控制面板。

瀏覽上方區段中的標籤，以存取Campaign主要功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可存取的核心功能清單取決於您的許可權和實施。

對於每個功能，您都可以存取 **[!UICONTROL Browsing]** 區段。 此 **[!UICONTROL More]** 連結可讓您存取所有其他元件。

例如，瀏覽至 **[!UICONTROL Profiles and targets]** 索引標籤中，您可以存取收件者清單、訂閱服務、現有的鎖定目標工作流程，以及建立所有這些元件的捷徑。

![](assets/overview-list.png)

當您在畫面中選取元素時，該元素會載入新的索引標籤中，以便您輕鬆瀏覽內容。

![](assets/new-tab.png)

### 建立元素 {#create-an-element}

在下列專案中使用捷徑： **[!UICONTROL Create]** 區段來新增元素。 您也可以使用 **[!UICONTROL Create]** 按鈕來將新元素新增至目前清單。

例如，在傳送頁面上，使用 **[!UICONTROL Create]** 按鈕以建立新傳遞。

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

![](../assets/do-not-localize/glass.png) [Learn more about Campaign web access](../start/connect.md#web-access).-->

### 存取Campaign總管 {#ac-explorer-ui}

瀏覽Campaign Explorer以存取所有Adobe Campaign功能和設定。

![](assets/explorer.png)

此工作區可讓您存取瀏覽器樹狀結構以瀏覽所有功能和選項。

* 左側區段顯示Campaign Explorer樹狀結構，並讓您根據許可權瀏覽執行個體的所有元件和設定。 您可以新增及自訂資料夾，如中所述 [此頁面](../audiences/folders-and-views.md).

* 上半部分顯示目前資料夾中的記錄清單。 這些清單皆可完全自訂。 [了解更多](../config/ui-settings.md)

* 下方區段會顯示所選記錄的詳細資訊。


## Campaign Web使用者介面 {#ac-web-ui}

自8.6.1版開始，身為Campaign v8使用者端主控台使用者，您現在可以透過Adobe Experience Cloud中央使用者介面存取網頁環境。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。透過其直覺式介面，您可以快速存取您的雲端應用程式、產品功能和服務。

![Adobe Campaign Web使用者介面首頁](assets/ac-web-home.png)

進一步瞭解中的全新Campaign網頁使用者介面 [本檔案](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.

其他和進階功能、組態和設定只能在使用者端主控台中使用。 進一步瞭解這兩個使用者介面中可用的功能 [（在Campaign Web使用者介面檔案中）](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html){target="_blank"}.


## 支援的語言 {#languages}

支援的語言取決於使用者介面。

* 對於Campaign v8使用者端主控台介面，支援的語言為：

   * 英文 (英國)
   * 英文 (美國)
   * 法文
   * 德文
   * 日文


  >[!CAUTION]
  >
  >語言是在安裝過程中選取的，之後無法變更。

* 對於Campaign Web使用者介面支援的語言， [請參閱此頁面](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html#language-pref){target="_blank"}.


語言會影響日期和時間格式。

英文 (US) 和英文 (EN) 的主要差異如下：

<table> 
 <thead> 
  <tr> 
   <th> 格式<br /> </th> 
   <th> 英文（美國）<br /> </th> 
   <th> 英文(EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 日期<br /> </td> 
   <td> 周從星期日開始<br /> </td> 
   <td> 一週從星期一開始<br /> </td> 
  </tr> 
  <tr> 
   <td> 簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>範例：09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>範例：25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 具有時間的簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>例如： 2018年9月25日10:47:下午25點</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>例如： 2018年9月25日22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
