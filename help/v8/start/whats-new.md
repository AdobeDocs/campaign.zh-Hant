---
title: Campaign v8 的新增功能
description: 探索 Campaign v8 中的重要功能
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '454'
ht-degree: 100%

---

# Adobe Campaign v8 有哪些新功能？ {#ac-gs-what-is-new}

Adobe Campaign v8 明顯改善基礎架構、安全性、可傳遞性和監視功能。 善用雲端資料庫技術[[!DNL Snowflake]](https://www.snowflake.com/)，Adobe Campaign 大幅提高了其規模和速度，能夠管理更多的客戶設定檔，並提供更高的每小時傳送率和異動。

主要功能包括：

* **速度和規模**。Adobe Campaign v8 利用雲端資料庫管理器，讓查詢的執行速度加快 200 倍，擴充了數 PB 規模，每小時訊息數增加，異動訊息達 20M 或 1M/小時，並管理多達 2 億個活動中檔案，甚至可能多達 10 億。

* **與 Adobe Experience Platform 的連結**。Adobe Campaign v8 支援 Adobe Experience Platform/RT-CDP 的資料連接器、統一的客戶設定檔以及與 Journey Orchestration 的原生整合。 這些投資將最佳化 Adobe Campaign 的客戶體驗，並解鎖新的使用實例，例如新增個人化即時客戶歷程至行銷活動等功能。

* **Managed Cloud Services**。Adobe Campaign v8 是同級最佳的 Managed Cloud Services，提供主動預防性監督、即時警報和服務治理。行銷人員的價值在於更敏捷、更可擴充的跨頻道行銷活動管理。

>[!CAUTION]
>
>目前，Campaign v8 僅&#x200B;****&#x200B;可作為托管 Cloud Service 使用，且無法在內部部署或混合環境中部署。
>
>尚無法從現有 Campaign Classic v7 環境進行移轉。
>
>如果您不確定部署模式，或有任何疑問，請洽詢您的帳戶團隊。

![](assets/home-page.png)

## 規模調整

Campaign v8 在流程的任何步驟中都提供端對端規模調整，從目標定位到最終報告：

* 擴充可處理的資料量 (至 8 TB)
* 針對細分和目標定位以及資料擷取與匯出調整查詢的效能
* 調整傳送準備規模 (從小時到分鐘)

## 簡化並提高效能

Campaign v8 引入了&#x200B;**完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫上遠端處理。

使用此新架構，Campaign v8 可簡化資料管理：雲端資料庫不需要索引。 您只需要建立表格、複製資料，即可開始。

[!DNL Snowflake] 是 Campaign Cloud 資料庫，可為您帶來速度和耐力：系統活動峰值不會過載。

雲端資料庫技術不需要進行具體的維護來保證效能等級。

## 整合的生態系統

您可以將 Campaign 與一組功能強大的 Adobe 解決方案整合，例如：Adobe Analytics、Adobe Journey Orchestration、即時 CDP 等。

您也可以使用 Journey AI 設定預測性傳送時間最佳化和預測性參與度評分，並提高開放率、點擊次數和收入。

?? [進一步瞭解 Campaign 整合](../connect/integration.md)

