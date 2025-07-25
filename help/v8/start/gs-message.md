---
title: 開始使用訊息
description: 開始使用訊息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 73%

---

# 開始使用訊息 {#gs-ac-msg}

透過 Adobe Campaign，您可以傳送跨頻道行銷活動，包括電子郵件、簡訊、LINE 訊息、推播通知和直接郵件，並使用各種專屬報告來評估行銷成效。 這些訊息是透過傳遞進行設計和傳送，而且可針對每位收件者進行個人化。

核心功能包括目標定位、定義及個人化訊息、通訊執行及相關的營運報告。

## 使用案例 {#gs-ac-delivery}

若要傳送訊息，您必須建立傳遞。 傳遞建立模式取決於您的使用案例。

>[!NOTE]
>
>建立傳遞時，您必須選取範本。 每個管道都可使用預設範本。 在[此頁面](../send/create-templates.md)中進一步瞭解傳遞範本。

1. **一次性訊息** — 您可以傳送一次性訊息給對象。 在[本節](create-message.md)中瞭解如何傳送您的第一封郵件。

   ![](assets/send-email.png)

1. **行銷活動中的訊息** — 您可以在[行銷活動的內容中傳送訊息](campaigns.md)、定義核准程式、在合併的控制面板中傳送及追蹤訊息。 在[本節](../../automation/campaigns/marketing-campaign-deliveries.md)中瞭解如何操作。

   ![](assets/deliveries-in-a-campaign.png)

1. **工作流程中的訊息** — 您可以透過[工作流程](../config/workflows.md)傳送訊息，並自動化您的傳遞。 在[此頁面](../../automation/workflow/delivery.md)中瞭解如何操作。

   ![](assets/send-in-a-wf.png)

1. **觸發訊息** — 您可從事件[觸發訊息](../send/transactional.md)。 異動訊息（訊息中心）是專為管理觸發訊息而設計的Campaign模組。 [本頁面](../send/transactional.md)詳細說明了設定及傳送異動訊息的步驟

## 通訊管道 {#gs-channel}

Adobe Campaign v8隨附下列傳送管道。 您環境中可用的管道取決於您的合約。 請檢查您的授權合約。

* **電子郵件管道**：電子郵件傳遞功能可讓您傳送個人化電子郵件給目標群體。[了解更多](../send/email.md)

* **行動裝置管道**：行動裝置管道的傳遞可讓您傳送個人化訊息給目標群體。您可以在行動裝置上傳送[簡訊](../send/sms/sms.md)和[LINE](../send/line.md)訊息。

* **行動應用程式頻道**：您可以使用Adobe Campaign，透過專用應用程式在iOS和Android行動裝置上傳送個人化和分段的[推播通知](../send/push.md)。 執行設定和整合步驟後，即可透過 Adobe Campaign 建立並傳送 iOS 和 Android 傳遞。 您也可以設計包含影像或影片的豐富通知，並傳送至 Android 裝置。

* **直接郵件頻道**： [直接郵件](../send/direct-mail.md)是離線頻道，可讓您建立、個人化並產生外部檔案，以與直接郵件提供者共用。 使用此管道在您的客戶歷程中協調線上和離線管道。

  當您準備直接郵件傳遞時，Adobe Campaign 會產生一個檔案，其中包含所有目標輪廓和選取的聯絡資訊 (例如，郵遞區號)。然後，您就可以將此檔案傳送給您的直接郵件提供者，由他們負責實際傳送。


* **其他管道**： Adobe Campaign也隨附電話傳遞範本，此範本可用來建立外部傳遞。 使用此管道表示您實施專用方法來處理輸出檔案。 設定步驟與[直接郵件管道](../send/direct-mail.md)相同。

  >[!NOTE]
  >
  >電話管道不是內建管道。實施需要 Adobe Consulting 或 Adobe 合作夥伴的參與。 如需詳細資訊，請聯絡您的 Adobe 代表。

  「其他」類型傳遞使用不執行流程的特定技術範本：這可讓他們管理在 Adobe Campaign 平台外部執行的行銷活動。

  此管道沒有特定機制。 、此一般管道有其專屬的外部帳戶路由選項、傳送範本類型和行銷活動工作流程活動，就像 Adobe Campaign 提供的任何其他通訊管道一樣。 此管道專為描述性用途而設計，例如，定義您想要對其在 Adobe Campaign 以外的工具執行之行銷活動目標保持追蹤的傳送。

## 傳遞型別 {#types-of-deliveries}

Campaign 的傳遞物件有三種：

### 單次傳遞 {#single-delivery}

 **傳遞**&#x200B;是執行一次的獨立傳送物件。 它可以複製、重新準備，但只要處於最終狀態 (取消、停止、完成)，就無法重複使用。

您可以從傳遞清單建立傳遞，或透過在工作流程中建立[傳遞](../../automation/workflow/delivery.md)活動。

工作流程也會根據您想使用的管道類型，提供特定的傳遞活動。 有關這些活動的詳細資訊，請參閱[本節](../../automation/workflow/cross-channel-deliveries.md)。

### 週期性傳遞 {#recurring-delivery}

**定期傳遞**&#x200B;可在工作流程的內容中使用。 它可讓您每次執行活動時，建立新的傳送。這可避免您必須為週期性任務建立新的傳送。例如，如果您每月執行一次這類活動，一年後最終將有 12 次傳遞。

定期傳遞是透過在工作流程中建立[定期傳遞活動](../../automation/workflow/recurring-delivery.md)。本節將介紹此活動使用方式的範例：[在目標工作流程中建立定期傳送](../../automation/workflow/send-a-birthday-email.md)。

### 持續傳遞 {#continuous-delivery}

**持續傳遞**&#x200B;可在工作流程的內容中使用。它可讓您將新收件者新增至現有傳遞，避免每次執行時都必須建立新傳遞。

如果傳送中的資訊變更 (內容、名稱等)，則會在傳送執行時建立新的傳送物件。如果未變更任何資訊，則會重複使用相同的傳遞對象，並將傳送和追蹤記錄新增至相同的物件中。

例如，如果您每月執行一次這類活動，一年後會收到單一傳送 (前提是您未對傳送進行任何變更)。

持續傳遞在工作流程中，透過[持續傳遞活動](../../automation/workflow/continuous-delivery.md)建立。

## Personalization功能 {#personalization}

Adobe Campaign 傳送的資訊可以透過多種方式實現個人化。[進一步瞭解個人化功能](../send/personalize.md)

您可以：

* 插入動態的個人化欄位。[了解更多](../send/personalization-fields.md)
* 插入預先定義的個人化區塊。[了解更多](../send/personalization-blocks.md)
* 建立有條件的內容。[了解更多](../send/conditions.md)


## 追蹤和監視 {#gs-tracking-logs}

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 您可以在傳送傳遞後進行監視，並瞭解傳送失敗和隔離的管理方式。

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}中瞭解如何監視傳遞
