---
title: 開始使用 Campaign v8
description: 不熟悉 Campaign 嗎？ 瞭解如何開始使用
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 100%

---

# 開始使用 Adobe Campaign{#gs-ac-v8}

Adobe Campaign 為跨頻道客戶體驗設計提供平台，並為視覺行銷活動協調、Real-time Interaction Management 和跨頻道執行提供環境。

使用 Campaign 可以：

* **透過存取單一客戶視圖，推動個人化和參與**
* 將電子郵件、行動裝置、線上和線下頻道&#x200B;**整合**&#x200B;至客戶歷程
* **自動化傳送有意義的即時訊息和優惠方案**

![](assets/ac-capabilities.png)

## 整合式客戶設定檔 {#integrated-customer-profile}

設定檔集中在功能強大的雲端資料庫中。 要獲取用戶檔案，並建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。藉助 Adobe Campaign，您可以將行銷記錄、購買資訊、偏好、CRM 資料以及任何相關的 PII 資料融入整合視圖中，以進行分析並採取行動。

在 Adobe　Campaign 中，收件者是用於傳送內容 (電子郵件、SMS 等) 的預設用戶檔案。有了資料庫中儲存的收件者資料，您能夠對接收任何給定內容的收件者進行篩選，並在交付內容中新增個人化資料。資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

![](../assets/do-not-localize/glass.png)有關設定檔管理的基本資訊請參閱[本節](audiences.md)。

![](../assets/do-not-localize/glass.png)在[本節](import.md)瞭解如何新增設定檔至 Campaign。

## 目標市場細分 {#targeted-segmentation}

Adobe Campaign 提供了強大且方便使用的市場細分和目標鎖定功能，允許您建立針對性強的差異化優惠方案。說明性分析功能讓您能夠分析行銷活動的上游和下游資訊，而篩選管理及圖形查詢編輯器功能則讓您能根據不限數量的條件，篩選訂閱者群體及樣本，或是建立目標群組。

進階資料管理功能進一步擴充了資料處理能力。該功能透過包含未在資料超市中模組化的資料，來簡化及最佳化目標定位流程。

![](../assets/do-not-localize/glass.png)在[本節](audiences.md)中深入瞭解細分、對象建立和個人化。

## 跨頻道行銷活動策劃 {#cross-channel-campaign-orchestration}

Adobe Campaign 可讓您在多個頻道上設計及編排有針對性的個人化行銷活動：電子郵件、直接行銷郵件、SMS、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評估所有行銷活動和通訊所需的所有功能。

![](../assets/do-not-localize/glass.png)在[本節](campaigns.md)中瞭解行銷活動的設計、排程及執行。

## 工作流程

Adobe Campaign 提供完整的圖形環境，讓您設計複雜程式，包括細分、行銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮，然後將其中的記錄匯入 Adobe Campaign 資料庫。

工作流程也可以讓使用者參與，例如向使用者指派工作或由他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准證明。

工作流程可用於不同的內容，例如：

* 定位以管理對象或傳送訊息。
* 資料管理 (ETL)，以操作資料。
* 將資料匯入 Campaign 資料庫。
* 技術流程，例如資料庫清理、復原追蹤資訊等。

![](../assets/do-not-localize/glass.png)在[本節](../config/workflows.md)中瞭解如何設計和執行工作流程。

## 報告與分析 {#analysis-and-reporting}

您可以使用 Adobe Campaign 透過逐步豐富客戶資料和設定檔，來監視和詮釋客戶行為。您可以使用報告和分析工具充分利用每一次新的行銷活動、更有效地鎖定行銷方案，且最佳化行銷影響力及投資報酬率。

![](../assets/do-not-localize/glass.png)進一步瞭解[本節](reporting.md)中的報告和追蹤功能。

## Adobe Experience Cloud 整合 {#adobe-experience-cloud-integrations}

您可以將 Adobe Campaign 的傳遞功能和行銷活動管理進階功能，與協助您個人化使用者體驗的解決方案 (例如：Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 觸發程式) 相互結合。

![](../assets/do-not-localize/glass.png) 在[本節](../connect/integration.md)中瞭解如何整合 Adobe 服務和解決方案。

## 關於 Campaign 功能的更多資訊 {#core-capabilities-and-add-ons}

Adobe Campaign 提供了一系列功能，協助您根據需求和架構實施及最佳化對話式行銷功能。其中部分是核心功能，部分功能取決於套件的安裝和您的設定。此處提供了詳盡的產品說明：[Adobe Campaign v8 產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html)。

![](../assets/do-not-localize/glass.png) 已經熟悉 Campaign Classic 嗎？在[本頁](capability-matrix.md)中瞭解 Campaign Classic 與Campaign v8 的主要差異。

## 工作區與自訂

Campaign 工作區可在[用戶端主控台](../dev/general-architecture.md)提供。

![](assets/home-page.png)

![](../assets/do-not-localize/glass.png) [進一步瞭解 Campaign 用戶端主控台](../start/connect.md)。

可根據您的需求調整 Campaign 工作區。

![](../assets/do-not-localize/book.png)  在 Campaign Classic v7 文件中瞭解 [如何使用 Campaign 工作區](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=zh-Hant){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何自訂清單

您也可以透過網頁存取某些功能。

![](../assets/do-not-localize/glass.png) [深入瞭解 Campaign 網頁存取](../start/connect.md#web-access)。


## 語言

Campaign v8 使用者介面提供下列語言版本：

* 英文 (英國)
* 英文 (美國)
* 法文
* 德文
* 日文

在安裝過程中選擇語言。

>[!CAUTION]
>
>建立執行個體後無法變更語言。

語言會影響日期和時間格式。 如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=zh-Hant#date-and-time){target=&quot;_blank&quot;}。

**另請參閱**

* [Campaign v8 相容性對照表](compatibility-matrix.md)
* [連結至 Campaign](connect.md)
* [常見問題集](campaign-faq.md)