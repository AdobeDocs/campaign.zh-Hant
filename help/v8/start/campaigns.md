---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用行銷活動
description: 開始使用行銷活動
feature: 閱聽眾
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 7%

---

# 開始使用行銷活動{#gs-ac-campaigns}

Adobe Campaign提供一套解決方案，可協助您個人化所有線上和離線管道，並傳送行銷活動。 您可以建立、設定、執行和分析行銷活動。 所有行銷活動都可從統一的控制中心管理。 探索如何在本區段瀏覽及建立行銷活動。

促銷活動包括動作（傳送）和程式（匯入或擷取檔案），以及資源（行銷檔案、傳送大綱）。 它們用於行銷活動。 行銷活動是方案的一部分，而方案則包含在行銷活動計畫中。

## 跨通路的行銷活動策劃

Adobe Campaign 可讓您在多個通路上設計及編排有針對性的個人化行銷活動：電子郵件、直效行銷郵件、SMS、推播通知等。單一介面可為您提供排程、編排、設定、個人化、自動化、執行和評量所有行銷活動和通訊所需的所有功能。

### 核心概念

開始實作行銷活動之前，您必須先熟悉下列概念：

* **行銷活動**:行銷活動會集中處理與行銷活動相關的所有元素：傳遞、目標規則、成本、匯出檔案、相關檔案等。每個促銷活動都會附加至方案。

* **方案**:方案可讓您定義日曆期間的行銷動作：啟動、遊說、忠誠度等。每個方案都包含連結至行事歷的促銷活動，而行事歷可提供整體檢視。

* **計畫**:行銷計畫可包含多個方案。它連結到日曆期間，有分配的預算，也可以連結到文檔和目標。

* **行銷活動工作流程**:促銷活動工作流程包含建立促銷活動邏輯的活動。使用行銷活動工作流程來定義對象，並為所有可用管道建立傳送。

* **循環促銷活動**:循環促銷活動是從定義要執行的工作流程範本和執行排程的特定範本建立。

* **定期促銷活動**:定期促銷活動是根據其範本的執行排程自動建立的促銷活動。

## 行銷活動工作區

Adobe Campaign可讓您從統一控制中心建立、設定、執行和分析所有行銷活動。

:arrow_upper_right:探索如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)中存取及實作行銷活動


## 開始的關鍵步驟

建立跨管道行銷活動的關鍵步驟為：

1. **規劃及設計行銷方案與行銷活動**

   定義層次結構和計畫、設定預算、添加資源、選擇運算子。

   :arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)中了解如何建立行銷計畫和設定行銷活動

   所有行銷活動都以範本為基礎，範本會儲存主要設定和功能。 提供內建範本，以建立尚未定義特定設定的促銷活動。 您可以建立和設定促銷活動範本，然後從這些範本建立促銷活動。

   :arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)中了解如何使用行銷活動範本

   :arrow_upper_right:探索循環促銷活動以及如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)中設定

1. **定義對象**

   您可以在工作流程中建立對象，或選取現有群組，例如收件者清單、電子報訂閱者、先前傳送的收件者或任何篩選條件。

   :arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)中了解如何定義訊息的對象

1. **建立傳送**

   選取管道、定義訊息內容並開始傳送。

   :arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)中了解如何建立和開始行銷活動傳送

   您可以將各種檔案與促銷活動建立關聯：報告、照片、網頁、圖表等。

   :arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)中進一步了解相關檔案

1. **設定核准流程**

   Adobe Campaign可讓您為行銷活動的主要階段設定協作核准流程。 對於每個促銷活動，您可以核准傳遞目標、內容和成本。 負責核准的Adobe Campaign運算子可透過電子郵件接收通知，並可從主控台或透過網路連線接受或拒絕核准。

   :arrow_upper_right:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)中設定和管理核准

