---
product: campaign
title: 在Adobe Campaign中監視傳遞能力
description: 瞭解Adobe Campaign中傳遞能力監視的工具和准則
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# 監視您的傳遞能力{#monitoring-deliverability}

在下方，您會找到Adobe Campaign所提供各種監控工具的詳細資訊，以及運用Adobe Campaign所提供功能來監控平台傳遞能力的一些其他准則。

## 監控工具 {#monitoring-tools}

Adobe Campaign可讓您存取下列所有傳遞工具。

* [收件匣轉譯報告](inbox-rendering.md)可讓您預覽主要電子郵件使用者端上的郵件，以掃描內容與信譽。

* **[!UICONTROL Delivery throughput]**&#x200B;報告提供指定期間內整個平台的輸送量概觀。 如需詳細資訊，請參閱[本節](../reporting/global-reports.md#delivery-throughput)。
* 每次傳送都會產生不同網際網路服務提供者(ISP)的廣播統計報表。 它會顯示一些可能影響您傳送能力的資料品質和信譽量度，包括下列數字：
   * **[!UICONTROL Hard bounces]**&#x200B;表示資料品質。 此數字應小於2%。
   * **[!UICONTROL Soft bounces]**&#x200B;表示信譽。 任何特定ISP的這個數字都不應超過10%。

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* 一般而言，[傳遞儀表板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}可讓您存取：
   * 傳送摘要，顯示傳送的詳細資訊，以及成功傳送、處理和傳送的訊息數目；
   * 傳送記錄與歷史記錄，顯示已排除的目標以及排除原因；
   * 追蹤記錄，會顯示開啟和點按次數等追蹤資訊。

## 監視指南 {#monitoring-guidelines}

以下是傳遞能力監視的其他准則：

* 定期檢查整個平台的[傳遞輸送量](../reporting/global-reports.md#delivery-throughput)，以確認其是否與原始設定一致。
* 檢查傳遞範本中的[重試](delivery-failures.md#retries)是否已正確設定（重試期間為30分鐘，重試次數超過20次）。
* 定期確認[退信](delivery-failures.md#bounce-mail-qualification)信箱可存取，且帳戶不會過期。
* 檢查可從[傳遞儀表板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}存取的每個傳遞輸送量，以確保其與傳遞內容的有效性一致（例如，「Flash銷售」應在幾分鐘內傳遞，而非幾天）。 是重要的工具，用於監視傳送訊息期間的傳遞情況和潛在問題。
* 使用[波段](configure-and-send.md#sending-using-multiple-waves)時，請確認每個波段都有足夠的時間完成，才能觸發下一個波段。
* 檢查錯誤數目和新的[隔離](quarantines.md)是否與其他傳遞一致。
* 仔細查閱[傳遞記錄](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"}以詳細檢查反白顯示的錯誤型別（封鎖清單、DNS問題、反垃圾郵件規則等）。
