---
title: 關於增強型MTA在Adobe Campaign
description: 瞭解與Adobe Campaign增強型MTA發送電子郵件的範圍和特點
feature: Email
role: Data Engineer
level: Beginner
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 4%

---

# 關於增強的MTA {#sending-with-enhanced-mta}

的 **Adobe Campaign增強MTA** （郵件傳輸代理）提供了升級的發送基礎結構，可實現最佳的傳輸能力、信譽、吞吐量、報告、跳轉處理、IP升級和連接設定管理。

它為所有Campaign v8客戶實施，以提高可擴充性、提高交付吞吐量並幫助更快地發送更多電子郵件。 這是通過新的自適應傳遞技術實現的，這種技術基於來自網際網路服務提供商的反饋即時地改變電子郵件發送設定。

## 使用和優勢

**什麼是增強的MTA?**

Adobe Campaign使用郵件傳輸代理(MTA)，該代理運行SparkPost的商業電子郵件MTA，該MTA名為 **動量**。

Momentum代表了創新的高效能MTA技術，其中包括更智慧的彈跳處理和自動化的可傳送性優化功能，幫助發送者實現和保持最佳收件箱傳送率。

**有什麼好處？**

* 增強的MTA使總吞吐速度大幅提高，軟邊界顯著減少。
* 它使用最新的MTA技術為您提供最佳的電子郵件傳輸速度。
* 通過立即自動適應它收到的反饋，它還確保了通過即時傳遞資料提供更準確和智慧的電子郵件。

## 增強的MTA特異性 {#enhanced-mta-impacts}

### 彈跳資格

對於 **同步** 傳遞失敗錯誤消息，增強型MTA確定退貨類型和資格，並將該資訊發回市場活動。

「增強的MTA」確認了SMTP退貨資格，並將該資格以彈出代碼的形式發回市場活動，該代碼映射到市場活動退貨原因和資格。

>[!NOTE]
>
>當前 **非同步** Enhanced MTA不限定Bounce，而是通過inMail流程 **[!UICONTROL Inbound email]** 規則。 有關此內容的詳細資訊，請參閱 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}。 <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

瞭解有關交付失敗的詳細資訊 [此部分](delivery-failures.md)。

### 有效期

僅當設定為時，增強型MTA才會使用「市場活動交付」中的有效期設定 **3.5天或以下**。 如果在「市場活動」中定義的值超過3.5天，則不會將其考慮在內。

例如，如果有效期在市場活動中設定為預設值5天，則軟跳轉消息將進入增強MTA重試隊列，並從消息到達增強MTA後重試最多3.5天。 在這種情況下，將不使用「市場活動」中設定的值。

當訊息在 Enhanced MTA 佇列中停留 3.5 天且無法傳送時，訊息會逾時，其狀態會從傳送記錄檔中的 **[!UICONTROL Sent]** 更新為 **[!UICONTROL Failed]**。

有關有效期的詳細資訊，請參閱 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}。

### 重試次數

軟反彈重試次數和它們之間的時間長度由增強MTA根據郵件電子郵件域返回的反彈響應的類型和嚴重性確定。

>[!NOTE]
>
>市場活動不使用傳遞屬性中的重試設定。

在中重試時瞭解更多資訊 [此部分](delivery-failures.md#retries)。

### 特定MX規則

MX規則（郵件eXchanger）是管理發送伺服器與接收伺服器之間通信的規則。

增強型MTA有其自己的MX規則，它可根據您的歷史電子郵件信譽以及您發送電子郵件的域的即時反饋，按域定制吞吐量。

### DKIM簽名

域密鑰標識郵件(DKIM)是一種用於檢測偽造的發件人地址（通常稱為欺騙）的身份驗證方法。

在Adobe Campaign,DKIM電子郵件身份驗證簽名由增強MTA執行。

瞭解有關DKIM的詳細資訊 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}。

## 電子郵件回饋服務 {#email-feedback-service}

借助電子郵件反饋服務(EFS)功能，可以準確報告每封電子郵件的狀態，因為反饋會直接從增強的MTA（郵件傳輸代理）中捕獲。

一旦開始交貨， **[!UICONTROL Success]** 成功將消息從「市場活動」中繼到「增強的MTA」時的百分比。

交貨日誌顯示 **[!UICONTROL Taken into account by the service provider]** 每個目標地址的狀態。

當郵件實際被傳送到目標配置檔案，並且一旦從增強型MTA即時報告此資訊，傳遞日誌將顯示 **[!UICONTROL Sent]** 成功接收消息的每個地址的狀態。 的 **[!UICONTROL Success]** 每次成功交付時，百分比都相應增加。

當硬跳消息從增強MTA返回報告時，其日誌狀態將從 **[!UICONTROL Taken into account by the service provider]** 至 **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。

從增強MTA返回軟跳跳消息時，其日誌狀態保持不變(**[!UICONTROL Taken into account by the service provider]**):只有 [錯誤原因](delivery-failures.md#delivery-failure-reasons) 已更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。 的 **[!UICONTROL Success]** 百分比保持不變。 然後在整個傳送過程中重試軟彈跳消息 [有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;:

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
| 已成功將消息從市場活動中轉到增強的MTA | **[!UICONTROL Success]** 百分比未顯示（以0%開始） | 服務提供商考慮的因素 |
| 從增強的MTA返回硬跳消息 | 未更改 **[!UICONTROL Success]** 百分比 | 已失敗 |
| 從增強的MTA返回軟彈跳消息 | 未更改 **[!UICONTROL Success]** 百分比 | 服務提供商考慮的因素 |
| 軟彈跳消息重試成功 | **[!UICONTROL Success]** 百分比相應增加 | 已傳送 |
| 軟跳轉消息重試失敗 | 未更改 **[!UICONTROL Success]** 百分比 | 已失敗 |

