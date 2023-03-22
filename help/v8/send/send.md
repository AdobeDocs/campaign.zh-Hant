---
title: 傳送及監控您的電子郵件
description: 了解使用Adobe Campaign傳送電子郵件的範圍和特性
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---


# 傳送及監控您的電子郵件

當已設定傳送並準備好傳送時，請確定您已執行傳送分析。 [了解更多](delivery-analysis.md)

完成後，確認傳送以啟動訊息傳送。

追蹤來自 **傳送** 索引標籤，可透過此傳送的詳細資訊或傳送清單存取。

## 監視您的電子郵件

傳送後，在「傳送控制面板」中檢查您的傳送狀態，並存取傳送記錄檔和報表，以確認訊息已正確傳送。

![](../assets/do-not-localize/book.png) [在 Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## 促銷活動MTA {#mta}

Campaign v8 Mail Transfer Agent(MTA)提供同級最佳的傳送基礎架構，以實現最佳的傳送能力、信譽、吞吐量、報告、退信處理、IP升級和連接設定管理。

它可供所有Campaign v8客戶使用，可保證可擴充性、高傳遞吞吐量，並有助於更快傳送電子郵件。 這是透過新的最適化傳送技術來達成，這些技術會根據來自網際網路服務提供者的意見即時變更電子郵件傳送設定。

### 好處

Adobe Campaign使用郵件傳輸代理(MTA)，該代理會執行SparkPost的商業電子郵件MTA，稱為 **動量**.

Momentum代表創新、高效能的MTA技術，包括更智慧的退信處理和自動化的傳遞能力優化功能，可幫助發件人實現並保持最佳的收件箱傳送率。

* MTA可大幅提升整體吞吐速度，並大幅降低軟跳出。
* 它使用最新的MTA技術，為您提供電子郵件傳送的最佳吞吐量速度。
* 借由即時且自動地適應收到的意見反應，還可確保以即時傳送資料傳送更精確且智慧的電子郵件。

### 退信資格

針對 **同步** 傳送失敗錯誤訊息，MTA會決定退信類型和資格，並將該資訊傳回至Campaign。

MTA會符合SMTP退信的資格，並以對應至促銷活動退信原因和資格的退信代碼形式，將該資格傳回Campaign。

>[!NOTE]
>
>目前 **非同步** 彈回會由inMail程式透過 **[!UICONTROL Inbound email]** 規則。

進一步了解傳遞失敗，位於 [本節](delivery-failures.md).


### 特定MX規則

MX規則(Mail eXchanger)是管理發送伺服器與接收伺服器之間通信的規則。

MTA有其專屬的MX規則，可讓MX根據您過去的電子郵件信譽，以及您傳送電子郵件之網域所提供的即時意見，依網域自訂您的輸送量。

### DKIM簽名

域密鑰標識郵件(DKIM)是一種用於檢測偽造的發件人地址的身份驗證方法（通常稱為欺騙）。

在Adobe Campaign中，DKIM電子郵件驗證簽署是由MTA執行。

進一步了解 [Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## 電子郵件回饋服務 {#email-feedback-service}

利用電子郵件反饋服務(EFS)功能，可以準確報告每封電子郵件的狀態，因為反饋是直接從MTA中捕獲的。

傳送開始後， **[!UICONTROL Success]** 成功從促銷活動中繼至MTA時的百分比。

傳送記錄會顯示 **[!UICONTROL Taken into account by the service provider]** 每個目標地址的狀態。

當訊息實際傳送至目標設定檔，且從MTA即時回報此資訊後，傳送記錄會顯示 **[!UICONTROL Sent]** 成功接收消息的每個地址的狀態。 此 **[!UICONTROL Success]** 每次成功傳送時，百分比會隨之增加。

從MTA回報硬彈回訊息時，其記錄狀態會從 **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

從MTA回報軟跳出訊息時，其記錄狀態維持不變(**[!UICONTROL Taken into account by the service provider]**):只有 [錯誤原因](delivery-failures.md#delivery-failure-reasons) 已更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. 此 **[!UICONTROL Success]** 百分比保持不變。 然後在傳送期間重試軟反彈消息 [有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* 如果在有效期結束前重試成功，則訊息狀態會變更為 **[!UICONTROL Sent]** 和 **[!UICONTROL Success]** 百分比隨之增加。

* 否則，狀態會變更為 **[!UICONTROL Failed]**. 此 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不變。

>[!NOTE]
>
>如需硬跳出和軟跳出的詳細資訊，請參閱 [本節](delivery-failures.md#delivery-failure-reasons).
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱 [本節](delivery-failures.md#retries).

下表顯示了KPI和發送日誌狀態在EFS功能的發送過程的每個步驟中如何更新。

| 傳送程式的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從促銷活動中繼至MTA | **[!UICONTROL Success]** 百分比未顯示（從0%開始） | 服務提供者已將其列入考量 |
| 從MTA回報硬彈回的訊息 | 中無變更 **[!UICONTROL Success]** 百分比 | 失敗 |
| 從MTA回報軟彈跳訊息 | 中無變更 **[!UICONTROL Success]** 百分比 | 服務提供者已將其列入考量 |
| 軟跳出消息重試成功 | **[!UICONTROL Success]** 百分比相應增加 | 已傳送 |
| 軟跳出訊息重試失敗 | 中無變更 **[!UICONTROL Success]** 百分比 | 失敗 |
