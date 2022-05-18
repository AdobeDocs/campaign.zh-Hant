---
title: Campaign Classic v7 - Campaign v8 功能對照表
description: 瞭解 Campaign Classic v7 和 Campaign v8 之間的差異
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 40%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 功能{#gs-matrix}

作為前 [!DNL Campaign Classic] v7用戶，您不應期望與通常交互的方式出現任何大中斷 [!DNL Adobe Campaign]。 除了 UI 和設定步驟中出現的小變更以外，v8 中的大多數變更都看不太到。

Adobe Campaignv8可作為 **托管Cloud Service**。 這一新產品將同類最佳服務與前瞻性監督和及時警報相結合，重點關注三個方面：

* **雲靈活性**  — 通過Adobe實現自動化，其特徵是優化、標準化的雲部署，以實現更可預測的效能、更高的靈活性和更高的自助服務工作效率。
* **服務體驗**  — 主動預防性的可用性、容量和效能監控和響應，以防止中斷、更快地解決事件，並定期審查服務以持續改進。
* **深入的營銷專長**  — 由專家客戶工程團隊提供的高親和力服務，以滿足功能、技術或可交付性需求，降低部署風險，並改進變更管理。

作為前 [!DNL Campaign Classic] 用戶，請注意 [!DNL Campaign Classic] v7功能 [!DNL Campaign] v8，除小組外，列在 [此部分](#gs-removed)。 其他內容將在未來發行中推出。 [在本節了解更多資訊](#gs-unavailable-features)

>[!NOTE]
>
> Campaing v8依賴於混合架構。 如果要從Campaign Classicv7進行轉換，請注意，所有交貨都通過中間採購伺服器。 [了解更多](../architecture/architecture.md)
>
> 因此，內部路由 **不可能** 在市場活動v8中，外部帳戶已相應禁用。


## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

Campaing v8與 [!DNL Snowflake]。 有兩種部署模式。

![](../assets/do-not-localize/glass.png) 在本頁面了解更多 [!DNL Campaign] v8 [架構](../architecture/architecture.md)。


## 使用您的Adobe ID連接到活動{#adobe-id}

Campaign 使用者透過其 Adobe ID 連線。 同一個Adobe ID用於將您的所有Adobe計畫和產品與單個客戶關聯，用於所有Adobe Experience Cloud解決方案。

![](../assets/do-not-localize/glass.png)瞭解在[此頁面](connect.md)如何連結到[!DNL Campaign].。

## 使用立方分析資料{#adobe-reporting}

使用「市場營銷分析」模組可以分析和測量資料、計算統計資訊、簡化和優化報表建立和計算。 此外，建立報告並構建目標群體：一旦識別，它們就儲存在可在Adobe Campaign使用的清單中（目標、分段等）。

Adobe Campaign立方報告經過優化，比Campaign Classicv7提供了更好的擴展能力。 以前對Cubes的限制不適用於Campaing v8。

## 變更資料來源 {#change-data-source}

Campaign v8 提供額外目標定位工作流程活動：**[!UICONTROL Change data source]**。

**[!UICONTROL Change data source]**&#x200B;活動可讓您變更工作流程的資料來源&#x200B;**[!UICONTROL Working table]**，以管理不同資料來源 (例如FDA、FFDA 和本機資料庫) 的資料。

![](../assets/do-not-localize/glass.png)**[!UICONTROL Change data source]**&#x200B;在[本頁面](../config/workflows.md#change-data-source-activity)瞭解活動的更多資訊。

## 未提供的功能{#gs-unavailable-features}

請注意此 Campaign 版本尚未提供部分功能，例如：

* 行銷資源管理
* 分散式行銷
* 回應管理員
* 混合/內部部署模型

>[!CAUTION]
>
>* 目前，Campaign v8 僅&#x200B;****&#x200B;可作為托管 Cloud Service 使用，而且無法在內部部署或混合環境中進行部署。
>
>* 尚無法從現有 Campaign Classic v7 環境進行移轉。
>
>* 如果您不確定您的部署模式或有任何問題，請與您的Adobe客戶主管聯繫。


## 不支援的功能{#gs-removed}

為符合 Campaign v8 的新架構和部署模型，Campaign v8 中已不再提供一些 Campaign Classic v7 的歷史性功能。例如:

* 優惠券
* 網路追蹤
* 調查
* 社交行銷搭配 Facebook
* ACS 連接器 (主要優惠)
* 與 LDAP 整合
* 使用者/密碼登入

>[!NOTE]
>
>某些不可用或不受支援的功能在用戶介面中仍可見。
