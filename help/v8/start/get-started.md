---
title: 開始使用 Campaign v8
description: 不熟悉 Adobe Campaign？請參閱相關文件，了解如何啟動及執行您的軟體，以及從何處開始使用介面。
feature: Overview, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d
version: Campaign v8, Campaign Classic v7
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 92%

---

# 開始使用 Adobe Campaign{#gs-ac-v8}

Adobe Campaign 提供了設計跨管道客戶體驗的平台，以及適用於視覺行銷活動協調流程、即時互動管理和跨管道執行的環境。

Adobe Campaign v8 是專為電子郵件、推播通知、簡訊和直接郵件等各種行銷管道打造的新一代行銷活動工具。 它提供強大的 ETL 和資料管理功能，有助於製作和策畫完美的促銷活動。 其編排引擎為豐富的多點觸控行銷方案提供了支援，其核心是批次型處理的驅動歷程。 還配備可擴充的即時傳訊伺服器，讓行銷團隊能夠根據來自任何 IT 系統的全包式承載來傳送預先定義的訊息，進行諸如重設密碼、確認訂單、電子收據等通訊。

Adobe Campaign v8 顯著改善基礎架構、安全性、傳遞能力和監視功能。其可作為 **Managed Cloud Service** ，結合服務與主動預防性監督和即時警報。[在本頁中](whats-new.md#acms-desc)深入了解 Campaign Managed Cloud Services。

使用 Campaign 可以：

* **透過存取單一客戶視圖，推動個人化和參與**
* 將電子郵件、行動裝置、線上和線下頻道&#x200B;**整合**&#x200B;至客戶歷程
* **自動化傳送有意義的即時訊息和產品建議**

![](assets/do-not-localize/ac-capabilities.png)


>[!AVAILABILITY]
>
>除非在頁面中提及，否則Adobe Campaign （主控台）檔案適用於Campaign Classic v7和Campaign v8。
>
>請注意，檔案中的某些參考資料可能仍會參考先前的品牌，但仍適用於目前的產品。

## 整合式客戶輪廓 {#integrated-customer-profile}

輪廓集中在功能強大的雲端資料庫中。 要取得輪廓來建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。藉助 Adobe Campaign，您可以將行銷記錄、購買資訊、偏好、CRM 資料以及任何相關的 PII 資料融入整合視圖中，以進行分析並採取行動。

在 Adobe　Campaign 中，收件者是用於傳送內容 (電子郵件、簡訊等) 的預設輪廓。有了資料庫中儲存的收件者資料，您能夠對接收任何給定內容的收件者進行篩選，並在交付內容中新增個人化資料。資料庫中還存在其他類型的輪廓。這些用戶檔案是針對不同用途設計的。例如，種子輪廓用於在內容傳送給最終目標前測試內容。

有關輪廓管理的基本資訊請參閱[本節](audiences.md)。

在[本節](import.md)瞭解如何新增輪廓至 Campaign。

## 目標市場細分 {#targeted-segmentation}

Adobe Campaign 提供了強大且方便使用的市場細分和目標鎖定功能，允許您建立針對性強的差異化產品建議。描述性分析功能可讓您分析行銷活動的上游和下游資訊，而[篩選管理](../audiences/create-filters.md)和圖形[查詢編輯器](query-editor.md)功能可讓您根據不限數量的條件，篩選訂閱者母體及樣本或建立目標群組。

進階資料管理功能進一步擴充了資料處理能力。該功能透過包含未在資料超市中模組化的資料，來簡化及最佳化目標定位流程。

在[本節](audiences.md)深入瞭解客戶細分與客群建立。

## 跨頻道行銷活動策劃 {#cross-channel-campaign-orchestration}

Adobe Campaign 可讓您在多個頻道上設計及編排有針對性的個人化行銷活動：電子郵件、直接行銷郵件、簡訊、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評估所有行銷活動和通訊所需的所有功能。

在[本章節](campaigns.md)瞭解行銷活動設計、排程及執行。

## 工作流程 {#wf-gsv8}

Adobe Campaign 提供完整的圖形環境，讓您設計複雜程式，包括細分、行銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮，然後將其中的記錄匯入 Adobe Campaign 資料庫。

工作流程也可以讓使用者參與，例如向使用者指派工作或由他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准校樣。

工作流程可用於不同的內容，例如：

* 定位以管理客群或傳送訊息。
* 資料管理 (ETL)，以操作資料。
* 將資料匯入 Campaign 資料庫。
* 技術流程，例如資料庫清理、復原追蹤資訊等。

在[本章節](../config/workflows.md)瞭解如何設計與執行工作流程。

## 報告與分析 {#analysis-and-reporting}

您可以使用 Adobe Campaign 透過逐步豐富客戶資料和輪廓，來監視和詮釋客戶行為。您可以使用報告和分析工具充分利用每一次新的行銷活動、更有效地鎖定行銷方案，且最佳化行銷影響力及投資報酬率。

除了功能強大的現成報告範本外，Adobe Campaign 還允許您在傳遞、行銷活動、使用者或區段層級建立自訂報告。 進行敘述性分析、匯總 ROI 或將資料匯出至 Adobe Analytics 和其他解決方案，以便進一步視覺化呈現資料並加以分析。

行銷活動報告功能有助於建立動態報告。 您可以利用可拖放的變數來自訂報告並分析行銷活動的成功與否。 根據查詢和計算的複雜性，資料可以彙總到清單檢視或透過便於產生行銷分析報告的格式加以存取。


在[本節](../reporting/gs-reporting.md)進一步瞭解報告與追蹤功能。

## Adobe Experience Cloud 整合 {#adobe-experience-cloud-integrations}

您可以將 Adobe Campaign 的傳遞功能和行銷活動管理進階功能，與協助您個人化使用者體驗的解決方案 (例如：Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 觸發程式) 相互結合。

在[本章節](../connect/integration.md)瞭解如何整合 Adobe 服務與解決方案。

## 關於 Campaign 功能的更多資訊 {#core-capabilities-and-add-ons}

Adobe Campaign 提供了一系列功能，協助您根據需求和架構實施及最佳化對話式行銷功能。其中部分是核心功能，部分功能取決於套件的安裝和您的設定。此處提供了詳盡的產品說明：[Adobe Campaign v8 產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html)。

已經熟悉 Campaign Classic 嗎？在[本頁](v7-to-v8.md)中瞭解 Campaign Classic 與 Campaign v8 的主要差異。

**另請參閱**

* [Campaign 工作環境](campaign-ui.md)
* [Campaign v8 相容性對照表](compatibility-matrix.md)
* [連線至 Campaign](connect.md)
* [常見問題集](campaign-faq.md)
