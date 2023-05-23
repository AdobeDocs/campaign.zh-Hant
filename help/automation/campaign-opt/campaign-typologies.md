---
product: campaign
title: 開始活動類型
description: 瞭解如何配置和實施促銷活動類型
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 19%

---

# 開始活動類型{#about-campaign-typologies}

**市場活動優化** 是Adobe Campaign模組，它允許您控制、過濾和監控送貨的發送。 為了避免行銷活動之間發生衝突，Adobe Campaign 可以套用特定限制規則來測試各種組合。這樣可確保傳送的訊息符合客戶和公司通訊政策的需求及期望。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#typologies-video)

>[!NOTE]
>
>根據您的產品，市場活動優化可以包括或附加項。 請檢查您的授權合約。

## 分類規則和類型 {#typology-rules}

預設情況下，「活動」帶有內置類型和類型規則。

類型是在傳遞分析期間應用於所有消息的一組驗證規則。

市場活動類型可以包含多個類型規則，但交付只能引用一個類型。

在 **[!UICONTROL Administration > Campaign management > Typology management]** 市場活動瀏覽器的資料夾。

對於每種類型， **[!UICONTROL Rules]** 頁籤中，您可以添加、刪除或查看要應用的類型規則。

![](assets/campaign_opt_rules_tab.png)

一旦建立了類型規則，就會在市場活動中分組 **類型** 在交貨中引用。 [了解更多](#apply-typologies)。


市場活動附帶一組預設 **篩選** 和 **控制項** 規則：

* **篩選** 規則用於根據條件排除目標的一部分。 [了解更多](filtering-rules.md)。
* **控制項** 規則允許您在發送消息之前檢查其有效性。 [了解更多](control-rules.md)。

「市場活動優化」附加模組提供了兩種附加類型 **類型規則**:

* **壓力** 可以控制市場疲勞的規則。 [了解更多](pressure-rules.md)。
* **容量** 規則，允許您限制載荷以確保最佳處理條件。 [了解更多](consistency-rules.md#controlling-capacity)。


>[!NOTE]
>
>如果使用 **交互** 模組，您還可以建立 **提供演示文稿** 類型規則，使用表示規則控制提供建議的流。 [了解更多](../../v8/interaction/interaction-offer.md#offer-presentation)。


## 建立和使用類型的關鍵步驟 {#apply-typologies}

要為交貨建立和使用類型，請執行以下步驟：

1. 建立類型規則並建立類型以將它們引入其中。
詳細步驟列於以下部分：

   * [篩選規則](filtering-rules.md)
   * [控制規則](control-rules.md)
   * [壓力規則](pressure-rules.md)
   * [容量規則](consistency-rules.md)

1. 將交貨配置為使用您建立的類型。 [了解更多](apply-rules.md#apply-a-typology-to-a-delivery)。
1. Test並通過戰役模擬控制行為。 [了解更多](campaign-simulations.md)。

在交付準備期間，當滿足標準時，接收者被排除。 您可以檢查日誌以監控排除。

有關壓力類型規則的示例使用案例，請參見 [此頁](pressure-rules.md#use-cases-on-pressure-rules)。

## 教學課程影片 {#typologies-video}

### 使用類型規則設定疲勞管理

此視頻說明了如何利用分類規則在Adobe Campaign實施疲勞管理。

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### 使用預定義篩選器設定疲勞管理

疲勞管理控制傳訊的頻率和數量，以避免過度向收件者發送請求。 如果您的市場活動實例中沒有市場活動優化模組，則可以配置一個預定義的篩選器，該篩選器將按接收的消息數篩選目標群體。此視頻說明如何使用篩選器在Adobe Campaign實施疲勞管理。

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
