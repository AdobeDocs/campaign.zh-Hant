---
solution: Campaign
product: Adobe Campaign
title: 實施方針
description: 瞭解如何實作Campaign v8
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 2%

---

# 促銷活動實作指引

在本節中，您將學習如何根據貴公司的需求調整Adobe Campaign。 使用下列准則來建構並組織您的實作。

1. **定義設定**:授與存取權、共用用戶端主控台、設定頻道（電子郵件、推播、簡訊）
1. **準備環境**:匯入設定檔、建立觀眾、設計工作流程和促銷活動範本，以及建立排版規則
1. **自訂您的例項**:建立新資料欄位，添加表／方案
1. **擴展您的部署**:連接到Adobe解決方案、其他產品和系統——連接器、多解決方案設定

## 開始之前

本節包含開發人員在開始之前必須先處理其實作的相關資訊，以瞭解其隱私權與安全性。

### 隱私權

Adobe Campaign提供流程和設定，允許您根據適用的資料隱私法和收件者的偏好使用促銷活動。 您可以管理：

* **資料獲取**:Adobe Campaign可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並管理收件者的同意。 進一步瞭解[Campaign Classic檔案](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **使用者同意與資料保留**:瞭解如何取得使用者同意、設定雙重選擇加入訂閱機制、促進選擇退出並在Campaign Classic隱私檔案中設定 [資料保留](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **隱私權與資料保護法規**:請參閱 [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) 隱私權檔案，以取得歐盟通用資料保護規則(GDPR)、加州消費者隱私法(CCPA)和其他國際隱私權要求的相關資訊，以及這些規定對貴組織和Adobe Campaign的影響。

### 安全性

在[促銷活動安全性檢查清單](../config/security.md)中瞭解安全性方針與Adobe Campaign原則

## 定義促銷活動設定

### 新增使用者並授與權限

您可以手動將使用者新增至Cammagin，並將他們與群組建立關聯，並與您的角色階層一致。 然後，使用者就可以登入並存取適合他們的資料和權限。

:arrow_upper_right:瞭解如何在[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started)中新增使用者至Adobe Campaign。

### 安裝Campaign用戶端主控台

應用程式的主要使用者介面是rich client，換言之，是原生應用程式(Windows)，僅與Adobe Campaign應用程式伺服器通訊，僅與標準網際網路通訊協定（SOAP、HTTP等）。 Adobe Campaign用戶端主控台提供絕佳的使用便利性，可大幅提升生產力，而且使用的頻寬很少（透過使用本機快取），而且易於部署。 此控制台可從網際網路瀏覽器部署、可自動更新，而且不需要任何特定網路組態，因為它只會產生HTTP(S)流量。

：球：[進一步瞭解Campaign Client Console](connect.md)。

## 準備您的環境

在開始傳送訊息和建立行銷促銷活動之前，您必須：

1. 匯入設定檔並建立觀眾

   Campaign可協助您將連絡人新增至Cloud資料庫。 您可以載入檔案、排程並自動化多個連絡人更新、在網路上收集資料，或直接在收件者表格中輸入描述檔資訊。

   ：球：[瞭解如何匯入描述檔](import.md)。

   觀眾會分組到清單中，並可透過工作流程建立。 然後，您就可以在跨通道傳送中鎖定這些目標。

   ：球：[瞭解如何定義觀眾](audiences.md)。

1. 建立範本

   促銷活動、傳送、工作或工作流程都以儲存關鍵設定和功能的範本為基礎。 系統會為每個元件提供內建範本，而尚未定義其特定組態。 您需要設定並調整範本以符合您的需求，並讓一般使用者也能使用範本。

   :arrow_upper_right:[進一步瞭解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)中使用促銷活動範本

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)中設定工作流程範本

1. 設定類型學規則

   運用促銷活動類型規則來篩選、控制和監控傳送。 例如，疲勞規則控制傳訊的頻率和數量，以避免收件者過度招攬。 實作後，在傳送中會參考類型學規則。

   :arrow_upper_right:[進一步瞭解類型和疲勞管理](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. 熟悉Campaign內建資料模型

   Adobe Campaign 隨附預先定義的資料模型。要實施和定制您的環境，您需要熟悉Adobe Campaign資料模型的內置表及其交互。

   ：球：[進一步瞭解Campaign資料模型](../dev/datamodel.md)。

## 自訂您的例項

您可以自訂許多不同的促銷活動區域和功能。 我們的大部份客戶都會自訂三件事：

1. **表和方案**

   Adobe Campaign提供了通用模式來識別資料，例如：收件者、傳送記錄、訂閱等。

   ：球：請參閱本節以進一步瞭解[Campaign內建資料模型](../dev/datamodel.md)。

   ：球：您可以擴展現有結構描述或從頭開始建立新結構描述。 進一步瞭解[本頁](../dev/customize.md)。

1. **控制面板和清單**

   您可以輕鬆設定清單、新增和移除欄位，以及自訂欄位。

   ：球：瞭解如何在[本頁](../dev/customize.md#gs-lists-and-filters)的「促銷活動」中管理篩選器和清單。

   您也可以根據您的需求建立新的控制面板以顯示促銷活動資料。

   ：球：進一步瞭解[本頁](../dev/customize.md#gs-custom-dashboards)。

1. **報告**

   Campaign提供一組內建的報表，說明傳送監控、URL和點按串流、追蹤、傳送能力指標等。

   除了內建報告之外，透過使用 Adobe Campaign，可以讓您在不同的工作環境中根據不同的需求產生報告。本檔案詳細說明了使用原則和實施模式。

   ：球：進一步瞭解[本頁](reporting.md)中促銷活動的報表功能。


## 設定促銷活動自動化

若要跨多個通道為不同的受眾策劃複雜的行銷宣傳，請運用Campaign自動化功能。

* 工作流程：管理流程和資料

* 訂閱和登陸頁面

* 類型學規則：疲勞與控制管理

## 擴展您的部署

### 多解決方案實作

如果您使用其他Adobe解決方案，可將其連線至您的Campaign環境並結合功能。

* 促銷活動-Journey Orchestration
* Campaign —— 即時CDP
* 促銷活動-Experience Cloud觸發器
* 促銷活動-Experience Manager
* 促銷活動——目標
* 促銷活動-Audience Manager/人員核心服務
* 促銷活動——資產
* 促銷活動- Analytics資料連接器


您也可以使用單一登入(SSO)來連線至促銷活動。 進一步瞭解[本頁](connect.md)。

：球：探索本頁](../connect/integration.md)中可與Adobe Campaign[整合的Adobe解決方案完整清單。

### 連接器

將Campaign與協力廠商系統連結，以結合多種功能並自動化流程。

：球：進一步瞭解[本節](../connect/integration.md)中的可用連接器。

**將您的CRM與Campaign連結**

您可以將您的Adobe Campaign平台連接至CRM協力廠商系統，並同步資料：連絡人、帳戶、購買等。

：球：瞭解如何在[本節](../connect/integration.md#gs-crm-connectors)中將CRM系統連線至Campaign

**連接到外部資料庫**

您可以透過Federated Data Access(FDA)模組，將Campaign Cloud資料庫連接至外部系統。

：球：瞭解如何設定Campaign FDA模組，以在[本節](../connect/integration.md#gs-fda)中定義存取參數
