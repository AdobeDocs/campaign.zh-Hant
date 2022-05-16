---
title: 連接到市場活動v8
description: 了解如何連線至 Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 8%

---

# 連接到Adobe Campaignv8{#gs-ac-connect}

市場活動客戶端控制台是一個富客戶端，它使您能夠連接到市場活動應用程式伺服器。

在開始之前，您需要：

* 檢查您的系統和工具與Adobe Campaign的相容性 [相容性矩陣](compatibility-matrix.md)
* 獲取您的市場活動伺服器URL
* 建立您的Adobe ID或從您的公司獲取您的用戶憑據

## 下載並安裝客戶端控制台{#download-ac-console}

首次使用市場活動時，或者如果需要升級到較新版本，則需要下載客戶端控制台並安裝它。

有兩個選項：

1. 作為市場活動管理員，連接到Adobe [軟體分發](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) 並下載客戶端控制台安裝程式。 然後，可以將其安裝到本地電腦上。

1. 作為最終用戶，Adobe可以為您部署控制台：更新控制台後，系統將提示您在彈出窗口中下載最新的客戶端控制台版本。

>[!CAUTION]
>
>Adobe建議保留 **[!UICONTROL No longer ask this question]** 未選定，以確保在有新版本的Console可用時向所有用戶發出警報。  如果選擇此選項，則用戶將不會獲悉新的可用版本。

## 建立連接{#create-your-connection}

新安裝客戶端控制台後，請按照以下步驟建立與應用程式伺服器的連接：

1. 從Windows啟動控制台 **[!UICONTROL Start]** 的 **Adobe Campaign** 程式組。

1. 按一下憑據欄位右上角的連結以訪問連接配置窗口。

1. 按一下 **[!UICONTROL Add > Connection]** 並輸入Adobe Campaign應用伺服器的標籤和URL。

1. 通過URL指定到Adobe Campaign應用程式伺服器的連接。 使用DNS或電腦的別名或IP地址。

   例如，您可以使用 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 鍵。

1. 選中選項 **[!UICONTROL Connect with an Adobe ID]**。

1. 按一下 **[!UICONTROL Ok]** 的子菜單。

例如，您可以根據需要添加多個連接以連接到test、舞台和生產環境。

>[!NOTE]
>
>的 **[!UICONTROL Add]** 按鈕，您可以建立 **[!UICONTROL folders]** 來組織你的所有聯繫。 只需將每個連線拖放到資料夾中即可。

## 登錄Adobe Campaign {#logon-to-ac}

要登錄到現有實例，請執行以下步驟：

1. 從Windows啟動控制台 **[!UICONTROL Start]** 的 **Adobe Campaign** 程式組。

1. 按一下憑據欄位右上角的連結以訪問連接配置窗口。

   ![](assets/connectToCampaign.png)

1. 選擇要登錄的市場活動實例。

1. 按一下&#x200B;**[!UICONTROL Ok]**。

1. 然後，您可以使用 [你的Adobe ID](#connect-ims)。

   ![](assets/adobeID.png)

## 授予用戶訪問權限{#grant-access}

Adobe Campaign允許您定義和管理分配給各種運算子的權限。 這些是授權或拒絕的一組權利和限制：

* 訪問某些功能（通過指定權限）,
* 訪問某些元素，
* 建立、修改和/或刪除要素（交貨、聯繫人、市場活動、組等）。

瞭解有關用戶的詳細資訊以及如何在 [此部分](permissions.md)。

作為市場活動管理員，您負責建立操作員並與用戶共用其憑據。

## 與您的Adobe ID聯繫{#connect-ims}

活動用戶通過AdobeIdentity Management系統(IMS)使用其Adobe ID連接到Adobe Campaign控制台。 他們可以使用相同的ID所有Adobe解決方案。 將Adobe Campaign與其他解決方案一起使用時，將保存連接。

瞭解有關Adobe IMS的詳細資訊 [此頁](https://helpx.adobe.com/enterprise/using/identity.html)。

## 網路存取{#web-access}

使用HTML用戶介面，可以通過Web瀏覽器訪問應用程式的某些部分：報告、交付審批、實例監控等。

網路存取介面與主控台的介面類似，但是功能有所減少。

例如，對於給定操作員，市場活動將在控制台中顯示以下選項：

![](assets/campaign-from-console.png)

而網路存取介面上，主要啟用檢視選項：

![](assets/campaign-from-web.png)

Web訪問也用於驗證過程：操作員可以按一下批准請求電子郵件並通過其web瀏覽器連接到市場活動，以驗證或拒絕交付內容或預算。

要從Web訪問您的Campaign實例，URL為：  `https://<your adobe campaign server>:<port number>/view/home`。
