---
solution: Campaign Classic
product: campaign
title: 開始使用Campaign v8
description: 探索主要功能、使用者介面和全域方針
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
translation-type: tm+mt
source-git-commit: 97cc2dd6f78fac2723306f06bea74e808c84b4ad
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 55%

---

# 開始使用Adobe Campaign{#gs-ac-v8}

Adobe Campaign 為跨通路客戶體驗的設計提供了平台，並為可視性行銷活動的策劃、即時互動管理和跨通路執行提供了環境。

使用促銷活動可：

* 透過單一可存取的客戶視圖，推動個人化和互動
* 將電子郵件、行動裝置、線上和線下通道整合至客戶歷程
* 自動傳送有意義且及時的訊息和優惠

![](assets/ac-capabilities.png)

## 整合的客戶設定檔 {#integrated-customer-profile}

設定檔集中在powerfull雲端資料庫中。 要獲取用戶檔案，並建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。藉助 Adobe Campaign，您可以將行銷記錄、購買資訊、偏好、CRM 資料以及任何相關的 PII 資料融入整合視圖中，以進行分析並採取行動。

在 Adobe　Campaign 中，收件者是用於傳送內容 (電子郵件、SMS 等) 的預設用戶檔案。有了資料庫中儲存的收件者資料，您能夠對接收任何給定內容的收件者進行篩選，並在交付內容中新增個人化資料。資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

：球：描述檔管理基本資訊請參閱[本節](audiences.md)。

：球：瞭解如何在[本節](import.md)中新增描述檔至促銷活動。

## 目標市場細分 {#targeted-segmentation}

Adobe Campaign 提供了強大且方便使用的市場細分和目標鎖定功能，允許您建立針對性強的差異化優惠方案。描述性分析功能允許您分析行銷活動的上游和下游資訊，而篩選管理及圖形查詢編輯器功能允許您根據不限數量的條件來篩選訂閱者母體及樣本或者設定目標群組。

進階資料管理功能對資料處理能力進行了進一步的擴充。該功能透過包含未在資料超市中模型化的資料，來簡化及最佳化目標鎖定流程。

：球：在[本節](audiences.md)中進一步瞭解細分、受眾建立和個人化。

## 跨通路的行銷活動策劃 {#cross-channel-campaign-orchestration}

Adobe Campaign 可讓您在多個通路上設計及編排有針對性的個人化行銷活動：電子郵件、直效行銷郵件、SMS、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評量所有行銷活動和通訊所需的所有功能。

：球：瞭解如何在[本節](campaigns.md)中設計、排程及執行促銷活動。

## 工作流程

Adobe Campaign提供完整的圖形環境，讓您設計複雜的程式，包括區段、促銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮檔案，然後將其記錄匯入Adobe Campaign資料庫。

工作流程也可以讓使用者參與，方法是指派工作或讓他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准校樣。

工作流可用於不同的上下文，例如：

* 定位以管理觀眾或傳送訊息。
* 資料管理(ETL)，以控制資料。
* 將資料匯入促銷活動資料庫。
* 技術流程，例如資料庫清理、追蹤資訊的復原等。

：球：瞭解如何在[本節](../config/workflows.md)中設計和執行工作流程。

## 報告與分析{#analysis-and-reporting}

您可以使用 Adobe Campaign 透過逐步豐富客戶資料和用戶檔案，來監視和解讀客戶行為。使用報告和分析工具，您可以充分利用每一次新的行銷活動、更有效地鎖定行銷方案，且最優化行銷影響力及投資報酬。

：球： 進一步瞭解[本節](reporting.md)中的報告和追蹤功能。

## Adobe Experience Cloud 整合 {#adobe-experience-cloud-integrations}

您可以將 Adobe Campaign 的交付功能和行銷活動管理進階功能與協助您個人化使用者體驗的解決方案 (例如　Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 觸發程式) 相結合。您也可以透過 Adobe ID 整合至 Adobe IMS 並登入 Campaign。

：球：瞭解如何與[本節](../connect/integration.md)中的Adobe服務和解決方案整合。

## 關於促銷活動功能的更多資訊{#core-capabilities-and-add-ons}

Adobe Campaign 提供了一系列功能，協助您根據需求和架構實行及最佳化對話式行銷功能。其中部分是核心功能，部分功能取決於套件的安裝和您的設定。您可從以下網址取得詳細的產品說明：[Adobe Campaignv8產品說明](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-classic---product-description.html)。

：球：已熟悉Campaign Classic? 瞭解[本頁](capability-matrix.md)中Campaign Classic與Campaign v8的主要差異。

## 工作區與自訂

促銷活動工作區可透過用戶端主控台使用。

：球： 瞭解如何在[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)中使用促銷活動工作區

：球： 瞭解如何在[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)中自訂清單

您也可以透過Web存取某些功能。

