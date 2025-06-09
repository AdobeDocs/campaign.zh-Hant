---
title: Campaign v8 （主控台） 2025年發行說明
description: 2025 Campaign v8 版本隨附的功能與改進清單
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 65%

---

# 2025 年發行說明 {#2025-rn}

此頁面列出&#x200B;**2025 Campaign v8版本**&#x200B;的新功能、改善和修正。 最新發行版本列於[此頁面](release-notes.md)。

>[!BEGINSHADEBOX]

**在此頁面**

* Campaign v8.7 - [版本8.7.2](#release-8-7-2) | [版本8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]


## 發行版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>身為Campaign Standard使用者轉換至Campaign v8，請在[Campaign v8網頁使用者介面檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步瞭解此轉換。

### 新功能 {#features-8-7-3}

* **異動訊息的動態報告** — 您現在可以在動態報告使用者介面中監視異動訊息。 這些報表可讓行銷人員即時檢視異動訊息的所有報表量度和維度，以及透過範本傳送的傳送劃分。 [閱讀更多](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **異動訊息REST API** — 事件型異動API現在可用於電子郵件。 [閱讀更多](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### 修正 {#fixes-8-7-3}

此版本已修正下列問題：

Neo-79373、NEO-81908、NEO-83081

## 發行版本 8.7.2 {#release-8-7-2}

_2024 年 9 月 3 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>身為Campaign Standard使用者轉換至Campaign v8，請在[Campaign v8網頁使用者介面檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步瞭解此轉換。

### 新功能 {#new-8-7-2}

* **新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充連接器。[閱讀全文](../send/sms/sms.md)。

* **豐富推播通知 (GA)** - 您現在可以傳送豐富推播通知。豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* **品牌化** - 品牌化選項現在可供所有管道使用，包括 SMS 和直接郵件。[閱讀更多](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hant){target="_blank"}

### 修正 {#fixes-8-7-2}

此版本已修正下列問題：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。
