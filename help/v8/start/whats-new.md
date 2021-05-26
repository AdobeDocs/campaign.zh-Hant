---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8的新功能
description: 了解更多重要功能
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Adobe Campaign v8的新增功能{#ac-gs-what-is-new}

Adobe Campaign v8提供重要的基礎架構、安全性、傳遞能力和監控增強功能。 透過運用[[!DNL Snowflake]](https://www.snowflake.com/)雲端資料庫技術，Adobe Campaign大幅改善其規模和速度，並能管理更多客戶設定檔，以及更高的每小時傳送率和交易。

主要功能包括：

* **速度和規模**。Adobe Campaign v8利用Cloud Database Manager，導致查詢執行速度加快200倍、規模高達數PB，每小時報文數量增加，交易式報文的報文數量高達20M/小時或1.5M/小時，並管理多達200M的活動配置檔案，可能達到1B。

* **連線至Adobe Experience Platform**。Adobe Campaign v8支援Data Connectors與Adobe Experience Platform/RT-CDP、統一的客戶設定檔，以及與Journey Orchestration的原生整合。 這些投資將可最佳化Adobe Campaign客戶體驗，並釋出新的使用案例，例如將個人化的即時客戶歷程新增至行銷活動的能力。

* **托管Cloud Services**。Adobe Campaign v8是同類最佳的受管Cloud Services，可提供主動式監督、及時警報和服務控管。 行銷人員的價值在於提供更靈活且可擴充的跨通道行銷活動管理。

>[!CAUTION]
>
>目前，Campaign v8僅&#x200B;****&#x200B;可作為托管Cloud Service使用，且無法部署在內部部署或混合環境中。
>
>尚無法從現有Campaign Classicv7環境進行移轉。


## 規模

Campaign v8可在程式的任何步驟（從定位到最終報告）提供端對端的規模：

* 擴展可處理的資料量（直到8 TB）
* 調整查詢的效能，以用於細分和定位，以及資料擷取和輸出
* 將傳送準備規模從小時縮小至分鐘

## 簡化和效能提高

Campaign v8提供&#x200B;**完整同盟資料存取**(FDA)的概念：雲資料庫上的所有資料現在都是遠程資料。

透過這個新架構，Campaign v8簡化了資料管理：雲資料庫上不需要索引。 您只需要建立表格、複製資料即可開始。

[!DNL Snowflake] 是Campaign雲端資料庫，將帶來速度和耐力：系統活動峰值沒有過載。

雲資料庫技術不需要進行特定維護，以保證效能水準。

## 整合生態系統

您可以將Campaign與一組強大的Adobe解決方案整合，例如：Adobe Analytics、Workfront、Journey Orchestration、即時CDP等。

您也可以使用Journey AI設定預測性傳送時間最佳化和預測性參與計分，並提高開放率、點按次數和收入。

[!DNL :bulb:] [進一步了解Campaign整合](../connect/integration.md)

