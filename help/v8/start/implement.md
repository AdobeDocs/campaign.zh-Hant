---
solution: Campaign v8
product: Adobe Campaign
title: 實作准則
description: 了解如何實作Campaign v8
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 2%

---

# 行銷活動實作准則

在本節中，您將學習如何根據貴公司的需求調整Adobe Campaign。 使用下列准則來建構和組織您的實作。

1. **定義設定**:授予存取權、共用用戶端主控台、設定通道（電子郵件、推播、簡訊）
1. **準備環境**:匯入設定檔、建立對象、設計工作流程和行銷活動範本，建立類型規則
1. **自訂您的例項**:建立新資料欄位，添加表/方案
1. **擴充您的部署**:連接到Adobe解決方案、其他產品和系統 — 連接器、多解決方案設定

>[!CAUTION]
>
>若使用&#x200B;**促銷活動托管Cloud Services**，您的環境和初始配置已根據您的許可協定條款由Adobe設定。 您不得修改已安裝的內建套件、內建結構或報表。
>
>如果您需要使用促銷活動附加元件或尚未布建的特定功能，您必須聯絡&#x200B;**Adobe客戶服務**。

## 開始之前

本節包含隱私權與安全性的重要資訊，在開始實際實作前，都需先加以檢閱並考量。

### 隱私權

Adobe Campaign隨附程式和設定，可讓您使用Campaign，以符合適用的資料隱私權法律和收件者的偏好。 您可以管理：

* **資料贏取**:Adobe Campaign可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並管理收件者的同意。 進一步了解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **使用者同意和資料保留**:在Campaign Classic隱私權檔案中了解如何取得使用者同意、設定雙重選擇加入訂閱機制、促進選擇退出並設定 [資料保留](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **隱私權與資料保護規範**:如需歐盟 [一般](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) 資料保護規範(GDPR)、加州消費者隱私保護法(CCPA)及其他國際隱私權要求的相關資訊，以及這些規範對您的組織和Adobe Campaign有何影響，請參閱Campaign Classic隱私權檔案。

### 安全性

在[Campaign安全性檢查清單](../config/security.md)中，透過Adobe Campaign了解安全性准則和原則。

## 定義促銷活動設定

### 新增使用者並授予權限

您可以手動將使用者新增至Cammaign，並與群組建立關聯，並與您的角色階層保持一致。 然後，使用者將能登入並存取適合他們的資料和權限。

:[!DNL :arrow_upper_right:]:了解如何在[本區段](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started)中將使用者新增至Adobe Campaign。

### 安裝Campaign用戶端主控台

應用程式的主要使用者介面是豐富用戶端，換言之，是原生應用程式(Windows)，僅與Adobe Campaign應用程式伺服器通訊而採用標準網際網路通訊協定（SOAP、HTTP等）。 Adobe Campaign用戶端主控台提供絕佳的使用方便性，可提高生產力、使用極少的頻寬（透過使用本機快取），且專為輕鬆部署而設計。 此控制台可從Internet瀏覽器部署，可自動更新，不需要任何特定的網路配置，因為它只生成HTTP(S)流量。

[!DNL :bulb:] [進一步了解Campaign用戶端主控台](connect.md)。

## 準備您的環境

開始傳送訊息及建立行銷活動之前，您需要：

1. 匯入設定檔並建立對象

   Campaign可協助您將聯絡人新增至雲端資料庫。 您可以載入檔案、排程並自動執行多個連絡人更新、在網路上收集資料，或直接在收件者表格中輸入設定檔資訊。

   [!DNL :bulb:] [了解如何匯入設定檔](import.md)。

   對象會分組為清單，並可透過工作流程建立。 然後，就能在跨通道傳遞中鎖定目標。

   [!DNL :bulb:] [了解如何定義對象](audiences.md)。

1. 建立範本

   行銷活動、傳送、工作或工作流程都以範本為基礎，範本會儲存關鍵設定和功能。 系統會為每個元件提供內建範本，但尚未定義特定設定。 您需要根據您的需求配置和調整範本，並將範本提供給使用者使用。

   [!DNL :arrow_upper_right:] [深入了解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   [!DNL :arrow_upper_right:] 在本頁面中了解如何使用行銷 [活動範本](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] 在本頁面中了解如何設定工作流 [程範本](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. 設定類型規則

   運用Campaign類型規則來篩選、控制及監控傳送。 例如，疲勞規則可控制傳訊的頻率和數量，以避免收件者過度請求。 實作後，傳遞會參考類型規則。

   [!DNL :arrow_upper_right:] [深入了解類型與疲勞管理](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. 熟悉Campaign內建的資料模型

   Adobe Campaign 隨附預先定義的資料模型。若要實作和自訂您的環境，您必須熟悉Adobe Campaign資料模型的內建表格，以及它們彼此的關聯方式。

   [!DNL :bulb:] [深入了解Campaign資料模型](../dev/datamodel.md)。

## 自訂您的執行個體

您可以自訂許多不同的Campaign區域和功能。 我們的大部分客戶都自訂了三件事：

1. **表格和結構**

   Adobe Campaign提供可識別資料的常見結構，例如：收件者、傳送記錄、訂閱等。

   [!DNL :bulb:] 請參閱本節，深入了解 [Campaign內建的資料模型](../dev/datamodel.md)。

   [!DNL :bulb:] 您可以擴充現有結構或從頭建立新結構。深入了解[本頁面](../dev/customize.md)。

1. **控制面板和清單**

   您可以輕鬆設定清單、新增和移除欄位及自訂欄。

   [!DNL :bulb:] 透過本頁面了解如何在Campaign中管理篩選 [器和清單](../dev/customize.md#gs-lists-and-filters)。

   您也可以建立新的控制面板，以根據您的需求來顯示促銷活動資料。

   [!DNL :bulb:] 了解更多 [資訊](../dev/customize.md#gs-custom-dashboards)。

1. **報告**

   Campaign提供一組內建報告，內建有關傳送監控、URL和點按資料流、追蹤、傳遞能力指標等。

   除了內建報告之外，透過使用 Adobe Campaign，可以讓您在不同的工作環境中根據不同的需求產生報告。本檔案詳細說明使用原則和實施模式。

   [!DNL :bulb:] 透過本頁面進一步了解Campaign中的報 [表功能](reporting.md)。


## 設定促銷活動自動化

若要跨多個管道協調複雜的行銷活動給不同的對象，請運用Campaign自動化功能。

* 工作流程：管理流程和資料

* 訂閱與登錄頁面

* 類型規則：疲勞與控制管理

## 擴展部署

### 多解決方案實作

如果您使用其他Adobe解決方案，您可以將其連線至您的Campaign環境，並結合功能。

* 行銷活動 — Journey Orchestration
* Campaign - Real-time CDP
* Campaign -Experience Cloud觸發器
* 行銷活動 — Experience Manager
* 促銷活動 — 目標
* 行銷活動 — Audience Manager/人員核心服務
* 行銷活動 — 資產
* Campaign - Analytics Data Connectors


您也可以使用單一登入(SSO)連線至Campaign。 深入了解[本頁面](connect.md)。

[!DNL :bulb:] 在本頁面中探索可與Adobe Campaign整合的Adobe解決 [方案完整清單](../connect/integration.md)。

### 連接器

將Campaign與協力廠商系統連結，以結合大量功能並自動化流程。

[!DNL :bulb:] 了解更多可用連接器 [的相關資訊](../connect/integration.md)。

**將您的CRM連線至Campaign**

您可以將Adobe Campaign平台連線至您的CRM協力廠商系統，並同步資料：聯繫人、帳戶、購買等。

[!DNL :bulb:] 在本小節中了解如何將CRM系統連 [結至Campaign](../connect/integration.md#gs-crm-connectors)

**連接到外部資料庫**

您可以透過同盟資料存取(FDA)模組，將Campaign Cloud資料庫連線至外部系統。

[!DNL :bulb:] 在本節了解如何設定Campaign FDA模組以定義存取 [參數](../connect/integration.md#gs-fda)
