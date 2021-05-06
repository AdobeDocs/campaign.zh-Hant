---
solution: Campaign Classic
product: campaign
title: 開始使用促銷活動自動化
description: 開始使用促銷活動自動化
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 1bdc1f03a824f8867ae6066196e8e3984fa73af7
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# 管理和自動化流程

設定Campaign以運用強大的行銷宣傳自動化功能。

您可以設定：

* 工作流程
* 週期性促銷活動
* 端對端驗證週期
* 警報
* 自動傳送報表
* 觸發事件

## 設計和使用工作流程{#gs-ac-wf}

使用Adobe Campaign工作流程來改善行銷宣傳的各個層面，從建立細分、準備訊息到傳遞，都能提升其速度和規模。

進一步瞭解這些章節中的工作流程：

* [開始使用工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* 工作流程活動
   * [定位活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html):查詢、讀取清單、擴充、聯合等
   * [流量控制活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html):排程器、分叉、警報、外部信號等
   * [行動活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):跨通道傳送、Javascript程式碼、CRM活動、更新匯總等
   * [活動](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):檔案傳輸、網路下載等等
* [透過端對端使用案例學習](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [在行銷宣傳工作流程中建立觀眾](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [內建技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [監控工作流程執行](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## 設定週期性促銷活動

每次執行時，都會重複設計並建立新的傳送例項。 例如，如果您的工作流程設計為每週執行一次，則一年後會產生52次傳送。 這也表示記錄檔將依每個傳送例項分開。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)中建立循環促銷活動。

## 設定端對端驗證週期

為傳送的每個步驟設定核准程式，並確保完整監控和控制行銷促銷活動的各種程式：定位、內容、預算、擷取和傳送證明。

通知會傳送給設為審核者的Adobe Campaign營運商，以通知他們核准要求。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html)中設定和管理核准程式。


## 傳送警報

身為促銷活動運算子，您可以在發生錯誤時接收警報。

您可以建立工作流程，讓您監控一組工作流程的狀態，並傳送循環訊息給主管。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow)中建立工作流程以監控其他工作流程的狀態。

您也可以在發生故障時收到警報

## 傳送自動報表

:arrow_upper_right:瞭解如何自動將報表傳送至運算子清單[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list)。


## 運用觸發事件

使用「促銷活動交易訊息」，自動化從資訊系統觸發的事件產生的訊息。 例如，這些交易訊息可以是發票、訂單確認、出貨確認、密碼變更、產品不可用通知、帳戶對帳單或網站帳戶建立。 這些訊息可個別傳送或透過電子郵件、簡訊或推播通知批次傳送。

:arrow_upper_right:進一步瞭解[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging)中的事務性消息傳遞功能。


連接Adobe Campaign和Adobe Analytics以擷取使用者動作並傳送近乎即時的個人化訊息。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud)中整合Campaign與Analytics觸發器。

：球：瞭解如何在[本節](../start/connect.md)中將Campaign與其他解決方案整合
