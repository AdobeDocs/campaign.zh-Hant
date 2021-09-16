---
title: 開始使用訊息
description: 開始使用訊息
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 100%

---

# 開始使用訊息{#gs-ac-audiences}

透過 Adobe Campaign，您可以傳送跨頻道行銷活動，包括電子郵件、SMS、LINE 訊息、推播通知和直接郵件，並使用各種專屬報告來評估行銷成效。 這些訊息是透過傳遞進行設計和傳送，而且可針對每位收件者進行個人化。

核心功能包括目標定位、定義和個人化訊息、通訊執行及相關的營運報告。 主要功能存取點是傳送助理。 此存取點可導向 Adobe Campaign 涵括的多種功能。

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=zh-Hant)中瞭解建立傳送的關鍵步驟。

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

    ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何傳送訊息

* 傳送與[行銷活動](campaigns.md)相關的訊息

   ![](assets/deliveries-in-a-campaign.png)

    ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何在行銷活動內容中傳送訊息

* 透過[工作流程](../config/workflows.md)傳送訊息

   ![](assets/send-in-a-wf.png)

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何自動傳遞電子郵件

* 由事件[觸發訊息](../send/transactional.md)
↗️ [使用案例：瞭解如何傳送含附件的異動電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=zh-Hant){target=&quot;_blank&quot;}

* 排程您的訊息

   ![](assets/schedule-send.png)

   ↗️ [使用案例：瞭解如何排程並傳送生日電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=zh-Hant){target=&quot;_blank&quot;}


## 新增個人化

Adobe Campaign 傳送的資訊可以透過多種方式實現個人化。

您可以：

* 插入動態個人化欄位。
↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何使用個人化欄位
* 插入預定義的個人化區塊。
↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解什麼是個人化區塊，以及如何使用
* 建立條件式內容。
↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解如何插入條件式內容

## 傳送異動訊息

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

?? 在[本章節](../dev/architecture.md#transac-msg-archi)進一步瞭解異動訊息功能

?? [本頁面](../send/transactional.md)詳細說明了設定及傳送異動訊息的步驟

↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=zh-Hant){target=&quot;_blank&quot;} 中瞭解此功能在端對端使用案例中的作用

## 傳送和追蹤記錄

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 您可以在傳送傳遞後進行監視，並瞭解傳送失敗和隔離的管理方式。

 ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target=&quot;_blank&quot;} 中瞭解如何監視傳遞


Campaign Classic v7 文件中的&#x200B;**相關主題**：

↗️  [傳遞最佳實務 ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=zh-Hant){target=&quot;_blank&quot;}

↗️  [測試並傳送電子郵件 ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;}

↗️  [傳送校樣](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target=&quot;_blank&quot;}
