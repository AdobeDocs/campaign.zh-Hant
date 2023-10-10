---
title: Adobe Campaign全域報告
description: 瞭解如何存取及使用全域報告
feature: Reporting, Monitoring
role: User, Data Engineer
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1763'
ht-degree: 8%

---

# 全域報告 {#global-reports}

這些報表會說明整個資料庫中的資料活動。 若要檢視報表控制面板，請前往 **[!UICONTROL Reports]** 標籤。

![](assets/reports-tab.png)

若要顯示報表，請按一下其名稱。 預設會提供下列報表：

![](assets/report-global-list.png)

>[!NOTE]
>
>本區段僅顯示連結至傳遞的報告。

* **[!UICONTROL Delivery throughput]** ：請參閱 [傳遞總處理能力](#delivery-throughput).
* **[!UICONTROL Browsers]** ：請參閱 [瀏覽器](#browsers).
* **[!UICONTROL Sharing to social networks]** ：請參閱 [分享至社交網路](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]** ：請參閱 [共用活動的統計資料](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]** ：請參閱 [作業系統](#operating-systems).
* **[!UICONTROL URLs and click streams]** ：請參閱 [URL和點按流量](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]** ：請參閱 [追蹤指標](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]** ：請參閱 [無法傳遞的專案和退信](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]** ：請參閱 [使用者活動](#user-activities).
* **[!UICONTROL Subscription tracking]** ：請參閱 [訂閱追蹤](#subscription-tracking).
* **[!UICONTROL Delivery summary]** ：請參閱 [傳遞摘要](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]** ：請參閱 [傳遞統計資料](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]** ：請參閱 [開啟的劃分](#breakdown-of-opens).

## 傳遞總處理能力 {#delivery-throughput}

此報表包含指定期間內整個平台的傳遞輸送量資訊。 若要測量訊息傳遞的速度，標準是每小時傳送的訊息數和訊息的大小 (以位元/秒為單位)。在下面的範例中，第一個圖表以藍色顯示成功傳遞，以橘色顯示錯誤傳遞的數量。

![](assets/report-toolbar.png)

您可以透過變更時程來設定顯示的值：1小時檢視、3小時檢視、24小時檢視等。 按一下 **[!UICONTROL Refresh]** 以確認您的選取。

>[!NOTE]
>
>您也可以使用監控每小時傳送的傳遞數目 [控制面板](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html).
>
>所有管理員使用者都可存取控制面板。 授予使用者管理員存取權限的步驟已詳載於[本頁](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hant#discover-control-panel)中。
>

## 使用者活動 {#user-activities}

此報表以圖表形式顯示每半小時、每小時或每日的開啟、點按及交易劃分。

可以使用以下選項：

* **[!UICONTROL Opens]** ：已開啟的訊息總數。 不考慮文字格式的電子郵件。 [了解更多](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]** ：傳遞中連結的點按總數。 對取消訂閱連結和映象頁面的點選次數不會考慮在內。
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## 傳遞失敗和退回次數 {#non-deliverables-and-bounces}

此報表顯示無法傳遞的劃分以及每個網域退信的劃分。

此 **[!UICONTROL Number of messages processed]** 代表傳遞伺服器處理的訊息總數。 此值低於某些傳遞已停止或暫停（在伺服器處理之前）時要傳遞的訊息數。

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>此報告中顯示的錯誤會觸發隔離程式。 有關隔離管理的詳細資訊，請參閱 [隔離管理](../send/quarantines.md).

此報表的第一區段以值表格和圖表的形式顯示無法傳遞專案的劃分。

針對每種錯誤型別，我們有：

* 此型別的錯誤訊息數目，
* 與含有錯誤的訊息總數相較之下，含有此型別錯誤的訊息百分比。
* 此型別的錯誤訊息佔已處理訊息總數的百分比。

使用下列指標：

* **[!UICONTROL User unknown]** ：傳送期間產生的錯誤型別，用以指出電子郵件地址無效。
* **[!UICONTROL Invalid domain]** ：傳送傳遞時產生的錯誤型別，用以指出電子郵件地址的網域錯誤或不存在。
* **[!UICONTROL Inbox full]** ：在嘗試傳送五次後產生的錯誤型別，以指出收件者的收件匣包含太多訊息。
* **[!UICONTROL Account disabled]** ：傳送傳遞時產生的錯誤型別，用以指出地址已不存在。
* **[!UICONTROL Rejected]** ：當IAP （網際網路存取提供者）拒絕位址時產生的錯誤型別，例如在套用安全性規則（反垃圾郵件軟體）之後。
* **[!UICONTROL Unreachable]** ：訊息發佈字串中發生的錯誤型別：SMTP轉送上的事件、暫時無法連線網域等
* **[!UICONTROL Not connected]** ：錯誤型別，表示收件者的行動電話在傳送時已關閉或已中斷與網路的連線。

  >[!NOTE]
  >
  >此指標與上的傳遞相關 [行動裝置頻道](../send/send.md) 僅限。

  您可以按一下 `[+]` 符號。 對於每個錯誤型別，您可以依網域顯示錯誤訊息的劃分。

**[!UICONTROL Breakdown of errors per domain]**

此報表的第二個區段以值表格和圖表的形式，顯示每個網域之錯誤的劃分資訊。

對於每個網域名稱，我們有：

* 這個網域有錯誤的訊息數目，
* 這個網域發生錯誤的訊息佔這個網域處理的訊息總數百分比，
* 此網域的錯誤訊息佔錯誤訊息總數的百分比。

您可以按一下 [+] 符號。 對於每個網域型別，您可以依錯誤型別顯示錯誤訊息的劃分。

![](assets/errors-report-details.png)

>[!NOTE]
>
>此報告中顯示的網域名稱是在多維資料庫層級定義的。 若要變更這些值，請編輯 **[!UICONTROL Delivery logs (broadlogrcp)]** 立方體。 如需詳細資訊，請參閱[本章節](gs-cubes.md)。此 **[!UICONTROL Others]** 類別包含不屬於特定類別的網域名稱。

## 瀏覽器 {#browsers}

此報表顯示相關期間內傳遞收件者所使用之網際網路瀏覽器的劃分。

>[!NOTE]
>
>此報表中顯示的值是預估值：僅納入已點按傳送的收件者。

**全域統計資料**

瀏覽器使用的全域統計資料會以值表格和圖表的形式呈現。

![](assets/browser-report.png)

使用下列指標：

* **[!UICONTROL Visitors]** ：已鎖定目標（每個網際網路瀏覽器）並已至少點按一次傳送的收件者總數。
* **[!UICONTROL Pages viewed]** ：所有傳遞的在傳遞中點按連結總數（每個網際網路瀏覽器）。
* **[!UICONTROL Usage rate]** ：此比率代表訪客（每個網際網路瀏覽器）相對於訪客總數的劃分。

**每個瀏覽器的統計資料**

在全域統計值表格中，您可以按一下每個瀏覽器名稱來檢視其使用統計值。

![](assets/browser-report-info.png)

統計資料會以曲線、圖表和值表的形式呈現。

此 **[!UICONTROL History]** 曲線代表此瀏覽器每日的出勤率。 此比率是每日訪客數（在此瀏覽器上）與出席率最高的當日所測量訪客數之間的比率。

此 **[!UICONTROL Breakdown per version]** 圖表代表每個版本的訪客與訪客總數（在此瀏覽器上）的比較。

值表使用以下指標：

* **[!UICONTROL Global rate]** ：此比率代表每個版本的訪客與訪客總數（在所有瀏覽器上）的比較。
* **[!UICONTROL Relative rate]** ：此比率代表每個版本的訪客與訪客總數（在此瀏覽器上）的比較。


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## 作業系統 {#operating-systems}

此報表顯示相關期間內傳遞收件者使用的作業系統劃分。

>[!NOTE]
>
>此報表中顯示的值是預估值：僅納入已點按傳送的收件者。

**全域統計資料**

作業系統的全域使用統計資料會以值表和圖表的形式呈現。

![](assets/os-report.png)

使用下列指標：

* **[!UICONTROL Visitors]** ：在傳遞中至少點按一次的目標收件者總數（每個作業系統）每日平均數。
* **[!UICONTROL Pages viewed]** ：所有傳遞的傳遞連結（每個作業系統）每日平均點按總數。
* **[!UICONTROL Rate of use]** ：此比率代表相對於訪客總數的訪客劃分（每個作業系統）。

**每個作業系統的統計資料**

在全域統計值表格中，按一下每個作業系統的名稱，即可檢視每個作業系統的統計值。

![](assets/os-report-details.png)

統計資料會以曲線、圖表和值表的形式呈現。

此 **[!UICONTROL History]** 曲線代表每日使用此作業系統的速率。 此比率是每日訪客數（在此作業系統上）與出席人數最多當日所測量訪客數的比率。

此 **[!UICONTROL Breakdown by version]** 圖表代表每個版本與此作業系統上的訪客總數相關的訪客劃分。

值表使用以下指標：

* **[!UICONTROL Global rate]** ：此比率代表訪客（每個版本）與整個作業系統的訪客總數之間的劃分。
* **[!UICONTROL Relative rate]** ：此比率代表此作業系統的訪客總數（每個版本）的劃分情況。

## 訂閱追蹤 {#subscription-tracking}

此報表可讓您監視資訊服務的訂閱。 它會顯示訂閱和取消訂閱。

![](assets/service-report.png)

按一下 **[!UICONTROL Profiles and targets > Services and subscriptions]** 首頁或檔案總管的節點。 選取所需的訂閱，然後按一下 **[!UICONTROL Reports]** 標籤。 此 **[!UICONTROL Subscriptions tracking]** 報告預設為可用。 它可讓您檢視一段時間內的訂閱和取消訂閱趨勢以及熟客率。 您可以透過下拉式清單設定此資料的表示方式。 按一下 **[!UICONTROL Refresh]** 以驗證選取的組態。

如需詳細資訊，請參閱[本頁面](../start/subscriptions.md)。

此 **[!UICONTROL Number subscribed to date]** 代表目前訂閱的總人數。

**[!UICONTROL Overall evolution of subscriptions]**

值表使用以下指標：

* **[!UICONTROL Subscribers]** ：相關期間的訂閱者總數。
* **[!UICONTROL Subscriptions]** ：相關期間的訂閱數目。
* **[!UICONTROL Unsubscriptions]** ：相關期間的取消訂閱數。
* **[!UICONTROL Evolution]** ：取消訂閱數減去訂閱數。 費率是根據訂閱者總數所計算。
* **[!UICONTROL Loyalty]** ：相關期間訂閱者的忠誠度比率。

**[!UICONTROL Subscription evolution curves]**

此圖表顯示相關期間的訂閱和取消訂閱的演變。

## 傳遞統計資料 {#delivery-statistics}

此報表顯示依網際網路網域、所有已處理和已傳送訊息、硬退信和軟退信、開啟、點按和取消訂閱的劃分資訊。

![](assets/broadcast-report.png)

使用下列指標：

* **[!UICONTROL Emails processed]** ：傳遞伺服器處理的訊息總數。
* **[!UICONTROL Delivered]** ：成功處理的訊息數與已處理的訊息總數相比的百分比。
* **[!UICONTROL Hard bounces]** ：與已處理的訊息總數相比的「硬」退回次數百分比。
* **[!UICONTROL Soft bounces]** ：與已處理的訊息總數相比的「軟」退回次數百分比。

  >[!NOTE]
  >
  >有關硬跳出和軟跳出的詳細資訊，請參閱 [此頁面](../send/quarantines.md).

* **[!UICONTROL Opens]** ：與成功處理的訊息數相比，至少開啟過一次訊息的目標收件者人數的百分比。
* **[!UICONTROL Clicks]** ：與成功處理的訊息數相比，至少一次點按傳送的人員數百分比。
* **[!UICONTROL Unsubscription]** ：與成功處理的訊息數相比的取消訂閱連結點選數百分比。

## 開啟次數的劃分 {#breakdown-of-opens}

此報表顯示相關期間內依作業系統、裝置和瀏覽器劃分的開啟專案。 每個類別有兩個圖表。第一個圖表顯示在電腦和行動裝置上的開啟數統計資料。第二個圖表僅顯示在行動裝置上的開啟數統計資料。

開啟次數與開啟的訊息總數相對應。 不計入文字格式的電子郵件。 有關追蹤開啟的詳細資訊，請參閱 [本節](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>瀏覽器和作業系統名稱構成了已開啟訊息的瀏覽器使用者代理程式所傳送的部分資訊。 Adobe Campaign會使用其裝置資訊來推斷裝置型別。
