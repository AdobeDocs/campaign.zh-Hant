---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3a63539bc6bb20fa79bdac76dd60efe7b232458b
workflow-type: ht
source-wordcount: '478'
ht-degree: 100%

---

# 最新版本{#latest-release}

Adobe Campaign 會定期更新。此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。Adobe 強烈建議所有客戶升級至最新版本。[在本頁中](upgrades.md)進一步瞭解 Campaign 版本和建議。

作為 Managed Cloud Services 使用者，您的執行個體會隨著每個新發行版本由 Adobe 升級。Adobe 將會聯絡您並升級您的環境。Campaign 用戶端主控台&#x200B;**必須升級至與 Campaign 伺服器相同的版本**。 透過[本頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

此外，身為客戶，請確定您使用的是列於[相容性矩陣](compatibility-matrix.md)的最新受支援系統版本。


## 發行版本 8.6.2 {#release-8-6-2}

_2024 年 2 月 23 日_

### 修正 {#fixes-8-6-2}

此版本修正下列問題：

* 修正了中間來源執行個體上可能發生的效能問題 (NEO-72595)。

## 發行版本 8.6.1 {#release-8-6-1}

_2024 年 2 月 14 日_

### 新功能 {#new-8-6-1}

* 自此版本起，您即可存取可透過中央 Adobe Experience Cloud 環境使用的新的 **Campaign Web 使用者介面**。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。[在此頁面中](campaign-ui.md#ac-web-ui)了解如何連線至 Adobe Experience Cloud，以及存取 Adobe Campaign Web 介面。


* Adobe Campaign v8 現在已與 **Adobe Experience Manager as a Cloud Service** 整合，可透過 Adobe Campaign Web 使用者介面獨家製作。[了解更多](../connect/ac-aem.md)

*  即使與 Adobe Experience Cloud 套件的整合安裝在您的 Adobe Campaign 執行個體上，您現在也可以一併使用 **Adobe Experience Manager Assets 資料庫**&#x200B;與 Experience Cloud Assets。 [了解更多](../connect/ac-aem.md#assets-library)

### 一般改善 {#improvements-8-6-1}

* Campaign v8.6 改善了&#x200B;**電子郵件傳遞追蹤指標**&#x200B;的輸送量。透過我們的最佳化程式，追蹤擷取和運算的時間得以減少，而且您可以更快檢查傳遞的關鍵指標。


### 傳遞能力更新 {#deliverability-8-6-1}

* 到 2024 年 2 月，任何透過 Google 或 Yahoo! 傳送超過 5,000 則電子郵件訊息的公司將必須開始使用稱為網域型訊息驗證報告和符合性 (DMARC) 的驗證技術。請務必為您搭配 Adobe Campaign 使用的所有子網域設定 DMARC 記錄。[了解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hant){target="_blank"}

* 2024 年 6 月 1 日起，Google 和 Yahoo! 將要求寄件者遵守一鍵式清單取消訂閱規範。Adobe Campaign 現在支援此選項。[了解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=zh-Hant#one-click-list-unsubscribe){target="_blank"}


### 修正 {#fixes-8-6-1}

此版本已修正下列問題：
NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580、NEO-61199、NEO-60786、NEO-59544、NEO-59198、NEO-59059、NEO-58637、NEO-55197、NEO-52542、NEO-50488、NEO-47789