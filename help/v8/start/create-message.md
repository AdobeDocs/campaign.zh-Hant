---
title: 開始使用訊息
description: 開始使用訊息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: d6160d927601f66f450553a6dd6f91d74b0b1104
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 29%

---

# 開始使用訊息{#gs-ac-audiences}

透過 Adobe Campaign，您可以傳送跨頻道行銷活動，包括電子郵件、簡訊、LINE 訊息、推播通知和直接郵件，並使用各種專屬報告來評估行銷成效。 這些訊息是透過傳遞進行設計和傳送，而且可針對每位收件者進行個人化。

核心功能包括目標定位、定義和個人化訊息、通訊執行及相關的營運報告。 主要功能存取點是傳送助理。 此存取點可導向 Adobe Campaign 涵括的多種功能。

Adobe Campaign v8 提供下列傳遞管道：

* **電子郵件管道**：電子郵件傳遞功能可讓您傳送個人化電子郵件給目標群體。[了解更多](#gs-channel-email)

* **行動裝置頻道**：行動裝置頻道上的傳遞可讓您在行動裝置上傳送個人化訊息給目標群體。 [了解更多](#gs-channel-sms)

* **行動應用程式頻道**：行動應用程式傳送可讓您傳送通知至iOS和Android裝置。 [了解更多](#gs-channel-push)

* **直接郵件頻道**：直接郵件傳遞可讓您產生擷取檔案，其中包含目標群體的資料。 [了解更多](#gs-channel-direct)


  其他管道的說明請參閱 [本節](#other-channels).

  >[!NOTE]
  >
  >可用管道的數量取決於您的合約。 請檢查您的授權合約。

## 選擇您的頻道{#gs-channel}

### 電子郵件管道 {#gs-channel-email}

此 [電子郵件頻道](../send/direct-mail.md) 是Adobe Campaign的核心管道之一，可讓您排程並傳送個人化電子郵件給特定目標。

您可以傳送不同型別的電子郵件：

* 單一傳送電子郵件：您可傳送一次給已定義目標的電子郵件。 它們通常用於促銷只需準備並傳送一次的特定內容（電子報、促銷電子郵件等）。
* 循環電子郵件：在行銷活動中，定期傳送相同的電子郵件，並定期彙總每個傳送及其報告。 會根據傳送當天符合資格的目標，傳送相同的電子郵件，但通常傳送給不同的目標。 常見的範例是生日電子郵件。 有關詳細資訊，請參閱 [週期性傳遞](../../automation/workflow/recurring-delivery.md).
* 異動電子郵件：根據客戶行為觸發的單一電子郵件。 請參閱 [異動訊息傳送](../send/transactional.md).

若要瞭解傳遞使用方式和建議，請參閱Adobe Campaign Classic [傳遞最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

如需不同型別傳送的詳細資訊，請參閱 [本節](#types-of-deliveries).

### 行動裝置頻道 {#gs-channel-sms}

Adobe Campaign可讓您提供 [簡訊](../send/sms.md) 和 [折線圖](../send/line.md) 在行動裝置上的訊息。

對於SMS訊息，您只能以文字格式建立、修改和個人化訊息。 您也可以在傳送SMS訊息之前先預覽訊息。

對於LINE訊息，您可以傳送文字或影像與連結。

若要將SMS或LINE訊息傳送到行動電話，您需要：

* 在上設定的外部帳戶 **[!UICONTROL Mobile (SMS)]** 頻道或在 **[!UICONTROL LINE]** 頻道。
* 正確連結至此外部帳戶的SMS或LINE傳遞範本。


### 推播通知管道 {#gs-channel-push}

您可以使用Adobe Campaign來傳送個人化和分段 [推播通知](../send/push.md) 在iOS和Android行動裝置上，透過專用應用程式。 執行設定和整合步驟後，即可透過Adobe Campaign建立iOS和Android傳遞並傳送。 您也可以設計包含影像或視訊的豐富通知，並傳送至Android裝置。

### 直接郵件管道 {#gs-channel-direct}

[直接郵件](../send/direct-mail.md) 是離線頻道，可讓您建立、個人化並產生外部檔案，以與直接郵件供應商共用。 使用此頻道在您的客戶歷程中協調線上和離線頻道。

當您準備直接郵件傳送時，Adobe Campaign 會產生一個檔案，其中包含所有目標設定檔和選取的聯絡資訊（例如，郵遞區號）。然後，您可以將此檔案傳送給直接郵件提供者，由他們負責實際傳送。


### 其他管道 {#other-channels}

Adobe Campaign也隨附電話傳遞範本，此範本可用來建立外部傳遞。 使用此管道表示您實作專用方法來處理輸出檔案。 設定步驟與相同 [直接郵件頻道](../send/direct-mail.md).

>[!NOTE]
>
>電話管道不是內建管道。 其實作需要Adobe諮詢或Adobe合作夥伴的參與。 如需詳細資訊，請洽詢您的Adobe代表。

「其他」型別傳遞使用不會執行流程的特定技術範本：這可讓他們管理在Adobe Campaign平台外部執行的行銷動作。

此管道沒有特定機制。 此一般管道有其專屬的外部帳戶路由選項、傳送範本型別和行銷活動工作流程活動，就像Adobe Campaign中提供的任何其他通訊管道一樣。 此管道專為描述性用途而設計，例如，定義您想要對其在Adobe Campaign以外的工具中執行的行銷活動目標保持追蹤的傳送。

## 選擇傳遞型別 {#types-of-deliveries}

Campaign中有三種型別的傳遞物件：

### 單次傳遞 {#single-delivery}

A **傳遞** 是獨立傳送物件，只會執行一次。 它可以複製、重新準備，但只要處於最終狀態（已取消、已停止、已完成），就無法重複使用。

您可以從傳遞清單建立傳遞，或透過在工作流程中建立 [傳遞](../../automation/workflow/delivery.md) 活動。

工作流程也會根據您想使用的管道型別，提供特定的傳送活動。 有關這些活動的詳細資訊，請參閱 [本節](../../automation/workflow/cross-channel-deliveries.md).

### 重複傳送 {#recurring-delivery}

A **循環傳遞** 可在工作流程的內容中使用。 它可讓您每次執行活動時，都建立新的傳送。 這可避免您必須為週期性任務建立新的傳送。 例如，如果您每月執行一次這類活動，一年後最終將有12次傳遞。

循環傳遞是透過在工作流程中建立 [循環傳遞活動](../../automation/workflow/recurring-delivery.md). 本章節將介紹此活動使用方式的範例： [在目標工作流程中建立循環傳送](../../automation/workflow/send-a-birthday-email.md).

### 持續傳遞 {#continuous-delivery}

A **持續傳遞** 可在工作流程的內容中使用。 它可讓您將新收件者新增至現有傳遞，以避免每次執行時都必須建立新傳遞。

如果傳送中的資訊變更（內容、名稱等），會在傳送執行時建立新的傳送物件。 如果未變更任何資訊，則會重複使用相同的傳送物件，並將傳送和追蹤記錄新增至相同的物件中。

例如，如果您每月執行一次這類活動，一年後最後會收到單一傳送（假設您未對傳送進行任何變更）。

在工作流程中，透過以下方式建立持續傳遞： [持續傳遞活動](../../automation/workflow/contin).


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

  異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

  在[本節](../architecture/architecture.md#transac-msg-archi)進一步瞭解異動訊息功能

  [本頁面](../send/transactional.md)詳細說明了設定及傳送異動訊息的步驟

* 排程您的訊息

  ![](assets/schedule-send.png)

  瞭解如何在中排程傳送作業 [此頁面](../send/configure-and-send.md)

  另請參閱此 [使用案例：瞭解如何排程並傳送生日電子郵件](../../automation/workflow/send-a-birthday-email.md)


## 新增個人化{#personalization}

Adobe Campaign 傳送的資訊可以透過多種方式實現個人化。[進一步瞭解個人化功能](../send/personalize.md)

您可以：

* 插入動態的個人化欄位。[了解更多](../send/personalization-fields.md)
* 插入預先定義的個人化區塊。[了解更多](../send/personalization-blocks.md)
* 建立有條件的內容。[了解更多](../send/conditions.md)


## 傳送和追蹤記錄{#gs-tracking-logs}

傳送傳遞後進行監視是確保行銷活動效率並與客戶溝通的關鍵步驟。 您可以在傳送傳遞後進行監視，並瞭解傳送失敗和隔離的管理方式。

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}瞭解如何監視傳遞

