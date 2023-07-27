---
title: 從 Campaign Classic v7 轉變到 Campaign v8
description: 了解 Campaign Classic v7 和 Campaign v8 之間的差異。
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 1297d5a602d125cb80ca6efb490b12174bcea8d6
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 92%

---

# 從 [!DNL Campaign Classic] v7 轉變至 [!DNL Campaign] v8{#gs-matrix}

身為前 [!DNL Campaign Classic]v7 的使用者，您和 [!DNL Adobe Campaign] 的互動方式差異應該不會太大。除了 UI 和設定步驟中出現的小變更以外，v8 中的大多數變更都看不太到。

>[!AVAILABILITY]
>
>* 目前，Campaign v8 **僅**&#x200B;可作為托管 Cloud Service 使用，而且無法在內部部署或混合環境中進行部署。[了解更多](#cloud-services)
>
>* 無法從現有 Campaign Classic V7 環境進行自動移轉。


## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 可作為 **Managed Cloud Service**。 

Adobe Campaign Managed Cloud Services 為設計跨頻道客戶體驗提供了 Managed Cloud Services 平台，同時為視覺銷活動的策劃、即時互動管理和跨頻道執行提供適合環境。進一步瞭解Campaign管理的Cloud Services，請參見 [產品說明頁面](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

此新產品結合同級最佳服務與預防性監督和即時警報，重點關注三個方面：

* **Cloud 靈敏度** — 藉由 Adobe 實現自動化，最佳化、標準化的雲端部署，以實現更可預測的效能、更高的靈敏度和更高的自助服務工作效率。
* **服務體驗** — 主動的可用性、容量和效能監控和回應，以防止中斷，更快地解決事件，並定期審查服務以持續改進。
* **深入的行銷活動專長** — 由專家客戶工程團隊提供的高相似性服務，可滿足功能、技術或傳遞性需求，降低部署風險，並改善變更管理。

身為前[!DNL Campaign Classic]使用者，請注意[!DNL Campaign Classic] v7 中除了[!DNL Campaign]本章節[所列的一小部分功能外，也提供大部份](#gs-removed) v8 的功能。 

Campaign v8依賴 **混合式架構**. 如果要從 Campaign Classic v7 進行轉換，請注意所有傳遞都會通過中間來源伺服器。 [了解更多](../architecture/architecture.md).因此，內部路由&#x200B;**不可能**&#x200B;在 Campaign v8 中，且外部帳戶已據此停用。

>[!NOTE]
>
>新的雲端架構可讓Campaign簡化流程、降低成本、管理風險，並改善資料安全性。 您的Campaign v8環境隨附預先為您設定的專用虛擬私人雲端(VPC)。

## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 可以與[!DNL Snowflake]使用。 

在[企業 (FFDA) 部署](../architecture/enterprise-deployment.md)中，[!DNL Adobe Campaign] v8 可同時使用兩個資料庫：本機 [!DNL Campaign] 資料庫，用於使用者介面即時傳送訊息並透過 API 統一查詢及寫入，以及雲端 [!DNL Snowflake] 資料庫，用於行銷活動執行、批次查詢及工作流程執行。

Campaign v8 企業版帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。使用此新架構，Campaign v8 企業 (FFDA) 部署可簡化資料管理：雲端資料庫不需要索引。 您只需要建立表格、複製資料，就可以開始。雲端資料庫技術不需要進行具體的維護來保證效能等級。

![](../assets/do-not-localize/glass.png) 在本頁面了解更多 [!DNL Campaign] v8 [架構](../architecture/architecture.md)。


## 使用您的 Adobe ID 連結到 Campaign{#adobe-id}

Campaign 使用者僅透過其 Adobe ID 連線。相同的 Adobe ID 可用來保留與單一帳戶相關聯的所有 Adobe Experience Cloud 解決方案。

![](../assets/do-not-localize/glass.png)瞭解在[此頁面](connect.md)如何連結到[!DNL Campaign].。

## 使用多維度資料集分析資料{#adobe-reporting}

使用「行銷分析」模組可以分析和測量資料、計算統計資料、簡化和最佳化報告建立和計算。 此外，建立報告並建置目標母體：一經識別，儲存在 Adobe Campaign (目標定位、分段等) 使用的清單中。

Adobe Campaign v8 已最佳化多維度資料集報告，且提供比 Campaign Classic v7 更好的擴充功能。 在該特定部署模型中，先前對多維資料集的限制不適用於 Campaign v8。若要深入了解多維度資料集，請參閱[本節](../../v8/reporting/gs-cubes.md)。

## 未提供的功能{#gs-unavailable-features}

請注意，某些功能無法用於[企業 (FFDA) 部署](../architecture/enterprise-deployment.md) 促銷活動的內容，例如：

* 行銷資源管理
* 優惠券
* 網路追蹤
* 調查

## 不支援的功能{#gs-removed}

Campaign v8 不再支援某些歷史性的 Campaign Classic v7 功能，例如：

* 使用 Facebook 進行社交行銷
* ACS 連接器 (主要優惠)
* 與 LDAP 整合
* 使用者/密碼登入
* 混合/內部部署模型


>[!NOTE]
>
>使用者介面中仍會顯示某些無法使用或不支援的功能。
