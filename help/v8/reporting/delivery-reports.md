---
title: Adobe Campaign內置交付報告
description: Adobe Campaign內置交付報告
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 9%

---

# 傳遞報告 {#delivery-reports}

您可以通過從交貨概覽訪問的各種報表跟蹤交貨的執行。

要訪問報告，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Campaigns]** ，然後按一下 **[!UICONTROL Delivery]** 連結以顯示交貨清單。
1. 按一下要訪問的報告的傳遞的名稱。
1. 選擇 **[!UICONTROL Summary]** ，然後按一下 **[!UICONTROL Reports]** 連結以訪問特定於傳遞的報告。

   ![](assets/detailed-report-2.png)

   預設情況下，以下報告可用：

   * **[!UICONTROL Delivery throughput]**
   * **[!UICONTROL Sharing to social networks]**
   * **[!UICONTROL Statistics on sharing activities]**
   * **[!UICONTROL Hot clicks]**
   * **[!UICONTROL Tracking statistics]**
   * **[!UICONTROL URLs and click streams]**
   * **[!UICONTROL Tracking indicators]**
   * **[!UICONTROL Non-deliverables and bounces]**
   * **[!UICONTROL User activities]**
   * **[!UICONTROL Delivery summary]**
   * **[!UICONTROL Subscription tracking]**
   * **[!UICONTROL Delivery statistics]**
   * **[!UICONTROL Breakdown of opens]**

## 追蹤指標 {#tracking-indicators}

此報表合併了用於跟蹤接收者在接收交貨時的行為的主要指標。 它可以存取傳遞和接收統計資料、開啟及點進率、產生的點按資料流、網頁追蹤以及與社交網路的分享活動。

>[!NOTE]
>
>基於消息開啟計算的值總是估計，因為以文本格式連結到電子郵件的錯誤邊距。 的 **[!UICONTROL Distinct opens/Sum of opens for the population reached]** 指標將這一誤差範圍考慮在內。 [了解更多](metrics-calculation.md#tracking-opens-)。

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** :傳遞分析後要傳遞的郵件總數。
* **[!UICONTROL Success]** : 已成功處理的訊息數.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>根據成功轉發的消息數計算相關百分比。

* **[!UICONTROL Distinct opens for the population reached]** :至少一次開啟消息的目標接收者的數目的估計。 由於必須開啟電子郵件以按一下連結，因此將考慮對跟蹤的URL的按一下。
* **[!UICONTROL Sum of opens for the population reached]** :目標接收者開啟總次數的估計。
* **[!UICONTROL Clicks on opt-out link]** :取消訂閱連結上的按一下次數。
* **[!UICONTROL Clicks on the mirror page link]** :指向的連結的按一下次數 [鏡像頁](../send/mirror-page.md)。 要考慮到這一點，必須在傳遞嚮導（跟蹤的URL）中將連結定義為這樣。
* **[!UICONTROL Estimation of forwards]** :目標收件人轉發的電子郵件數的估計。 此值通過減去在電子郵件中按一下的不同人員的數量和不同收件人的數量來計算。

   >[!NOTE]
   >
   >有關不同人員和目標收件人之間差異的詳細資訊，請參閱 [目標人員/收件人](metrics-calculation.md#targeted-persons---recipients)。

**[!UICONTROL 3. Open and click-through rate]**

此表顯示每個Internet域的交付、開啟、點擊和原始反應性的分解。 使用以下指標：

* **[!UICONTROL Sent]** :在此域上發送的消息總數。
* **[!UICONTROL Complaints]** :收件人報告為不希望接收的此域的郵件數。 該速率根據在此域上發送的消息總數計算。
* **[!UICONTROL Opens]** :此域至少開啟一次郵件的不同目標收件人數。 該速率根據在此域上發送的消息總數計算。
* **[!UICONTROL Clicks]** :按一下同一傳遞至少一次的不同目標收件人數。 此速率是根據在此域上發送的消息總數計算的
* **[!UICONTROL Raw reactivity]** :在傳遞中按一下至少一次的收件人數與開啟傳遞至少一次的收件人數的百分比。

>[!NOTE]
>
>此報告中顯示的域名在多維資料集級別使用的明細清單中定義。 要更改、添加或刪除預設域，請編輯 **[!UICONTROL Domains]** 逐項列出並修改值和別名。 的 **[!UICONTROL Others]** 類別包括不屬於明細清單任何值的域名。
>
>瞭解如何在中訪問和配置枚舉 [此頁](../config/ui-settings.md)。


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>根據成功轉發的消息數計算相關百分比。

* **[!UICONTROL Distinct clicks for the population reached]** :點擊遞送至少一次的不同人數。
* **[!UICONTROL Cumulated clicks]** :按目標收件人（不包括未訂閱連結和鏡像頁）按一下的總數。
* **[!UICONTROL Recipient clicks]** :按一下同一傳遞至少一次的不同目標收件人數。
* **[!UICONTROL Estimated recipient reactivity]** :在遞送中點擊至少一次的收件人數目與開啟遞送至少一次的估計收件人數目之比。 按一下「選擇退出」和「鏡像」頁面連結時，不會考慮這些連結。
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]** : Number of web pages visited following message reception.
* **[!UICONTROL Transactions]** : Number of purchases following message reception.
* **[!UICONTROL Total amount]** : Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]** : Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]** : Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]** : Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]** : Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]** : Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]** : Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]** : Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]** : This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]** : Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]** : Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## 傳遞摘要 {#delivery-summary}

此報告提供有關交貨的所有主要資訊。

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

本節有兩個指標：

* **[!UICONTROL Initial population]** :傳遞目標的收件人總數。
* **[!UICONTROL Messages rejected by the rule]** :應用類型規則時在分析期間忽略的地址數：地址丟失、隔離、拒絕清單等。 <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

中間圖表顯示分析期間拒絕的消息的每個規則的細分。

**[!UICONTROL Delivery statistics]**

本節包括以下指標：

* **[!UICONTROL Messages to be delivered]** :傳遞分析後要傳遞的郵件總數。
* **[!UICONTROL Success]** :成功處理的消息數。 關聯速率是要傳遞的消息數的比率。
* **[!UICONTROL Errors]** :在交貨和自動回彈處理期間累積的錯誤總數。 關聯速率是要傳遞的消息數的比率。
* **[!UICONTROL New quarantines]** :傳遞失敗後隔離的地址數（用戶未知，無效域）。 關聯速率是要傳遞的消息數的比率。

## 熱點點擊 {#hot-clicks}

此報告顯示訊息內容 (HTML 和/或文字) 以及每個連結的連結點按百分比。個人化區塊取消訂閱連結、鏡像頁面連結和優惠連結有計入總累計點按數，但不顯示在報告中。

>[!NOTE]
>
>如果您的交貨包含優惠（交互），則報表上方會顯示一個框，其中顯示優惠的按一下百分比。


## 追蹤統計資料 {#tracking-statistics}

此報表提供有關開啟、按一下和事務的統計資訊。

它讓您跟蹤交付對市場營銷的影響。 您可以通過更改時間刻度（1小時、3小時或24小時視圖等）來配置值的顯示方式。 按一下 **[!UICONTROL Refresh]** 以確認您的選取。

此報表提供值表和帕累托圖，其中顯示交貨達到最高效率所需的時間。 使用以下指標：

* **[!UICONTROL Opens]** :估計達到開啟郵件總數百分比所需的時間。 不考慮文本格式的電子郵件。 [了解更多](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]** :估計達到記錄的點擊總數百分比所需的時間。 按一下「opt-out（選擇退出）」連結時，鏡像頁面不會被考慮在內。
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 累積報告 {#cumulated-reports}

您可以顯示交貨的累計報表。 為此，請選擇要比較的交貨，以獲取這些交貨的報表清單。

要從清單中選擇非相鄰交貨，請在進行選擇時按住CTRL鍵。

要選擇保存在其他資料夾中的交貨，請按一下 **[!UICONTROL Display sub-levels]** 表徵圖。 然後，它們將顯示在同一清單中。
