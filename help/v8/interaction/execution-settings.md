---
product: campaign
title: 執行設定
description: 執行設定
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: simulating-offers
exl-id: e2dea4a0-9ed8-47b6-a16b-eeee653d2290
TQID: 'https://experienceleague.adobe.com/k2-e-laXDXtVyBJnoiyKAdNHKiS3nB-t1X1cEaqeudM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 936b7519d13ab54d94df9305ef05d4ceb6d6742d
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 4%
---
# 執行設定{#execution-settings}



建立模擬時，您可以視需要指定執行設定。 這些設定可讓您在活動較少期間根據其優先順序執行模擬，或在記錄中記錄SQL查詢。 此階段為選填。

這些設定稍後可以在模擬視窗的&#x200B;**[!UICONTROL General]**&#x200B;標籤中變更。

![](assets/offer_simulation_008.png)

* **[!UICONTROL Schedule execution for a time of low activity]** ：可讓您根據所選的優先順序（低、平均或高）排程模擬，以最佳化Adobe Campaign效能。
* **[!UICONTROL Priority]** ：這是套用至模擬以排程的層級。 核取&#x200B;**[!UICONTROL Schedule execution for a time of low activity]**&#x200B;選項時，行銷活動處理工作流程會選取活動較少的時間來開始行銷活動。
* **[!UICONTROL Log SQL queries in the journal]** ：此功能僅供專家使用者使用。 它可讓您新增標籤到顯示SQL查詢的記錄中，以在模擬完成時偵測可能的故障。
