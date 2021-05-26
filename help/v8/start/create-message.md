---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用訊息
description: 開始使用訊息
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 3%

---

# 開始使用messages{#gs-ac-audiences}

透過Adobe Campaign，您可以傳送跨通道行銷活動，包括電子郵件、簡訊、推播通知和直接郵件，並使用各種專用報表來評估其成效。 這些訊息會經由傳送而設計和傳送，且可針對每個收件者進行個人化。

核心功能包括定位、定義及個人化訊息、執行通訊及相關營運報告。 主要功能存取點是傳遞助理。 此存取點可提供Adobe Campaign涵蓋的多項功能。

了解在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)中建立傳送的關鍵步驟。

Adobe Campaign v8隨附下列傳送管道：

* **電子郵件通道**:電子郵件傳送可讓您傳送個人化電子郵件給目標人口。深入了解[本頁面](../send/email.md)。

* **直接郵件通道**:直接郵件傳送可讓您產生包含目標母體資料的擷取檔案。進一步了解[此頁面](../send/direct-mail.md)

* **行動裝置頻道**:行動通道上的傳送可讓您將個人化簡訊傳送至目標人口。進一步了解[此頁面](../send/sms.md)

* **行動應用程式通道**:行動應用程式傳送可讓您傳送通知至iOS和Android系統。進一步了解[此頁面](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 選擇如何傳送訊息

建立訊息並設計及測試其內容後，您就可以選擇要如何傳送訊息。 Campaign提供一組功能，可：

* 手動傳送訊息至主要目標
:[!DNL :arrow_upper_right:]:[了解如何傳送訊息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* 傳送與[行銷活動](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)相關聯的訊息
:[!DNL :arrow_upper_right:]:[了解如何在行銷活動](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html)的內容中傳送訊息。
* 透過[workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)傳送訊息
:[!DNL :arrow_upper_right:]:[了解如何自動傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [從事](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 件觸發訊息：[!DNL :arrow_upper_right:]: [使用案例：了解如何傳送包含附件的交易式電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 排程訊息
:[!DNL :arrow_upper_right:]:[使用案例：了解如何排程並傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## 新增個人化

Adobe Campaign傳送的訊息可透過多種方式個人化。

您可以：

* 插入動態的個人化欄位。:[!DNL :arrow_upper_right:]:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)中使用個人化欄位
* 插入預先定義的個人化區塊。
:[!DNL :arrow_upper_right:]:了解什麼是個人化區塊，以及如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)中使用
* 建立有條件的內容。:[!DNL :arrow_upper_right:]:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)中插入條件式內容

## 傳送交易式訊息

交易式訊息（訊息中心）是專為管理觸發訊息而設計的Campaign模組。

[!DNL :bulb:] 在本節中進一步了解交易式訊息 [功能](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] 本頁詳細說明設定及傳送交易式訊息 [的步驟](../send/transactional.md)

:[!DNL :arrow_upper_right:]:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)中，以端對端使用案例探索此功能

## 傳送和追蹤記錄檔

在傳送後監控傳送是確保行銷活動有效率並與客戶聯絡的關鍵步驟。 您可以在傳送傳送後進行監控，並了解如何管理傳送失敗和隔離。

:[!DNL :arrow_upper_right:]:[在本小節中了解如何監控您的傳送](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**相關主題**

:[!DNL :arrow_upper_right:]:  [關於傳遞的最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:[!DNL :arrow_upper_right:]: [測試並傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:[!DNL :arrow_upper_right:]: [傳送校樣](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
