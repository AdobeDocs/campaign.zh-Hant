---
title: 傳送及監視您的電子郵件
description: 瞭解使用Adobe Campaign傳送電子郵件的範圍和特性
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---


# 傳送及監視您的電子郵件

當傳送已設定好並準備好傳送時，請確定您已執行傳送分析。 [了解更多](delivery-analysis.md)

完成後，確認傳送以啟動訊息傳送。

從追蹤傳送的執行 **傳遞** 索引標籤，可透過此傳送的詳細資訊或傳送清單存取。

## 監視您的電子郵件

傳送後，在傳送控制面板中檢查您的傳送狀態，並存取傳送記錄檔及報告，以確認訊息已正確傳送。

![](../assets/do-not-localize/book.png) [在 Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## Campaign MTA {#mta}

Campaign v8郵件傳輸代理程式(MTA)提供同級最佳的傳送基礎架構，以實現最佳傳遞能力、信譽、輸送量、報告、跳出處理、IP提升和連線設定管理。

此服務適用於所有Campaign v8客戶，可保證擴充性、高傳遞輸送量，並有助於更快速地傳送更多電子郵件。 這是透過新的適應性傳送技術達成，該技術會根據網際網路服務提供者的意見來即時變更電子郵件傳送設定。

### 好處

Adobe Campaign使用郵件傳輸代理程式(MTA)，執行SparkPost的商業電子郵件MTA，稱為 **動量**.

Momentum代表創新的高效能MTA技術，包括更聰明的彈回處理以及自動化傳遞能力最佳化功能，可協助寄件者達成並維持最佳收件匣傳遞率。

* MTA可大幅提升整體輸送速度，並大幅減少軟退信。
* 它使用最新的MTA技術，為您提供最佳的電子郵件傳送輸送速度。
* 透過即時且自動地調整它收到的意見回饋，它還可以確保使用即時傳遞資料進行更精確且更智慧的電子郵件傳遞。

### 退信資格

的 **同步** 傳送失敗錯誤訊息、MTA會決定退信型別和資格，並將該資訊傳回至Campaign。

MTA會符合SMTP退信的資格，並以對應至Campaign退信原因和資格的退信代碼形式，將該資格傳送回Campaign。

>[!NOTE]
>
>目前 **非同步** inMail程式會透過 **[!UICONTROL Inbound email]** 規則。

瞭解更多關於傳送失敗的內容，位置在： [本節](delivery-failures.md).


### 特定MX規則

MX規則（郵件交換器）是管理傳送伺服器與接收伺服器之間通訊的規則。

MTA有自己的MX規則，可讓它根據您過去的電子郵件信譽，以及您傳送電子郵件之網域所提供的即時回饋，而依網域來自訂您的輸送量。

### DKIM簽署

Domain Keys Identified Mail (DKIM)是一種用於偵測偽造的寄件者地址（通常稱為欺騙）的驗證方法。

在Adobe Campaign中，DKIM電子郵件驗證簽署是由MTA執行。

進一步瞭解DKIM，請參閱 [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## 電子郵件回饋服務 {#email-feedback-service}

使用電子郵件回饋服務(EFS)功能，可準確報告每個電子郵件的狀態，因為回饋會直接從MTA擷取。

開始傳送後， **[!UICONTROL Success]** 訊息成功從Campaign轉送至MTA時的百分比。

傳遞記錄顯示 **[!UICONTROL Taken into account by the service provider]** 每個目標地址的狀態。

當訊息實際傳送到目標設定檔時，一旦從MTA即時回報此資訊，傳送記錄會顯示 **[!UICONTROL Sent]** 成功接收訊息的每個位址的狀態。 此 **[!UICONTROL Success]** 百分比會隨著每次成功傳遞而增加。

當從MTA回報硬退信時，其記錄狀態會從 **[!UICONTROL Taken into account by the service provider]** 至 **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

當從MTA回報軟退信訊息時，其記錄狀態維持不變(**[!UICONTROL Taken into account by the service provider]**)：僅限 [錯誤原因](delivery-failures.md#delivery-failure-reasons) 已更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. 此 **[!UICONTROL Success]** 百分比保持不變。 然後會在整個傳遞期間重試軟退信訊息 [有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}：

* 如果在有效期結束前重試成功，則訊息狀態會變更為 **[!UICONTROL Sent]** 和 **[!UICONTROL Success]** 百分比會隨之增加。

* 否則，狀態將變更為 **[!UICONTROL Failed]**. 此 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不變。

>[!NOTE]
>
>如需硬跳出和軟跳出的詳細資訊，請參閱 [本節](delivery-failures.md#delivery-failure-reasons).
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱 [本節](delivery-failures.md#retries).

下表顯示如何使用EFS功能在傳送程式的每個步驟更新KPI和傳送記錄檔狀態。

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至MTA | **[!UICONTROL Success]** 百分比未顯示（從0%開始） | 服務提供者已將其列入考量 |
| 系統會從MTA回報硬跳出訊息 | 無變更 **[!UICONTROL Success]** 百分比 | 失敗 |
| 系統會從MTA回報軟退信訊息 | 無變更 **[!UICONTROL Success]** 百分比 | 服務提供者已將其列入考量 |
| 軟退信重試成功 | **[!UICONTROL Success]** 百分比會隨之增加 | 已傳送 |
| 軟退信重試失敗 | 無變更 **[!UICONTROL Success]** 百分比 | 失敗 |
