---
title: Adobe Campaign內建傳遞報告
description: Adobe Campaign內建傳遞報告
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 12%

---

# 傳遞報告 {#delivery-reports}

您可以透過傳遞概述中可存取的各種報告，追蹤傳遞的執行情況。

若要存取報表，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Campaigns]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Delivery]**&#x200B;連結以顯示傳遞清單。
1. 按一下您要存取報告的傳遞名稱。
1. 選取「**[!UICONTROL Summary]**」標籤，然後按一下「**[!UICONTROL Reports]**」連結以存取傳遞的特定報告。

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

此報表結合關鍵指標，用於追蹤收件者在接收傳遞時的行為。 它可以存取傳遞和接收統計資料、開啟及點進率、產生的點按資料流、網頁追蹤以及與社交網路的分享活動。

>[!NOTE]
>
>根據訊息開啟計算出的值一律為預估值，因為連結至文字格式電子郵件的錯誤邊界。 **[!UICONTROL Distinct opens/Sum of opens for the population reached]**&#x200B;指標會將此錯誤邊界列入考量。 [了解更多](metrics-calculation.md#tracking-opens-)。

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]**：傳遞分析後要傳遞的訊息總數。
* **[!UICONTROL Success]**：已成功處理的訊息數。

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>相關百分比是根據成功轉送的訊息數量計算。

* **[!UICONTROL Distinct opens for the population reached]**：已開啟訊息至少一次的目標收件者人數預估值。 由於必須開啟電子郵件才能點按連結，因此會考量追蹤URL的點按次數。
* **[!UICONTROL Sum of opens for the population reached]**：目標收件者開啟的總數預估值。
* **[!UICONTROL Clicks on opt-out link]**：對取消訂閱連結的點按次數。
* **[!UICONTROL Clicks on the mirror page link]**：點按[映象頁面](../send/mirror-page.md)連結的次數。 若要將納入考量，必須在傳送精靈（追蹤的URL）中定義連結。
* **[!UICONTROL Estimation of forwards]**：目標收件者轉寄的電子郵件預估數量。 此值的計算方式為減去相異人數與按一下電子郵件之相異收件者人數。

  >[!NOTE]
  >
  >如需不同對象和目標收件者之間差異的詳細資訊，請參閱[目標對象/收件者](metrics-calculation.md#targeted-persons---recipients)。

**[!UICONTROL 3. Open and click-through rate]**

此值表格顯示每個網域的分割傳遞次數、開啟次數、點按次數及原始反應性。 使用下列指標：

* **[!UICONTROL Sent]**：在這個網域上傳送的訊息總數。
* **[!UICONTROL Complaints]**：收件者回報此網域不想要的訊息數。 此速率是根據此網域上傳送的訊息總數所計算。
* **[!UICONTROL Opens]**：此網域已開啟郵件至少一次的不同目標收件者數目。 此速率是根據此網域上傳送的訊息總數所計算。
* **[!UICONTROL Clicks]**：至少點按一次相同傳遞的不同目標收件者數目。 此速率是根據此網域上傳送的訊息總數所計算
* **[!UICONTROL Raw reactivity]**：與開啟傳遞至少一次的收件者人數相比，至少點選一次傳遞的收件者人數的百分比。

>[!NOTE]
>
>此報告中顯示的網域名稱是在多維資料庫層級使用的分項清單中定義。 若要變更、新增或移除預設網域，請編輯&#x200B;**[!UICONTROL Domains]**&#x200B;專案清單，並修改值與別名。 **[!UICONTROL Others]**&#x200B;類別包含不屬於任何專案清單值的網域名稱。
>
>在[此頁面](../config/ui-settings.md)中瞭解如何存取及設定您的分項清單。


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>相關百分比是根據成功轉送的訊息數量計算。

* **[!UICONTROL Distinct clicks for the population reached]**：在傳遞中按一下至少一次的不同人數。
* **[!UICONTROL Cumulated clicks]**：目標收件者的點按總數，不包括取消訂閱連結和映象頁面。
* **[!UICONTROL Recipient clicks]**：至少點按一次相同傳遞的不同目標收件者數目。
* **[!UICONTROL Estimated recipient reactivity]**：在傳遞中至少點按一次的收件者人數，與開啟傳遞至少一次的估計收件者人數之間的比率。 在選擇退出和映象頁面連結上的點選次數不會考慮在內。
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]**: Number of web pages visited following message reception.
* **[!UICONTROL Transactions]**: Number of purchases following message reception.
* **[!UICONTROL Total amount]**: Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]**: Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]**: Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]**: Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]**: Average amount of purchases generated per message.

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

* **[!UICONTROL Reactivity]**: Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]**: Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]**: Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]**: This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]**: Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]**: Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## 傳遞摘要 {#delivery-summary}

此報表提供有關傳遞的所有主要資訊。

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

本節提供兩種指標：

* **[!UICONTROL Initial population]**：傳遞所定位的收件者總數。
* **[!UICONTROL Messages rejected by the rule]**：套用型別規則時，分析期間忽略的地址數：地址遺失、隔離、封鎖清單上等。<!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

中間圖表顯示分析期間拒絕之訊息的每條規則劃分。

**[!UICONTROL Delivery statistics]**

本節包含下列指標：

* **[!UICONTROL Messages to be delivered]**：傳遞分析後要傳遞的訊息總數。
* **[!UICONTROL Success]**：已成功處理的訊息數。 關聯率是要傳遞訊息數量的比率。
* **[!UICONTROL Errors]**：在傳遞和自動復原處理期間累積的錯誤總數。 關聯率是要傳遞訊息數量的比率。
* **[!UICONTROL New quarantines]**：在傳送失敗（使用者不明、網域無效）後隔離的地址數。 關聯率是要傳遞訊息數量的比率。

## 熱點點擊 {#hot-clicks}

此報告顯示訊息內容 (HTML 和/或文字) 以及每個連結的連結點按百分比。個人化區塊取消訂閱連結、鏡像頁面連結和產品建議連結有計入總累計點按數，但不顯示在報告中。

>[!NOTE]
>
>如果您的傳送包含優惠方案（互動），報表上方部分會顯示一個方塊，顯示優惠方案的點按百分比。


## 追蹤統計資料 {#tracking-statistics}

此報表提供有關開啟、點按和交易的統計資料。

它可讓您追蹤傳送的行銷影響。 您可以透過變更時幅（1小時、3小時或24小時檢視等）來設定值的顯示方式。 按一下&#x200B;**[!UICONTROL Refresh]**&#x200B;以確認您的選擇。

此報表提供值表格和柏瑞圖圖表，顯示傳遞達到最高效率所需的時間。 使用下列指標：

* **[!UICONTROL Opens]**：達到開啟的訊息總數百分比所需時間的預估值。 不考慮文字格式的電子郵件。 [了解更多](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]**：達到所記錄點按總數百分比所需時間的預估值。 在選擇退出連結和映象頁面上的點選次數不會考慮在內。
<!--
* **[!UICONTROL Transactions]**: Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 累積報告 {#cumulated-reports}

您可以顯示傳遞的累積報告。 要執行此操作，請選取要比較的傳送，以取得這些傳送的報告清單。

若要從清單中選取不相鄰的傳送，請在進行選取時按住CTRL鍵。

若要選取儲存在不同資料夾中的傳送，請按一下工具列中的&#x200B;**[!UICONTROL Display sub-levels]**&#x200B;圖示。 然後它們會顯示在相同的清單中。
