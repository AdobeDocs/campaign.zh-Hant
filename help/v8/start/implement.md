---
title: 實施方針
description: 瞭解如何實施 Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: ht
source-wordcount: '1170'
ht-degree: 100%

---

# Campaign 實施方針

在本節中，您將瞭解如何根據貴公司的需求調整 Adobe Campaign。 使用下列方針來建構並組織您的實施。

1. **定義設定**：授與存取權、共用用戶端控制台、設定頻道 (電子郵件、推播、簡訊)
1. **準備環境**：匯入設定檔、建立對象、設計工作流程和行銷活動範本，以及建立類型規則
1. **自訂您的執行個體**：建立新資料欄位，新增表格/方案
1. **擴展您的部署**：連結至 Adobe 解決方案、其他產品和系統：連接器、多解決方案設定

>[!CAUTION]
>
>若使用 **Campaign Managed Cloud Services**，您的環境和初始設定已根據您的許可協定條款由 Adobe 設定。 您不得修改已安裝的內建套件、內建方案或報告。
>
>如果您需要使用 Campaign 附加元件或尚未佈建的特定功能，您必須聯絡 **Adobe 客戶服務**。

## 開始之前

本節包含隱私權與安全性的重要資訊，在開始實際實施之前，必須先加以檢視和考慮。

### 隱私權

Adobe Campaign 提供流程和設定，允許您根據適用的資料隱私法和收件者的偏好使用 Campaign。 您可以管理：

* **資料取得**：Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並管理收件者的同意。深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant#data-acquisition){target=&quot;_blank&quot;} 

* **使用者同意與資料保留**：瞭解如何取得使用者同意、設定雙重選擇加入訂閱機制、促進選擇退出並在 [Campaign Classic 隱私文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant#consent)中設定資料保留{target=&quot;_blank&quot;}

* **隱私和資料保護法規**：請參考[此章節](privacy.md)關於隱私權請求的資訊，以及這些法規對您的組織和 Adobe Campaign 的影響。

### 安全性

在 [Campaign 安全性檢查清單](../config/security.md)中瞭解安全性方針與 Adobe Campaign 原則

## 定義 Campaign 設定

### 新增使用者並授與權限

您可以手動將使用者新增至 Campagin，並將他們與群組建立關聯，並使其與您的角色階層一致。 接著，使用者就可以登入並存取適合他們的資料和權限。

![](../assets/do-not-localize/book.png)在[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=zh-Hant#getting-started){target=&quot;_blank&quot;} 中瞭解如何新增使用者至 Adobe Campaign。

### 安裝 Campaign 用戶端控制台

應用程式的主要使用者介面為豐富型客戶端，換言之，即僅與擁有標準網際網路通訊協定 (SOAP、HTTP 等) 的 Adobe Campaign 應用程式伺服器通訊的原生應用程式 (Windows)。Adobe Campaign 用戶端控制台提供絕佳使用便利性，可大幅提升生產力，而且使用的頻寬很少 (透過使用本機快取)，而且易於部署。 此控制台可從網路瀏覽器部署、可自動更新，且不需要任何特定網路組態，因為它只會產生 HTTP(S) 流量。

![](../assets/do-not-localize/glass.png) [深入瞭解 Campaign 用戶端主控台](connect.md)。

## 準備您的環境

在開始傳送訊息和建立行銷活動之前，您需要：

1. 匯入設定檔並建立閱聽眾

   Campaign 可協助您將聯絡人新增至雲端資料庫。 您可以載入檔案、排程並自動化多個聯絡人更新、在網路上收集資料，或直接在收件者表格中輸入設定檔資訊。

   ![](../assets/do-not-localize/glass.png) [瞭解如何匯入設定檔](import.md)。

   對象會分組到清單中，並可透過工作流程建立。 然後，您就可以在跨頻道傳遞中鎖定這些目標。

   ![](../assets/do-not-localize/glass.png) [瞭解如何定義對象](audiences.md)。

1. 建立範本

   行銷活動、傳遞、工作或工作流程都以儲存關鍵設定和功能的範本為基礎。 系統會為每個元件提供內建範本，其尚未定義特定組態。 您需要設定並調整範本以符合您的需求，並讓終端使用者也能使用範本。


   ![](../assets/do-not-localize/glass.png) 在[本頁面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=zh-Hant)瞭解如何使用行銷活動範本

   ![](../assets/do-not-localize/glass.png) 在[本頁面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant)瞭解如何設定工作流程範本

   在 [Campaign Classic v7 文件 ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hant){target=&quot;_blank&quot;}![](../assets/do-not-localize/book.png) 進一步瞭解電子郵件範本


1. 設定類型規則

   運用 Campaign 類型規則來篩選、控制和監視傳遞。 例如，疲勞規則控制傳送訊息的頻率和數量，以避免收件者過度徵求。 實施後，在傳遞中會參考類型規則。

   在[此章節](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=zh-Hant)進一步瞭解類型與疲勞管理。

1. 熟悉 Campaign 內建資料模型

   Adobe Campaign 附有預定義的資料模型。若要實施和自訂您的環境，您需要熟悉 Adobe Campaign 資料模型的內建表格以及它們之間的關係。

   ![](../assets/do-not-localize/glass.png) [深入瞭解 Campaign 資料模型](../dev/datamodel.md)。

## 自訂您的執行個體

您可以自訂許多不同的 Campaign 區域和功能。 我們的大部份客戶都會自訂三件事：

1. **表格和方案**

   Adobe Campaign 提供了通用方案來識別資料，例如：收件者、傳遞記錄、訂閱及更多。

   ![](../assets/do-not-localize/glass.png) 請參閱本節以深入瞭解 [Campaign 內建資料模型](../dev/datamodel.md)。

   ![](../assets/do-not-localize/glass.png) 您可以擴充現有方案或從頭開始建立新方案。 在[本頁](../dev/customize.md)中瞭解更多。

1. **儀表板和清單**

   您可以輕鬆設定清單、新增和移除欄位，以及自訂欄位。

   ![](../assets/do-not-localize/glass.png)在[本頁面](../dev/customize.md#gs-lists-and-filters)瞭解如何管理 Campaign 的篩選器和清單。

   您也可以根據您的需求建立新的控制面板以顯示 Campaign 資料。

   ![](../assets/do-not-localize/glass.png)在[本頁面](../dev/customize.md#gs-custom-dashboards)深入瞭解。

1. **報告**

   Campaign 提供一組內建報告，說明傳遞監視、URL 和點擊串流、追蹤、傳遞性指標等。

   除了內建報告之外，透過使用 Adobe Campaign，可以讓您在不同工作環境中根據不同需求產生報告。本檔案詳細說明了使用原則和實施模式。

   ![](../assets/do-not-localize/glass.png)在[本頁面](reporting.md)伸入瞭解 Campaign 的報告功能。


## 設定行銷活動自動化

若要跨多頻道為不同的閱聽眾策劃複雜的行銷活動，請善用 Campaign 自動化功能。

* 工作流程：管理流程和資料

* 訂閱和登陸頁面

* 類型規則：疲勞與控制管理

## 擴展您的部署

### 多解決方案實施

如果您使用其他 Adobe 解決方案，可將其連結至您的 Campaign 環境並結合功能。

* Campaign - Journey Orchestration
* Campaign - 即時 CDP
* Campaign - Experience Cloud 觸發程式
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/人員核心服務
* Campaign - 資產
* Campaign - Analytics 資料連接器


您也可以使用單一登入 (SSO) 來連線至 Campaign。在[本頁](connect.md)瞭解更多。

![](../assets/do-not-localize/glass.png) 在[本頁面](../connect/integration.md)瞭解可整合 Adobe Campaign 的完整 Adobe 解決方案清單。

### 連接器

將 Campaign 與協力廠商系統連結，以結合多種功能並自動化流程。

![](../assets/do-not-localize/glass.png) 在[本節](../connect/integration.md)深入瞭解可用的連接器。

**將您的 CRM 連結至 Campaign**

您可以將您的 Adobe Campaign 平台連接至 CRM 協力廠商系統，並同步資料：連絡人、帳戶、購買等。

![](../assets/do-not-localize/glass.png) 在[本節](../connect/integration.md#gs-crm-connectors)瞭解如何將 CRM 系統連結至 Campaign

**連結至外部資料庫**

您可以透過同盟資料存取 (FDA) 模組，將 Campaign Cloud 資料庫連結至外部系統。

![](../assets/do-not-localize/glass.png) 在[本節](../connect/integration.md#gs-fda)瞭解如何設定 Campaign FDA 模組，以定義存取參數
