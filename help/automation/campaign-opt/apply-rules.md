---
product: campaign
title: 套用型別規則
description: 瞭解如何套用型別規則
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 9%

---

# 套用型別規則{#applying-rules}

## 將型別套用至傳遞 {#apply-a-typology-to-a-delivery}

若要套用您建立的型別規則，請將其與型別建立關聯，然後在傳送中參考此型別。

要執行此操作，請遵循下列步驟：

1. 建立行銷活動型別。

   型別可透過以下方式存取： **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** Campaign檔案總管的資料夾。

1. 前往 **[!UICONTROL Rules]** 索引標籤，按一下 **[!UICONTROL Add]** 按鈕，並選取要與此型別套用的規則。

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. 儲存型別：是否將其新增至現有型別的清單。
1. 開啟您要套用規則的傳遞。
1. 瀏覽至傳遞屬性並開啟 **[!UICONTROL Typology]** 標籤。
1. 在下拉式清單中選取型別。

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >可以在傳遞範本中定義類型，以便自動套用至使用此範本建立的所有傳送。

## 定義應用程式條件 {#define-application-conditions}

您可以視需要限制規則的應用程式欄位（控制規則除外）。

您可以設定型別規則，使其僅涉及所連結的特定傳遞，或傳遞目標中的特定收件者。

若要定義規則的應用程式條件，請按一下 **[!UICONTROL Edit the rule application conditions...]** 中的連結 **[!UICONTROL General]** 標籤。

然後使用查詢編輯器來定義篩選條件。 在以下範例中，容量規則僅涉及其標籤中包含「offer」字樣的傳送，或是在2013年4月1日之前建立的傳送。

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>對於篩選規則，您可以選取篩選條件的套用條件：它們可以取決於傳遞或傳遞大網。 [了解更多](filtering-rules.md#condition-a-filtering-rule)。

## 調整計算頻率 {#adjust-calculation-frequency}

每晚都會透過資料庫清理工作流程自動重新執行仲裁。 不過，在此期間之後可儲存值。

事實上，有些計算會使用不會每日變更的值。 因此，每天重新計算資料與讓資料庫過載毫無關係。 例如，如果程式每週都透過客戶傾向評分和購買資訊來豐富行銷資料庫，則不需要每天重新計算基於這些值的資料。

若要這麼做， **[!UICONTROL Frequency]** 的欄位 **[!UICONTROL General]** tab可讓您定義儲存目標定位的最長時段。 根據預設，值 **0** 表示在下次執行每日重新仲裁之前，計算仍有效。

若要在此期間之後儲存結果，請在 **[!UICONTROL Frequency]** 欄位：此期間過期後，所有規則都會重新套用。

此 **[!UICONTROL Re-apply the rule at the start of personalization]** 選項可讓您在個人化階段期間自動套用規則，包括 **[!UICONTROL Frequency]** 欄位仍然有效。

## 選取規則應用程式階段 {#selecting-the-rule-application-phase}

型別規則會在相關傳遞的鎖定、分析和個人化階段中，以特定順序套用。

### 執行順序 {#execution-order}

在標準操作模式下，會依下列順序套用規則：

1. 控制規則（如果這些規則是在定位開始時套用）。
1. 篩選規則：

   * 位址資格的原生應用程式規則：封鎖清單/隔離位址/位址品質上定義的地址/未驗證的位址/位址。
   * 篩選由使用者定義的規則。
   * 地址或識別碼上的重複資料刪除規則（必要時套用）。

1. 壓力規則.
1. 容量規則。
1. 控制規則（如果這些規則是在定位結束時套用）。
1. 控制規則（如果這些規則是在個人化開始時套用）。如果使用者規則（篩選/壓力/電容性）已過期且需要重新計算，則會在此步驟中套用。
1. 控制規則（如果這些規則適用於個人化結束時）。

>[!NOTE]
>
>如果您使用Campaign互動模組，優惠方案適用性規則會在篩選規則（適用於傳遞大網中的優惠方案）的同時套用，或在個人化階段期間、呼叫優惠方案引擎期間套用。

您可以使用中的適當欄位，調整具有相同型別之規則的執行順序 **[!UICONTROL General]** 標籤中指定的「規則」。 在同一訊息處理階段執行數個規則時，您可在以下位置設定其執行順序： **[!UICONTROL Execution sequence]** 欄位。

例如，執行順序為20的壓力規則會在執行順序為30的壓力規則之前執行。

### 控制規則 {#control-rules}

對象 **[!UICONTROL Control]** 規則，您可以決定套用規則的傳送生命週期的哪個時間點：定位之前或之後、個人化開始時、分析結束時。 選取要在的下拉式清單中套用的值 **[!UICONTROL Phase]** 欄位，在 **[!UICONTROL General]** 型別規則的索引標籤。

![](assets/campaign_opt_define_control_phase.png)

可能的值包括：

* **[!UICONTROL At the start of targeting]**

   若要防止發生錯誤時執行個人化步驟，您可以在此處套用控制規則。

* **[!UICONTROL After targeting]**

   如果您需要知道目標的音量才能套用控制規則，請選取此階段。

   例如， **[!UICONTROL Check proof size]** 控制規則適用於每個目標定位階段之後：如果校樣收件者過多，此規則會防止訊息個人化。

* **[!UICONTROL At the start of personalization]**

   如果控制涉及訊息個人化的核准，則必須選取此階段。 訊息個人化會在分析階段中執行。

* **[!UICONTROL At the end of the analysis]**

   當檢查要求完成訊息個人化時，請選取此階段。

## 其他設定 {#additional-configurations}

### 控制傳出SMTP流量 {#control-outgoing-smtp-traffic}

您可選擇使用 **[!UICONTROL Managing affinities with IP addresses]** 此相似性將傳遞連結至傳遞伺服器(MTA)的欄位。 這可讓您限制向電腦或輸出地址傳送特定內容的電子郵件數量。

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>相似性管理不適用於 **[!UICONTROL Filtering]** 型別。

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### Campaign最佳化和分散式行銷 {#campaign-optimization-and-distributed-marketing}

此 **[!UICONTROL Distributed Marketing]** 索引標籤可讓您定義重新對應型別和/或規則，以便在訂購和/或保留共用行銷活動時套用。 為本機實體定義的型別/規則（連結至為中央實體定義的型別/規則）會取代連結至中央實體的規則/型別。 重新對應可讓您將中央實體規則調整為適合訂購行銷活動的本地實體。

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>在型別與型別規則中， **[!UICONTROL Distributed Marketing]** 標籤會新增如果您的授權包含此選項：請檢查您的授權合約。\
>如需分散式行銷的詳細資訊，請參閱 [本節](../distributed-marketing/about-distributed-marketing.md).
