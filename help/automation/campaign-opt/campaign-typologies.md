---
product: campaign
title: 開始使用行銷活動類型
description: 了解如何設定和實作行銷活動類型
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 19%

---

# 開始使用行銷活動類型{#about-campaign-typologies}

**促銷活動最佳化** 是Adobe Campaign模組，可讓您控制、篩選及監控傳送的傳送。 為了避免行銷活動之間發生衝突，Adobe Campaign 可以套用特定限制規則來測試各種組合。這樣可確保傳送的訊息符合客戶和公司通訊政策的需求及期望。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#typologies-video)

>[!NOTE]
>
>視您的產品而定，可包含促銷活動最佳化或附加元件。 請檢查您的授權合約。

## 類型規則與類型 {#typology-rules}

依預設，Campaign會提供內建的類型與類型規則。

類型是傳遞分析期間套用於所有訊息的一組驗證規則。

行銷活動類型可包含數個類型規則，但傳送只能參考一個類型。

內建的類型規則和類型可在 **[!UICONTROL Administration > Campaign management > Typology management]** Campaign檔案總管的資料夾。

對於每個類型， **[!UICONTROL Rules]** 索引標籤可讓您新增、刪除或檢視要套用的類型規則。

![](assets/campaign_opt_rules_tab.png)

建立類型規則後，就會在行銷活動中分組類型規則 **類型** 在傳送中參考。 [了解更多資訊](#apply-typologies)。


Campaign隨附一組預設值 **篩選** 和 **控制** 規則：

* **篩選** 規則可用來根據條件排除部分目標。 [了解更多資訊](filtering-rules.md)。
* **控制** 規則可讓您在傳送訊息之前檢查訊息的有效性。 [了解更多資訊](control-rules.md)。

「促銷活動最佳化」附加元件提供另外兩種類型 **類型規則**:

* **壓力** 可讓您控制行銷疲勞的規則。 [了解更多資訊](pressure-rules.md)。
* **容量** 可讓您限制負載以保證最佳處理條件的規則。 [了解更多資訊](consistency-rules.md#controlling-capacity)。


>[!NOTE]
>
>如果您使用 **互動** 模組，您也可以建立 **優惠方案簡報** 類型規則，使用簡報規則來控制優惠方案的流程。 [了解更多資訊](../../v8/interaction/interaction-offer.md#offer-presentation)。


## 建立和使用類型的關鍵步驟 {#apply-typologies}

若要建立並使用類型至您的傳送，請遵循下列步驟：

1. 建立類型規則並建立類型，以參考這些規則。
以下章節列出詳細步驟：

   * [篩選規則](filtering-rules.md)
   * [控制規則](control-rules.md)
   * [壓力規則](pressure-rules.md)
   * [容量規則](consistency-rules.md)

1. 設定您的傳送，以使用您建立的類型。 [了解更多資訊](apply-rules.md#apply-a-typology-to-a-delivery)。
1. 透過行銷活動模擬來測試和控制行為。 [了解更多資訊](campaign-simulations.md)。

在準備傳送期間，當符合條件時，會排除收件者。 您可以檢查日誌以監控排除。

有關壓力類型規則的範例使用案例，請參閱 [本頁](pressure-rules.md#use-cases-on-pressure-rules).

## 教學課程影片 {#typologies-video}

### 使用類型規則設定疲勞管理

此影片說明如何運用類型規則，在Adobe Campaign中實作疲勞管理。

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### 使用預先定義的篩選器設定疲勞管理

疲勞管理控制傳訊的頻率和數量，以避免過度向收件者發送請求。 如果您的促銷活動例項中沒有促銷活動最佳化模組，您可以設定預先定義的篩選器，以依據收到的訊息數量篩選目標母體。此影片說明如何使用篩選器在Adobe Campaign中實作疲勞管理。

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
