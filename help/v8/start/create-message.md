---
title: 開始使用訊息
description: 開始使用訊息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '415'
ht-degree: 100%

---

# 開始使用訊息{#gs-ac-audiences}

透過 Adobe Campaign，您可以傳送跨頻道行銷活動，包括電子郵件、簡訊、LINE 訊息、推播通知和直接郵件，並使用各種專屬報告來評估行銷成效。 這些訊息是透過傳遞進行設計和傳送，而且可針對每位收件者進行個人化。

核心功能包括目標定位、定義和個人化訊息、通訊執行及相關的營運報告。 主要功能存取點是傳送助理。 此存取點可導向 Adobe Campaign 涵括的多種功能。

Adobe Campaign v8 提供下列傳遞管道：

* **電子郵件頻道**：電子郵件傳遞功能可讓您傳送個人化電子郵件給目標群體。在[本頁](../send/email.md)中了解更多。

* **直接郵件頻道**：直接郵件傳遞可讓您產生擷取檔案，其中包含目標群體的資料。在[本頁](../send/direct-mail.md)中了解更多

* **行動裝置頻道**：行動裝置頻道上的傳遞可讓您傳送個人化簡訊給目標群體。在[本頁](../send/sms.md)中了解更多

* **行動應用程式頻道**：行動應用程式傳送可讓您傳送通知至 iOS 和 Android 系統。在[本頁](../send/push.md)中了解更多

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 選擇如何傳送訊息{#gs-send-msg}

當您的訊息建立完成且其內容經過設計和測試後，您就可以選擇要如何傳送。 Campaign 提供一組功能，可以：

* 手動傳送訊息至主要目標

  ![](assets/send-email.png)

  了解如何在[本節](../send/send.md)傳送訊息

* 傳送與[行銷活動](campaigns.md)相關的訊息

  ![](assets/deliveries-in-a-campaign.png)

  在[本章節](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hant){target="_blank"}瞭解如何在行銷活動內容之中傳送訊息。

* 透過[工作流程](../config/workflows.md)傳送訊息

  ![](assets/send-in-a-wf.png)

  在[此頁面](../../automation/workflow/delivery.md)瞭解如何自動傳遞電子郵件

* 從事件[觸發訊息](../send/transactional.md) 

* 排程您的訊息

  ![](assets/schedule-send.png)

[使用案例：瞭解如何排程並傳送生日電子郵件](../../automation/workflow/send-a-birthday-email.md)


## 新增個人化{#personalization}

Adobe Campaign 傳送的資訊可以透過多種方式實現個人化。[進一步瞭解個人化功能](../send/personalize.md)

您可以：

* 插入動態的個人化欄位。[了解更多](../send/personalization-fields.md)
* 插入預先定義的個人化區塊。[了解更多](../send/personalization-blocks.md)
* 建立有條件的內容。[了解更多](../send/conditions.md)

## 傳送異動訊息{#gs-transac-messages}

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

在[本節](../architecture/architecture.md#transac-msg-archi)進一步瞭解異動訊息功能

[本頁面](../send/transactional.md)詳細說明了設定及傳送異動訊息的步驟


## 傳送和追蹤記錄{#gs-tracking-logs}

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 您可以在傳送傳遞後進行監視，並瞭解傳送失敗和隔離的管理方式。

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}瞭解如何監視傳遞

