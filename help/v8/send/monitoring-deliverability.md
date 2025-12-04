---
product: campaign
title: 在Adobe Campaign中監視傳遞能力
description: 瞭解Adobe Campaign中傳遞能力監視的工具和准則
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# 監視您的傳遞能力{#monitoring-deliverability}

在下方，您會找到Adobe Campaign所提供各種監控工具的詳細資訊，以及運用Adobe Campaign所提供功能來監控平台傳遞能力的一些其他准則。

## 監控工具 {#monitoring-tools}

Adobe Campaign可讓您存取下列傳遞工具。

### 收件匣轉譯 {#inbox-rendering-tool}

[收件匣轉譯報告](inbox-rendering.md)可讓您預覽主要電子郵件使用者端上的郵件，以掃描內容與信譽。

### 傳遞總處理能力 {#throughput-reports}

**[!UICONTROL Delivery throughput]**&#x200B;報告提供指定期間內整個平台的輸送量概觀。 如需詳細資訊，請參閱[本節](../reporting/global-reports.md#delivery-throughput)。

### 廣播統計資料 {#broadcast-statistics}

每次傳送都會產生不同網際網路服務提供者(ISP)的廣播統計報表。 它會顯示一些可能影響您傳送能力的資料品質和信譽量度，包括下列數字：

**[!UICONTROL Hard bounces]**&#x200B;表示資料品質。 此數字應小於2%。

**[!UICONTROL Soft bounces]**&#x200B;表示信譽。 任何特定ISP的這個數字都不應超過10%。

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### 傳遞儀表板 {#delivery-dashboard-monitoring}

一般而言，[傳遞儀表板](delivery-dashboard.md)可讓您存取：

傳遞摘要，顯示傳送的詳細資訊，以及成功傳送、處理和傳送的訊息數。

傳送記錄檔和歷史記錄，顯示已排除的目標以及排除原因。

追蹤記錄，顯示開啟和點按次數等追蹤資訊。

### SpamAssassin測試 {#spam-testing}

使用[SpamAssassin](spamassassin.md)測試您的電子郵件內容，並對它評分，以判斷郵件是否有被接收時所使用的反垃圾郵件工具視為垃圾郵件的風險。

### 控制面板 {#control-panel-monitoring}

>[!NOTE]
>
>「控制面板」適用於Campaign v8 Managed Cloud Services使用者。 深入瞭解[控制面板](../config/self-service.md)。

Campaign [控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant){target="_blank"}提供傳遞能力的監視功能，包括子網域和憑證管理、作用中設定檔監視，以及傳遞輸送量和延遲量度。

## 監視指南 {#monitoring-guidelines}

以下是傳遞能力監視的其他准則：

### 平台輸送量監控

定期檢查整個平台的[傳遞輸送量](../reporting/global-reports.md#delivery-throughput)，以確認其是否與原始設定一致。

### 重試設定

檢查傳遞範本中的[重試](delivery-failures.md#retries)是否已正確設定（重試期間為30分鐘，重試次數超過20次）。

### 退回信箱驗證

定期確認[退信](delivery-failures.md#bounce-mail-qualification)信箱可存取，且帳戶不會過期。

### 傳遞效能檢查

檢查可從[傳遞儀表板](delivery-dashboard.md)存取的每個傳遞輸送量，以確保其與傳遞內容的有效性一致（例如，「Flash銷售」應在幾分鐘內傳遞，而非幾天）。

### 波段計時驗證

使用[波段](configure-and-send.md#sending-using-multiple-waves)時，請確認每個波段都有足夠的時間完成，才能觸發下一個波段。

### 隔離監視

檢查錯誤數目和新的[隔離](quarantines.md)是否與其他傳遞一致。

### 傳遞記錄分析

仔細查閱[傳遞記錄](delivery-dashboard.md#delivery-logs-and-history)以詳細檢查反白顯示的錯誤型別（封鎖清單、DNS問題、反垃圾郵件規則等）。

## 相關主題

[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}提供傳遞能力策略、定義、量度和最佳實務的全面指引。

[什麼是傳遞能力](about-deliverability.md)介紹了傳遞能力的重要概念，以及如何提高您在Campaign中的傳遞率。

[傳遞失敗和退信](delivery-failures.md)說明不同型別的傳遞失敗、Campaign如何處理這些失敗，並包含常見問題的疑難排解指引。

[隔離管理](quarantines.md)說明Campaign如何管理隔離地址，以保護您的傳送信譽。

[控制訊息內容](control-message-content.md)提供如何確保您的內容已針對傳遞能力最佳化的指引。
