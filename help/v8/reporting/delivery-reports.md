---
title: Adobe Campaign內建的傳送報表
description: Adobe Campaign內建的傳送報表
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# 傳遞報告 {#delivery-reports}

您可以透過各種可從傳送概述存取的報表來追蹤傳送的執行。

若要存取報表，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Campaigns]** ，然後按一下 **[!UICONTROL Delivery]** 連結以顯示傳送清單。
1. 按一下您要存取之報表的傳送名稱。
1. 選取 **[!UICONTROL Summary]** ，然後按一下 **[!UICONTROL Reports]** 連結以存取傳送專屬的報表。

   ![](assets/detailed-report-2.png)

   依預設，可使用下列報表：

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

此報表結合了在收到傳遞時追蹤收件者行為的關鍵指標。 它提供傳送和接收統計資料、開啟和點進率、產生的點按資料流、網路追蹤，以及分享活動至社交網路。

>[!NOTE]
>
>根據訊息開啟次數計算的值一律會經過估計，因為以文字格式連結至電子郵件的錯誤邊界。 此 **[!UICONTROL Distinct opens/Sum of opens for the population reached]** 指標會將此誤差幅度納入考量。 [了解更多資訊](metrics-calculation.md#tracking-opens-)。

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** :傳遞分析後要傳送的訊息總數。
* **[!UICONTROL Success]** : 已成功處理的訊息數.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>相關百分比是根據成功轉送的訊息數量計算。

* **[!UICONTROL Distinct opens for the population reached]** :估計已至少開啟消息一次的目標接收者的數量。 由於必須開啟電子郵件才能點按連結，因此系統會考慮對追蹤URL的點按次數。
* **[!UICONTROL Sum of opens for the population reached]** :目標收件者開啟總數的估計。
* **[!UICONTROL Clicks on opt-out link]** :取消訂閱連結的點按次數。
* **[!UICONTROL Clicks on the mirror page link]** :連結至的點按次數 [鏡像頁面](../send/mirror-page.md). 若想納入考量，必須在傳送精靈（追蹤的URL）中將連結定義為。
* **[!UICONTROL Estimation of forwards]** :目標收件者轉送的電子郵件估計數。 此值的計算方式是減去不同人員的數量以及在電子郵件中點按的不同收件者數量。

   >[!NOTE]
   >
   >如需不同人員與目標收件者之間差異的詳細資訊，請參閱 [目標人員/收件者](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

此值表格顯示每個網際網路網域的傳送、開啟、點按和原始再活動的劃分。 已使用下列指標：

* **[!UICONTROL Sent]** :在此域上發送的消息總數。
* **[!UICONTROL Complaints]** :收件人報告為不希望的此域的消息數。 此速率是根據在此網域上傳送的訊息總數計算。
* **[!UICONTROL Opens]** :此域中至少開啟一次郵件的不重複目標收件人數。 此速率是根據在此網域上傳送的訊息總數計算。
* **[!UICONTROL Clicks]** :在相同傳送中至少按一下一次的不同目標收件者數目。 此速率是根據在此網域上傳送的訊息總數計算
* **[!UICONTROL Raw reactivity]** :至少按一次傳遞的收件者人數，與至少開啟一次傳遞的收件者人數之比。

>[!NOTE]
>
>此報告中顯示的域名在多維資料集級別使用的明細清單中定義。 若要變更、新增或移除預設網域，請編輯 **[!UICONTROL Domains]** 逐項列出並修改值和別名。 此 **[!UICONTROL Others]** 類別包含不屬於分項清單任何值的網域名稱。
>
>了解如何存取和設定您的分項清單，位於 [本頁](../config/ui-settings.md).


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>相關百分比是根據成功轉送的訊息數量計算。

* **[!UICONTROL Distinct clicks for the population reached]** :已點按至少一次傳遞的不重複人員數量。
* **[!UICONTROL Cumulated clicks]** :目標收件者點按的總次數，不包括取消訂閱連結和鏡像頁面。
* **[!UICONTROL Recipient clicks]** :在相同傳送中至少按一下一次的不同目標收件者數目。
* **[!UICONTROL Estimated recipient reactivity]** :在傳遞中點擊至少一次的接收者數目與至少開啟傳遞一次的估計接收者數目的比率。 退出和鏡像頁面連結上的點按次數並未納入考量。
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

此報告提供傳送的所有主要資訊。

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

本節包含兩個指標：

* **[!UICONTROL Initial population]** :傳遞鎖定的收件者總數。
* **[!UICONTROL Messages rejected by the rule]** :套用類型規則時，分析期間忽略的地址數：地址遺失、隔離、封鎖清單上等。 <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

中圖顯示分析期間拒絕之訊息的每個規則劃分。

**[!UICONTROL Delivery statistics]**

本節包含下列指標：

* **[!UICONTROL Messages to be delivered]** :傳遞分析後要傳送的訊息總數。
* **[!UICONTROL Success]** :已成功處理的郵件數。 關聯速率是要傳遞的報文數的比率。
* **[!UICONTROL Errors]** :傳遞和自動反彈處理期間累積的錯誤總數。 關聯速率是要傳遞的報文數的比率。
* **[!UICONTROL New quarantines]** :傳送失敗後隔離的地址數（用戶未知、無效域）。 關聯速率是要傳遞的報文數的比率。

## 熱點點擊 {#hot-clicks}

此報表顯示訊息內容(HTML和/或文字)，在每個連結上包含點按連結的百分比。 個人化區塊取消訂閱連結、鏡像頁面連結和選件連結會納入累積點按總數中，但不會顯示在報表中。

>[!NOTE]
>
>如果您的傳送包含選件（互動），則報表上方會顯示一個方塊，顯示選件的點按百分比。


## 追蹤統計資料 {#tracking-statistics}

此報表提供開啟、點按和交易的統計資料。

它可讓您追蹤傳送對行銷的影響。 您可以透過變更時標（1小時、3小時或24小時檢視等），來設定值的顯示方式。 按一下 **[!UICONTROL Refresh]** 以確認您的選取。

此報表提供值表和排列圖，顯示傳送達到最高效率所需的時間。 已使用下列指標：

* **[!UICONTROL Opens]** :估計達到已開啟訊息總數百分比所需的時間。 未考慮文字格式的電子郵件。 [了解更多資訊](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]** :預估達到記錄點按總數百分比所需的時間。 點按選擇退出連結和鏡像頁面時不會納入考量。
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 累積報告 {#cumulated-reports}

您可以顯示傳遞的累積報表。 若要這麼做，請選取要比較的傳送，以取得這些傳送的報表清單。

若要從清單中選取非相鄰的傳送，請在選取時按住CTRL鍵。

若要選取儲存在不同資料夾中的傳送，請按一下 **[!UICONTROL Display sub-levels]** 圖示，可在工具列中存取。 然後，它們會顯示在相同的清單中。
