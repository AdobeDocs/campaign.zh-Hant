---
product: Adobe Campaign
title: Campaign v8 的新增功能
description: 探索Campaign v8中的關鍵功能
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 8b31e24e0b6cfb699179e62366bc6706e9019382
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 52%

---

# Adobe Campaign v8 有哪些新功能？{#ac-gs-what-is-new}

Adobe Campaign v8 明顯改善基礎架構、安全性、可傳遞性和監視。 透過運用[[!DNL Snowflake]](https://www.snowflake.com/)雲端資料庫技術，Adobe Campaign大幅改善其規模和速度，並能管理更多客戶設定檔，以及更高的每小時傳送率和交易。

主要功能包括：

* **速度和規模**。Adobe Campaign v8 利用雲端資料庫管理器，讓查詢的執行速度加快 200 倍，擴展了多 PB 規模，每小時訊息數增加，異動訊息時速達 20M 或 1M/ 小時，並管理多達 2 億個活動中檔案，甚至可能多達 10 億。

* **與 Adobe Experience Platform 的連結**。Adobe Campaign v8 支援 Adobe Experience Platform/RT-CDP 的資料連接器、統一的客戶設定檔以及與 Journey Orchestration 的原生整合。 這些投資將最佳化 Adobe Campaign 的客戶體驗，並解鎖新的使用實例，例如新增個人化即時客戶歷程至行銷活動等功能。

* **Managed Cloud Services**。Adobe Campaign v8 是同級最佳的 Managed Cloud Services，提供主動預防性監督、即時警報和服務治理。行銷人員的價值在於提供更靈活且可擴充的跨通道行銷活動管理。

>[!CAUTION]
>
>目前，Campaign v8僅&#x200B;****&#x200B;可作為托管Cloud Service使用，且無法部署在內部部署或混合環境中。
>
>尚無法從現有Campaign Classicv7環境進行移轉。
>
>如果您不確定部署模式或有任何疑問，請洽詢您的客戶團隊。

![](assets/home-page.png)

## 規模

Campaign v8可在程式的任何步驟（從定位到最終報告）提供端對端的規模：

* 擴充可處理的資料量 (至 8 TB)
* 針對細分和目標定位以及資料擷取與匯出調整查詢的效能
* 將傳送準備規模從小時縮小至分鐘

## 簡化並提高效能

Campaign v8帶來了&#x200B;**完整同盟資料存取**(FFDA)的概念：雲資料庫上的所有資料現在都是遠程資料。

透過這個新架構，Campaign v8簡化了資料管理：雲資料庫上不需要索引。 您只需要建立表格、複製資料，就可以開始。

[!DNL Snowflake] 是Campaign雲端資料庫，將帶來速度和耐力：系統活動峰值沒有過載。

雲端資料庫技術不需要進行具體的維護來保證效能等級。

## 整合的生態系統

您可以將Campaign與一組強大的Adobe解決方案整合，例如：Adobe Analytics、AdobeJourney Orchestration、即時CDP等。

您也可以使用 Journey AI 設定預測性傳送時間最佳化和預測性參與度評分，並提高開放率、點擊次數和收入。

[!DNL :bulb:] [進一步瞭解 Campaign 整合](../connect/integration.md)

