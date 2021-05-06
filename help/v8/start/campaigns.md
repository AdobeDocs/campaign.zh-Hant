---
solution: Campaign Classic
product: campaign
title: 開始使用行銷活動
description: 開始使用行銷活動
feature: 受眾
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
translation-type: tm+mt
source-git-commit: d7d026422d43e8baef43b114936366071f7086e5
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 8%

---

# 開始使用行銷促銷活動{#gs-ac-campaigns}

Adobe Campaign提供一套解決方案，幫助您跨所有線上及線下通道個人化並傳遞宣傳活動。 您可以建立、設定、執行及分析行銷促銷活動。 所有行銷活動都可從統一的控制中心進行管理。 探索如何在此區段中瀏覽及建立行銷促銷活動。

促銷活動包括動作（傳送）和程式（匯入或擷取檔案），以及資源（行銷檔案、傳送大綱）。 它們用於行銷促銷活動。 促銷活動是方案的一部分，而方案則包含在促銷活動計畫中。

## 跨通路的行銷活動策劃

Adobe Campaign 可讓您在多個通路上設計及編排有針對性的個人化行銷活動：電子郵件、直效行銷郵件、SMS、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評量所有行銷活動和通訊所需的所有功能。

### 核心概念

在開始實作行銷促銷活動之前，您必須熟悉下列概念：

* **行銷宣傳**:促銷活動會集中與行銷促銷活動相關的所有元素：傳送、定位規則、成本、匯出檔案、相關檔案等。每個促銷活動都會附加至一個方案。

* **計畫**:方案可讓您定義日曆期間的行銷動作：啟動、遊說、忠誠等。每個方案都包含連結至日曆的促銷活動，提供整體檢視。

* **計畫**:行銷計畫可包含多個方案。它連結至日曆期間、已分配預算，也可連結至檔案和目標。

* **促銷活動工作流程**:促銷活動工作流程包含建立促銷活動邏輯的活動。使用促銷活動工作流程可定義觀眾並建立所有可用渠道的傳送。

* **週期性促銷活動**:循環促銷活動是從定義要執行的工作流程範本和執行排程的特定範本建立。

* **定期促銷活動**:週期性促銷活動是根據其範本的執行排程自動建立的促銷活動。

## 行銷促銷活動工作區

Adobe Campaign可讓您從統一的控制中心建立、設定、執行和分析所有行銷宣傳。

:arrow_upper_right:瞭解如何存取及實作此頁面[中的行銷促銷活動](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## 啟動的關鍵步驟

建立跨通道行銷促銷活動的主要步驟為：

1. **規劃及設計行銷計畫與宣傳活動**

   定義層次結構和計畫、設定預算、添加資源、選擇運算子。

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)中建立行銷計畫及設定促銷活動

   所有行銷促銷活動都以儲存主要設定和功能的範本為基礎。 提供內建範本，以建立尚未定義特定設定的促銷活動。 您可以建立和設定促銷活動範本，然後從這些範本建立促銷活動。

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)中使用促銷活動範本

   :arrow_upper_right:探索循環性促銷活動以及如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)中設定這些促銷活動

1. **定義觀眾**

   您可以在工作流程中建立對象，或選取現有群組，例如收件者清單、電子報訂閱者、先前傳送的收件者或任何篩選條件。

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)中定義訊息的讀者

1. **建立傳送**

   選取渠道、定義訊息內容並開始傳送。

   :arrow_upper_right:瞭解如何在[此頁面](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)中建立和開始行銷促銷活動傳送

   您可以將各種檔案與促銷活動建立關聯：報表、像片、網頁、圖表等。

   :arrow_upper_right:進一步瞭解[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)中的相關檔案

1. **設定核准程式**

   Adobe Campaign可讓您針對行銷活動的主要階段設定協作核准程式。 您可以針對每個促銷活動核准傳送目標、內容和成本。 Adobe Campaign負責核准的營運商可以透過電子郵件收到通知，並可從主控台或透過網路連線接受或拒絕核准。

   :arrow_upper_right:瞭解如何在[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)中設定和管理核准


1. 監視消息：控制傳送和執行。 了解更多。

1. 規劃促銷活動和相關成本。 了解更多。

## 核准與驗證


## 服務與訂閱

建立服務並管理訂閱／取消訂閱

## 報告

促銷活動的報表

：球：
