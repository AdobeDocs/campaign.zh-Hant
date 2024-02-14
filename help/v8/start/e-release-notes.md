---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: eae364fb3d082c91022fee6bf29802c9eb6dfcf5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 22%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。在發行日期前，此內容可能會有所變更，恕不另行通知。 本[頁面](../start/release-notes.md)提供正式發行說明。

## 發行版本8.6.1 {#release-8-6-1}

_2024年2月14日_


### 新功能 {#new-8-6-1}

* 自此版本起，您即可存取新的 **Campaign Web使用者介面**，可透過中央Adobe Experience Cloud環境取得。 Experience Cloud 是 Adobe 的整合式數位行銷應用程式、產品和服務系列。您可以從其直覺式介面，快速存取雲端應用程式、產品功能和服務。瞭解如何連線至Adobe Experience Cloud及存取Adobe Campaign網頁介面 [在此頁面中](campaign-ui.md#ac-web-ui).

* 使用者端主控台的32位元版本現已棄用。 從8.6版開始，使用者端主控台將僅提供64位元版本。 使用者端主控台可順暢升級至64位元版本。 深入了解如何升級作業系統，請參閱此[技術說明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=zh-Hant)。


### 一般改善 {#improvements-8-6-1}

* Campaign v8.6改善以下專案的輸送量： **電子郵件傳遞追蹤指標**. 透過我們的最佳化程式，追蹤擷取和運算時間得以減少，而且您可以更快檢查傳送的關鍵指標。

* 您現在可以將Campaign v8執行個體連線至Azure synapse外部資料庫。 此連線透過新的外部帳戶進行管理。

* Adobe Campaign v8現在已與 **Adobe Experience Manager as a Cloud Service**，可透過Adobe Campaign網頁使用者介面獨家製作。

* 您現在可以使用 **Adobe Experience Manager Assets資料庫** 連同您的Experience Cloud資產，即使 **與Adobe Experience Cloud整合** 套件安裝在您的Adobe Campaign執行個體上。

* 您無法再從使用者端主控台建立運運算元。 您現在需要使用Admin Console。 [了解更多](../start/gs-permissions.md)。

* 已更新數個協力廠商工具，以最佳化安全性。

### 傳遞能力更新 {#deliverability-8-6-1}

* 到2024年2月，任何透過Google或Yahoo！傳送超過5,000則電子郵件訊息的公司 將必須開始使用稱為網域型訊息驗證報告和符合性(DMARC)的驗證技術。 請務必為您搭配Adobe Campaign使用的所有子網域設定DMARC記錄。 [瞭解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hant){target="_blank"}

* 2024年6月1日起，Google和Yahoo！ 要求寄件者遵守一鍵式清單取消訂閱規範。 Adobe Campaign現在支援此選項。 [瞭解更多](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### 修正 {#fixes-8-6-1}

此版本已修正下列問題： NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406， NEO-61580， NEO-61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789