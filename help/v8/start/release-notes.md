---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 2dbe73df0cbc194ec6c239e13851395a0b94c991
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 16%

---

# 最新版本{#latest-release}

Adobe Campaign 會定期更新。此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。Adobe強烈建議所有客戶升級至最新版本。 深入瞭解Campaign版本和建議 [在此頁面中](upgrades.md).

作為「受管理的Cloud Service」使用者，您的執行個體會隨著每個新版本進行Adobe升級。 Adobe將會聯絡您並升級您的環境。 Campaign使用者端主控台 **必須升級至相同版本** 做為Campaign伺服器。 在此瞭解如何升級您的使用者端主控台 [頁面](../start/connect.md#upgrade-ac-console).

此外，身為客戶，請確定您使用的系統為 [相容性矩陣](compatibility-matrix.md).


## 發行版本8.6.1 {#release-8-6-1}

_2024年2月14日_


### 新功能 {#new-8-6-1}

* 自此版本起，您即可存取新的 **Campaign Web使用者介面**，可透過中央Adobe Experience Cloud環境取得。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。瞭解如何連線至Adobe Experience Cloud及存取Adobe Campaign網頁介面 [在此頁面中](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8現在已與 **Adobe Experience Manager as a Cloud Service**，可透過Adobe Campaign網頁使用者介面獨家製作。 [了解更多](../connect/ac-aem.md)

* 您現在可以使用 **Adobe Experience Manager Assets資料庫** 即使在您的Adobe Campaign執行個體上安裝與Adobe Experience Cloud套件的整合，仍會與您的Experience Cloud資產一併安裝。[了解更多](../connect/ac-aem.md)

### 一般改善 {#improvements-8-6-1}

* Campaign v8.6改善以下專案的輸送量： **電子郵件傳遞追蹤指標**. 透過我們的最佳化程式，追蹤擷取和運算時間得以減少，而且您可以更快檢查傳送的關鍵指標。


### 傳遞能力更新 {#deliverability-8-6-1}

* 到2024年2月，任何透過Google或Yahoo！傳送超過5,000則電子郵件訊息的公司 將必須開始使用稱為網域型訊息驗證報告和符合性(DMARC)的驗證技術。 請務必為您搭配Adobe Campaign使用的所有子網域設定DMARC記錄。 [瞭解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hant){target="_blank"}

* 2024年6月1日起，Google和Yahoo！ 要求寄件者遵守一鍵式清單取消訂閱規範。 Adobe Campaign現在支援此選項。 [瞭解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### 修正 {#fixes-8-6-1}

此版本已修正下列問題： NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406， NEO-61580， NEO-61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789