---
product: Adobe Campaign
title: 開始使用 Campaign v8
description: 探索重要功能、使用者介面和全域準則
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 78%

---

# 開始使用 Adobe Campaign{#gs-ac-v8}

Adobe Campaign 為跨頻道客戶體驗設計提供平台，並為視覺行銷活動的策劃、即時互動管理和跨頻道執行提供環境。

使用 Campaign 可以：

* **透過單一可存取的客戶檢視，推動個人化和參與**
* **將電子郵件、行動裝置、線上和線下頻道整合至客戶歷程**
* **自動化有意義且即時的訊息和優惠方案傳遞**

![](assets/ac-capabilities.png)

## Integrated Customer Profile{#integrated-customer-profile}

設定檔集中在功能強大的雲端資料庫中。 要獲取用戶檔案，並建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。藉助 Adobe Campaign，您可以將行銷記錄、購買資訊、偏好、CRM 資料以及任何相關的 PII 資料融入整合視圖中，以進行分析並採取行動。

在 Adobe　Campaign 中，收件者是用於傳送內容 (電子郵件、SMS 等) 的預設用戶檔案。有了資料庫中儲存的收件者資料，您能夠對接收任何給定內容的收件者進行篩選，並在交付內容中新增個人化資料。資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

[!DNL :bulb:] 本節將說明設定檔管理的 [基本知識](audiences.md)。

[!DNL :bulb:] 在本小節中了解如何將設定檔 [新增至Campaign](import.md)。

## 目標市場細分 {#targeted-segmentation}

Adobe Campaign 提供了強大且方便使用的市場細分和目標鎖定功能，允許您建立針對性強的差異化優惠方案。說明性分析功能讓您能夠分析行銷活動的上游和下游資訊，而篩選管理及圖形查詢編輯器功能則讓您能根據不限數量的條件，篩選訂閱者群體及樣本，或是建立目標群組。

進階資料管理功能進一步擴充了資料處理能力。該功能透過包含未在資料超市中模組化的資料，來簡化及最佳化目標定位流程。

[!DNL :bulb:] 在本小節中深入了解區段、受眾建立 [和個人化](audiences.md)。

## 跨通路的行銷活動策劃 {#cross-channel-campaign-orchestration}

Adobe Campaign 可讓您在多個頻道上設計及編排有針對性的個人化行銷活動：電子郵件、直接行銷郵件、SMS、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評估所有行銷活動和通訊所需的所有功能。

[!DNL :bulb:] 在本小節中了解如何設計、排程及執行 [行銷活動](campaigns.md)。

## 工作流程

Adobe Campaign 提供完整的圖形環境，讓您設計複雜程式，包括細分、行銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮，然後將其中的記錄匯入 Adobe Campaign 資料庫。

工作流程也可以讓使用者參與，例如向使用者指派工作或由他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准證明。

工作流程可用於不同的內容，例如：

* 定位以管理對象或傳送訊息。
* 資料管理 (ETL)，以操作資料。
* 將資料匯入 Campaign 資料庫。
* 技術流程，例如資料庫清理、復原追蹤資訊等。

[!DNL :bulb:] 在本小節中了解如何設計和執行工 [作流程](../config/workflows.md)。

## 報告與分析{#analysis-and-reporting}

您可以使用 Adobe Campaign 透過逐步豐富客戶資料和設定檔，來監視和詮釋客戶行為。您可以使用報告和分析工具充分利用每一次新的行銷活動、更有效地鎖定行銷方案，且最佳化行銷影響力及投資報酬率。

[!DNL :bulb:] 在本小節中進一步了解報告和 [追蹤功能](reporting.md)。

## Adobe Experience Cloud 整合 {#adobe-experience-cloud-integrations}

您可以將 Adobe Campaign 的傳遞功能和行銷活動管理進階功能，與協助您個人化使用者體驗的解決方案 (例如：Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 觸發程式) 相互結合。

[!DNL :bulb:] 在本小節中了解如何與Adobe服務和解決 [方案整合](../connect/integration.md)。

## 關於 Campaign 功能的更多資訊{#core-capabilities-and-add-ons}

Adobe Campaign 提供了一系列功能，協助您根據需求和架構實施及最佳化對話式行銷功能。其中部分是核心功能，部分功能取決於套件的安裝和您的設定。此處提供了詳盡的產品說明：[Adobe Campaign v8 產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-classic---product-description.html)。

[!DNL :bulb:] 已熟悉Campaign Classic?在[本頁](capability-matrix.md)中瞭解 Campaign Classic 與Campaign v8 的主要差異。

## 工作區與自訂

可透過[用戶端主控台](../dev/general-architecture.md)使用促銷活動工作區。

[!DNL :bulb:] [進一步了解Campaign用戶端主控台](../start/connect.md)。

可根據您的需求調整行銷活動工作區。

[!DNL :arrow_upper_right:]  在Campaign Classicv7檔案中了解如 [何使用Campaign工作區](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=zh-Hant)

[!DNL :arrow_upper_right:]  了解如何在 [Campaign Classicv7檔案中自訂清單](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=zh-Hant)

您也可以透過 Web 存取某些功能。

[!DNL :bulb:] [深入了解Campaign Web Access](../start/connect.md#web-access)。


## 語言

Campaign v8使用者介面提供下列語言版本：

* 英語（英國）
* 英文 (US)
* 法文
* 德文
* 日文

在安裝過程中將選擇該語言。

>[!CAUTION]
>
>建立執行個體後無法變更語言。

語言會影響日期和時間格式。 如需詳細資訊，請參閱[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time)。

