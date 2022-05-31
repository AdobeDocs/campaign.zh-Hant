---
title: 發送和接收電子郵件
description: 瞭解與Adobe Campaign發送電子郵件的範圍和特點
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 1%

---


# 發送和接收電子郵件

配置並準備發送交貨後，請確保已運行交貨分析。

![](../assets/do-not-localize/book.png) [瞭解有關Campaign Classicv7文檔的更多資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery){target=&quot;_blank&quot;

完成後，確認發送以啟動消息的發送。

您也可以：

* 使用 [推遲交付選擇](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;,
* 發送到多個批中 [多波](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}。

從 **交貨** 頁籤，可通過此交貨的詳細資訊或交貨清單訪問。

## 監視電子郵件

發送後，在「傳遞控制板」中檢查您的傳遞狀態，並訪問傳遞日誌和報告以確認郵件已正確發送。

![](../assets/do-not-localize/book.png) [瞭解有關Campaign Classicv7文檔的更多資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target=&quot;_blank&quot;


## 市場活動MTA {#mta}

市場活動v8郵件傳輸代理(MTA)提供了同類最佳的發送基礎架構，可實現最佳的傳送能力、信譽、吞吐量、報告、反彈處理、IP升級和連接設定管理。

它適用於所有Campaign v8客戶，可保證可擴充性、高交付吞吐量，並幫助更快地發送更多電子郵件。 這是通過新的自適應傳遞技術實現的，這種技術基於來自網際網路服務提供商的反饋即時地改變電子郵件發送設定。

### 好處

Adobe Campaign使用郵件傳輸代理(MTA)，該代理運行SparkPost的商業電子郵件MTA，該MTA名為 **動量**。

Momentum代表了創新的高效能MTA技術，其中包括更智慧的彈跳處理和自動化的可傳送性優化功能，幫助發送者實現和保持最佳收件箱傳送率。

* MTA允許整體吞吐速度的大幅提高和軟邊界的顯著減少。
* 它使用最新的MTA技術為您提供最佳的電子郵件傳輸速度。
* 通過立即自動適應它收到的反饋，它還確保了通過即時傳遞資料提供更準確和智慧的電子郵件。

### 彈跳資格

對於 **同步** 傳遞失敗錯誤消息，MTA確定退貨類型和資格，並將該資訊發回市場活動。

MTA確認SMTP退貨資格，並以彈出代碼的形式將該資格發回市場活動，該代碼映射到市場活動退貨原因和資格。

>[!NOTE]
>
>當前 **非同步** 通過inMail流程對回報進行限定 **[!UICONTROL Inbound email]** 規則。 有關此內容的詳細資訊，請參閱 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}。 <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

瞭解有關交付失敗的詳細資訊 [此部分](delivery-failures.md)。


### 特定MX規則

MX規則（郵件eXchanger）是管理發送伺服器與接收伺服器之間通信的規則。

MTA有其自己的MX規則，它可以根據您的歷史電子郵件信譽以及您發送電子郵件的域的即時反饋，按域定制您的吞吐量。

### DKIM簽名

域密鑰標識郵件(DKIM)是一種用於檢測偽造的發件人地址（通常稱為欺騙）的身份驗證方法。

在Adobe Campaign,DKIM電子郵件驗證簽名由MTA執行。

瞭解有關DKIM的詳細資訊 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}。

## 電子郵件回饋服務 {#email-feedback-service}

利用電子郵件反饋服務(EFS)功能，可以準確報告每封電子郵件的狀態，因為反饋會直接從MTA捕獲。

一旦開始交貨， **[!UICONTROL Success]** 成功將消息從市場活動中繼到MTA時的百分比。

交貨日誌顯示 **[!UICONTROL Taken into account by the service provider]** 每個目標地址的狀態。

當消息實際被傳送到目標配置檔案，並且一旦從MTA即時報告此資訊，傳遞日誌將顯示 **[!UICONTROL Sent]** 成功接收消息的每個地址的狀態。 的 **[!UICONTROL Success]** 每次成功交付時，百分比都相應增加。

當硬跳消息從MTA返回報告時，其日誌狀態將從 **[!UICONTROL Taken into account by the service provider]** 至 **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。

從MTA返回軟跳跳消息時，其日誌狀態保持不變(**[!UICONTROL Taken into account by the service provider]**):只有 [錯誤原因](delivery-failures.md#delivery-failure-reasons) 已更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。 的 **[!UICONTROL Success]** 百分比保持不變。 然後在整個傳送過程中重試軟彈跳消息 [有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;:

* 如果在有效期結束前重試成功，則消息狀態將更改為 **[!UICONTROL Sent]** 和 **[!UICONTROL Success]** 百分比相應增加。

* 否則，狀態將更改為 **[!UICONTROL Failed]**。 的 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不變。

>[!NOTE]
>
>有關硬邊界和軟邊界的詳細資訊，請參閱 [此部分](delivery-failures.md#delivery-failure-reasons)。
>
>有關傳遞臨時失敗後重試的更多資訊，請參見 [此部分](delivery-failures.md#retries)。

下表顯示了如何在使用EFS功能發送流程的每個步驟更新KPI和發送日誌狀態。

| 發送過程中的步驟 | KPI摘要 | 正在發送日誌狀態 |
|--- |--- |--- |
| 已成功將消息從市場活動中轉到MTA | **[!UICONTROL Success]** 百分比未顯示（以0%開始） | 服務提供商考慮的因素 |
| 從MTA返回硬跳消息 | 未更改 **[!UICONTROL Success]** 百分比 | 已失敗 |
| 從MTA返回軟跳跳消息 | 未更改 **[!UICONTROL Success]** 百分比 | 服務提供商考慮的因素 |
| 軟彈跳消息重試成功 | **[!UICONTROL Success]** 百分比相應增加 | 已傳送 |
| 軟跳轉消息重試失敗 | 未更改 **[!UICONTROL Success]** 百分比 | 已失敗 |
