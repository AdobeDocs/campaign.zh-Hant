---
title: 傳送及監視您的電子郵件
description: 瞭解使用Adobe Campaign傳送電子郵件的範圍和特性
feature: Email
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: c7f139dd7f139ba421eb034f4d8911671b3b3332
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 2%

---


# 傳送及監視您的電子郵件  {#send-and-monitor-emails}

當傳送已設定好並準備好傳送時，請確定您已執行傳送分析。 [了解更多](delivery-analysis.md)

完成後，確認傳送以啟動訊息傳送。

從&#x200B;**傳遞**&#x200B;索引標籤追蹤傳遞的執行，可透過此傳遞的詳細資訊或傳遞清單存取。

## 監視您的電子郵件 {#email-monitoring}

傳送後，請在&#x200B;**傳遞控制面板**&#x200B;中檢查您的傳遞狀態，並存取傳遞記錄與報告，確認訊息已正確傳送。

從傳送控制面板中，您可以檢查已處理的訊息和傳送稽核記錄。 您也可以控制傳送記錄檔中訊息的狀態。

深入瞭解[傳遞狀態](delivery-statuses.md)。

>[!NOTE]
>
>傳遞狀態不會即時顯示。 在本節[中進一步瞭解電子郵件回饋服務](#email-feedback-service)。

## Campaign MTA {#mta}

Campaign v8郵件傳輸代理程式(MTA)提供同級最佳的傳送基礎架構，以實現最佳傳遞能力、信譽、輸送量、報告、跳出處理、IP提升和連線設定管理。

此服務適用於所有Campaign v8客戶，可保證擴充性、高傳遞輸送量，並有助於更快速地傳送更多電子郵件。 這是透過新的適應性傳送技術達成，該技術會根據網際網路服務提供者的意見來即時變更電子郵件傳送設定。

### 好處

Adobe Campaign使用郵件傳輸代理程式(MTA)，執行SparkPost的商業電子郵件MTA，稱為&#x200B;**Momentum**。

Momentum代表創新的高效能MTA技術，包括更聰明的彈回處理以及自動化傳遞能力最佳化功能，可協助寄件者達成並維持最佳收件匣傳遞率。

* MTA可大幅提升整體輸送速度，並大幅減少軟退信。
* 它使用最新的MTA技術，為您提供最佳的電子郵件傳送輸送速度。
* 透過即時且自動地調整它收到的意見回饋，它還可以確保使用即時傳遞資料進行更精確且更智慧的電子郵件傳遞。

### 退信資格

對於&#x200B;**同步**&#x200B;傳遞失敗錯誤訊息，MTA會決定退信型別和資格，並將該資訊傳回至Campaign。

MTA會符合SMTP退信的資格，並以對應至Campaign退信原因和資格的退信代碼形式，將該資格傳送回Campaign。

>[!NOTE]
>
>目前&#x200B;**非同步**&#x200B;退信由inMail處理序透過&#x200B;**[!UICONTROL Inbound email]**&#x200B;規則限定。

在[本節](delivery-failures.md)中進一步瞭解傳遞失敗。


### 特定MX規則

MX規則（郵件交換器）是管理傳送伺服器與接收伺服器之間通訊的規則。

MTA有自己的MX規則，可讓它根據您過去的電子郵件信譽，以及您傳送電子郵件之網域所提供的即時回饋，而依網域來自訂您的輸送量。

### DKIM簽署

Domain Keys Identified Mail (DKIM)是一種驗證方法，用來偵測偽造的寄件者地址（通常稱為欺騙）。

在Adobe Campaign中，DKIM電子郵件驗證簽署是由MTA執行。

在[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=zh-Hant#authentication){target="_blank"}中瞭解更多有關DKIM的資訊。

## 電子郵件回饋服務 {#email-feedback-service}

Campaign電子郵件回饋服務(EFS)會報告透過Adobe Campaign傳送的每個電子郵件傳遞的狀態。

開始傳遞後，當訊息成功從Campaign轉送至MTA時，**[!UICONTROL Success]**&#x200B;百分比沒有變更。 傳遞記錄顯示每個目標地址的&#x200B;**[!UICONTROL Taken into account by the service provider]**&#x200B;狀態。

當訊息實際傳遞至目標設定檔，且從MTA即時回報此資訊後，傳遞記錄會顯示成功收到訊息之每個位址的&#x200B;**[!UICONTROL Sent]**&#x200B;狀態。 每次成功傳遞時，**[!UICONTROL Success]**&#x200B;百分比都會相應增加。

當從MTA回報硬退信時，其記錄狀態會從&#x200B;**[!UICONTROL Taken into account by the service provider]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。

當從MTA回報軟退信訊息時，其記錄狀態維持不變(**[!UICONTROL Taken into account by the service provider]**)：只有[錯誤原因](delivery-failures.md#delivery-failure-reasons)更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。 **[!UICONTROL Success]**&#x200B;百分比保持不變。 然後，會在整個傳遞[有效期間](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/communication-channels){target="_blank"}重試軟退信訊息：

* 如果在有效期間結束前重試成功，則訊息狀態會變更為&#x200B;**[!UICONTROL Sent]**，而&#x200B;**[!UICONTROL Success]**&#x200B;百分比會相應增加。

* 否則，狀態會變更為&#x200B;**[!UICONTROL Failed]**。 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不變。

>[!NOTE]
>
>如需硬退信和軟退信的詳細資訊，請參閱[本節](delivery-failures.md#delivery-failure-reasons)。
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱[本節](delivery-failures.md#retries)。

下表顯示如何在傳送程式的每個步驟更新KPI和傳送記錄檔狀態。

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至MTA | 未顯示&#x200B;**[!UICONTROL Success]**&#x200B;百分比（從0%開始） | 服務提供者已將其列入考量 |
| 系統會從MTA回報硬跳出訊息 | **[!UICONTROL Success]**&#x200B;百分比沒有變更 | 失敗 |
| 系統會從MTA回報軟退信訊息 | **[!UICONTROL Success]**&#x200B;百分比沒有變更 | 服務提供者已將其列入考量 |
| 軟退信重試成功 | **[!UICONTROL Success]**&#x200B;百分比會相應增加 | 已傳送 |
| 軟退信重試失敗 | **[!UICONTROL Success]**&#x200B;百分比沒有變更 | 失敗 |
