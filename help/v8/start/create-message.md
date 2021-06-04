---
product: Adobe Campaign
title: 開始使用訊息
description: 開始使用訊息
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 9ecd0af7a6e8e173a89106c84a78de8b2311fef7
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 71%

---

# 開始使用訊息{#gs-ac-audiences}

透過Adobe Campaign，您可以傳送跨通道行銷活動，包括電子郵件、簡訊、推播通知和直接郵件，並使用各種專用報表來評估其成效。 這些訊息是透過傳遞進行設計和傳送，而且可針對每位收件者進行個人化。

核心功能包括目標定位、定義和個人化訊息、通訊執行及相關的營運報告。 主要功能存取點是傳送助理。 此存取點可導向 Adobe Campaign 涵括的多種功能。

了解在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=zh-Hant)中建立傳送的關鍵步驟。

Adobe Campaign v8 提供下列傳送頻道：

* **電子郵件頻道**：電子郵件傳遞功能可讓您傳送個人化電子郵件給目標群體。在[本頁](../send/email.md)中了解更多。

* **直接郵件頻道**：直接郵件傳遞可讓您產生擷取檔案，其中包含目標群體的資料。在[本頁](../send/direct-mail.md)中了解更多

* **行動裝置頻道**：行動裝置頻道上的傳遞可讓您傳送個人化 SMS 給目標群體。在[本頁](../send/sms.md)中了解更多

* **行動應用程式頻道**：行動應用程式傳送可讓您傳送通知至 iOS 和 Android 系統。在[本頁](../send/push.md)中了解更多

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 選擇如何傳送訊息

當您的訊息建立完成且其內容經過設計和測試後，您就可以選擇要如何傳送。 Campaign 提供一組功能，可以：

* 手動傳送訊息至主要目標

   ![](assets/send-email.png)

   [!DNL :arrow_upper_right:] [了解如何傳送訊息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=zh-Hant)
* 傳送與[行銷活動](campaigns.md)相關聯的訊息

   ![](assets/deliveries-in-a-campaign.png)

   [!DNL :arrow_upper_right:] [了解如何在行銷活動內容中傳送訊息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=zh-Hant)。
* 透過[workflow](../config/workflows.md)傳送訊息

   ![](assets/send-in-a-wf.png)

   [!DNL :arrow_upper_right:] [了解如何自動傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=zh-Hant)
* [從事](../send/transactional.md) 件觸發訊息
   [!DNL :arrow_upper_right:] [使用案例：了解如何傳送包含附件的交易式電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=zh-Hant)
* 排程訊息

   ![](assets/schedule-send.png)

   [!DNL :arrow_upper_right:] [使用案例：了解如何排程和傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=zh-Hant)


## 新增個人化

Adobe Campaign 傳送的資訊可以透過多種方式實現個人化。

您可以：

* 插入動態個人化欄位。

   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7檔案中 [使用個人化欄位](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=zh-Hant)
* 插入預定義的個人化區塊。

   [!DNL :arrow_upper_right:] 了解什麼是個人化區塊，以及如何在 [Campaign Classicv7檔案中使用](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=zh-Hant)
* 建立條件式內容。

   [!DNL :arrow_upper_right:] 了解如何在 [Campaign Classicv7檔案中插入條件式內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=zh-Hant)

## 傳送異動訊息

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

[!DNL :bulb:] 在[本節](../dev/architecture.md#transac-msg-archi)中進一步瞭解異動訊息功能

[!DNL :bulb:][ 本頁](../send/transactional.md)中詳細說明了設定和傳送異動訊息的步驟

[!DNL :arrow_upper_right:] 在Campaign Classicv7檔案中，透過端對端使用案例 [探索此功能](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=zh-Hant#transactional-messaging)

## 傳送和追蹤記錄

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 您可以在傳送傳遞後進行監視，並瞭解傳送失敗和隔離的管理方式。

[!DNL :arrow_upper_right:] [在本小節中了解如何監視您的傳送](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hant#sending-messages)


**相關主題**

[!DNL :arrow_upper_right:]  [傳遞最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=zh-Hant)

[!DNL :arrow_upper_right:]  [測試並傳送電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [傳送校樣](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant)
