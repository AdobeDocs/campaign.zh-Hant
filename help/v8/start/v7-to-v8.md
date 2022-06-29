---
title: 從Campaign Classicv7過渡到市場活動v8
description: 瞭解 Campaign Classic v7 和 Campaign v8 之間的差異
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 63e109f31706880a1723dfd0c611835842e39083
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 78%

---

# 從 [!DNL Campaign Classic] v7至 [!DNL Campaign] v8{#gs-matrix}

身為前 [!DNL Campaign Classic]v7 的使用者，您和 [!DNL Adobe Campaign] 的互動方式差異應該不會太大。除了 UI 和設定步驟中出現的小變更以外，v8 中的大多數變更都看不太到。

>[!AVAILABILITY]
>
>* 目前，Campaign v8 僅&#x200B;****&#x200B;可作為托管 Cloud Service 使用，而且無法在內部部署或混合環境中進行部署。[了解更多](#cloud-services)
>
>* 尚無法從現有 Campaign Classic v7 環境進行移轉。



## 托管Cloud Services{#cloud-services}

Adobe Campaign v8 可作為 **Managed Cloud Service**。 

Adobe Campaign Managed Cloud Services公司為設計跨渠道客戶體驗提供了Managed Services平台，並為可視的市場活動協調，即時交互管理和跨渠道執行提供了環境。 瞭解有關中的市場活動管理Cloud Services的詳細資訊 [產品說明頁](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}...

此新產品結合同級最佳服務與預防性監督和即時警報，重點關注三個方面：

* **Cloud 靈敏度** — 藉由 Adobe 實現自動化，最佳化、標準化的雲端部署，以實現更可預測的效能、更高的靈敏度和更高的自助服務工作效率。
* **服務體驗** — 主動的可用性、容量和效能監控和回應，以防止中斷，更快地解決事件，並定期審查服務以持續改進。
* **深入的行銷活動專長** — 由專家客戶工程團隊提供的高相似性服務，可滿足功能、技術或傳遞性需求，降低部署風險，並改善變更管理。

身為前[!DNL Campaign Classic]使用者，請注意[!DNL Campaign Classic] v7 中除了[本章節](#gs-removed)所列的一小部分功能外，也提供大部份[!DNL Campaign] v8 的功能。 其他內容將在未來發行中推出。 [在本節了解更多資訊](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 依賴於混合架構。 如果要從 Campaign Classic v7 進行轉換，請注意所有傳遞都會通過中間來源伺服器。 [了解更多](../architecture/architecture.md)
>
> 因此，內部路由&#x200B;**不可能**&#x200B;在 Campaign v8 中，且外部帳戶已據此停用。


## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 可以與[!DNL Snowflake]使用。 

在 [企業(FDA)部署](../architecture/enterprise-deployment.md)。 [!DNL Adobe Campaign] v8適用於兩個資料庫：當地 [!DNL Campaign] 用於用戶介面即時消息傳遞和統一查詢及通過API和雲寫入的資料庫 [!DNL Snowflake] 用於市場活動執行、批處理查詢和工作流執行的資料庫。

Campaign v8 企業版 帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。利用此新體系結構，Campaign v8 Enterprise(FDA)部署簡化了資料管理：雲資料庫不需要索引。 您只需建立表、複製資料即可啟動。 雲端資料庫技術不需要進行具體的維護來保證效能等級。

![](../assets/do-not-localize/glass.png) 在本頁面了解更多 [!DNL Campaign] v8 [架構](../architecture/architecture.md)。


## 使用您的 Adobe ID 連結到 Campaign{#adobe-id}

競選用戶只能通過他們的Adobe ID進行連接。 相同的 Adobe ID 可用來保留與單一帳戶相關聯的所有 Adobe Experience Cloud 解決方案。

![](../assets/do-not-localize/glass.png)瞭解在[此頁面](connect.md)如何連結到[!DNL Campaign].。

## 使用多維度資料集分析資料{#adobe-reporting}

使用「行銷分析」模組可以分析和測量資料、計算統計資料、簡化和最佳化報告建立和計算。 此外，建立報告並建置目標母體：一經識別，儲存在 Adobe Campaign (目標定位、分段等) 使用的清單中。

請注意，已最佳化多維度資料集報告，且提供比 Campaign Classic v7 更好的擴充功能。 以前對多維度資料集的限制不適用於 Campaign v8。

## 未提供的功能{#gs-unavailable-features}

請注意此 Campaign 版本尚未提供部分功能，例如：

* 行銷資源管理
* 混合/內部部署模型


## 不支援的功能{#gs-removed}

為符合 Campaign v8 的新架構和部署模型，Campaign v8 中已不再提供一些 Campaign Classic v7 的歷史性功能。例如:

* 優惠券
* 網路追蹤
* 調查
* 社交行銷
* ACS 連接器 (主要優惠)
* 與 LDAP 整合
* 使用者/密碼登入

>[!NOTE]
>
>使用者介面中仍會顯示某些無法使用或不支援的功能。
