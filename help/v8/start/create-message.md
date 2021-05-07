---
solution: Campaign
product: Adobe Campaign
title: 開始使用訊息
description: 開始使用訊息
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 221adcce8951a3884b83d5e5e2de1a73fbe96050
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# 開始使用messages{#gs-ac-audiences}

透過Adobe Campaign，您可以傳送跨通道宣傳，包括電子郵件、簡訊、LINE訊息、推播通知和直效郵件，並使用各種專屬報告來評估宣傳的成效。 這些訊息是透過傳送進行設計和傳送，而且可針對每位收件者個人化。

核心功能包括定位、定義和個人化訊息、通訊執行及相關的營運報告。 主要功能接入點是交付助理。 此接入點可提供Adobe Campaign涵蓋的多種功能。

瞭解在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)中建立傳送的關鍵步驟。

Adobe Campaignv8提供下列傳送管道：

* **電子郵件通道**:電子郵件傳送功能可讓您傳送個人化電子郵件給目標人群。進一步瞭解[本頁](../send/email.md)。

* **直接郵件渠道**:直接郵件傳送可讓您產生擷取檔案，其中包含目標人口的資料。進一步瞭解[本頁](../send/direct-mail.md)

* **行動頻道**:行動頻道上的傳送可讓您傳送個人化SMS給目標群體。進一步瞭解[本頁](../send/sms.md)

* **行動應用程式頻道**:行動應用程式傳送可讓您傳送通知至iOS和Android系統。進一步瞭解[本頁](../send/push.md)
* **線路頻道**:LINE傳送功能可讓您在LINE上傳送訊息，此即時訊息應用程式適用於所有智慧型手機。進一步瞭解[本頁](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/line-channel.html)

## 選擇如何傳送訊息

一旦您的訊息建立完成，並且其內容經過設計和測試後，您就可以選擇要如何傳送。 促銷活動提供一組功能，可：

* 手動傳送訊息至主要目標
:arrow_upper_right:[瞭解如何傳送訊息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* 傳送與[行銷促銷活動](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)相關的訊息
:arrow_upper_right:[瞭解如何在促銷活動中傳送訊息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html)。
* 透過[workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)傳送訊息
:arrow_upper_right:[瞭解如何自動傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [觸發](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 事件的訊息：arrow_upper_right: [使用案例：瞭解如何傳送含附件的交易式電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 排程您的訊息
:arrow_upper_right:[使用案例：瞭解如何排程及傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## 新增個人化

Adobe Campaign傳遞的資訊可以通過多種方式實現個性化。

您可以：

* 插入動態的個人化欄位。:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)中使用個人化欄位
* 插入預先定義的個人化區塊。
:arrow_upper_right:瞭解什麼是個人化區塊，以及如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)中使用它
* 建立有條件的內容。:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)中插入條件式內容

## 傳送交易訊息

交易式訊息（訊息中心）是專為管理觸發訊息而設計的促銷活動模組。

：球：在[本節](../dev/architecture.md#transac-msg-archi)中進一步瞭解事務性消息功能

：球：[本頁](../send/transactional.md)中詳細說明了配置和發送事務性消息的步驟

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)的端到端使用案例中探索此功能

## 傳送和追蹤記錄檔

在傳送交貨後監控交貨是確保行銷宣傳有效率並與客戶溝通的關鍵步驟。 您可以在傳送傳送後進行監控，並瞭解傳送失敗和隔離的管理方式。

:arrow_upper_right:[瞭解如何在本節中監控您的交貨](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**相關主題**

:arrow_upper_right: [傳遞最佳實踐](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right: [測試並傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right: [傳送校樣](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
