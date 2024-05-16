---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 166fe487aa169f47f9da86c2990acb1f6dff430e
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 97%

---

# 最新版本{#latest-release}

Adobe Campaign 會定期更新。此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。Adobe 強烈建議所有客戶升級至最新版本。

作為 Managed Cloud Services 使用者，您的執行個體會隨著每個新發行版本由 Adobe 升級。Adobe 將會聯絡您並升級您的環境。Campaign 用戶端主控台&#x200B;**必須升級至與 Campaign 伺服器相同的版本**。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

此外，身為客戶，請確定您使用的是列於[相容性矩陣](compatibility-matrix.md)的最新受支援系統版本。

## 發行版本 8.7.1 {#release-8-7-1}

_2024 年 5 月 2 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至Campaign v8的Campaign Standard使用者，請在中進一步瞭解此轉換 [Campaign v8網頁使用者介面檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### 新功能 {#new-8-7-1}

* **豐富推播通知範本** - 您現可透過 Android 傳送豐富推播通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 [顯示全文](../send/rich-push.md)。

* **品牌化** - 作為 Campaign Standard 移轉使用者，您的技術管理員現可定義一個或多個品牌，以便集中影響品牌識別的參數。 這包括品牌標誌、登陸頁面存取 URL 之網域或訊息追蹤設定。您可以建立這些品牌，並將其連結至訊息或登陸頁面。 此設定在範本中管理。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-Hant){target="_blank"}

* **Rest API** - 作為 Campaign Standard 移轉使用者，您可使用 Rest API 來建立 Adobe Campaign 整合，並將 Adobe Campaign 與您使用的技術面板結合，以便建立您自己的生態系統。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=zh-Hant){target="_blank"}

* **動態報告** - 作為 Campaign Standard 移轉使用者，您可存取動態報告，其提供完全可自訂的即時報告，以便測量行銷活動的影響。 其可新增對設定檔資料的存取權，除了功能性電子郵件行銷活動資料 (如開啟和點按) 外，還可依設定檔維度 (例如，性別、城市和年齡) 進行人口統計分析。[閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-Hant){target="_blank"}

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### 相容性更新 {#comp-8-7-1}

現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。 在[本頁](compatibility-matrix.md#FederatedDataAccessFDA)中深入瞭解。

### 一般改善 {#improvements-8-7-1}

* 數個結構描述已從 32 位元變更為 64 位元。 這僅適用從 Campaign Standard 移轉的客戶。 [顯示全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=zh-Hant)。

* 在 Campaign 表格，新標幟可讓您針對 lastModified、created 以及 createdBy-id 屬性進行修改。 當標幟開啟時，會忽略使用者提供給這些屬性的值。 僅使用伺服器時間與使用者內容的 ID。 當標幟關閉時，會採用使用者提供給這些屬性的值。 ignoreTimestampsID 標幟位於「共用」節點下的 serverConf.xml。

### 修正 {#fixes-8-7-1}

此版本已修正下列問題：
NEO-72648、NEO-71534、NEO-71473、NEO-70263、NEO-70195、NEO-69651、NEO-68704、NEO-68192、NEO-67814、NEO-67702、NEO-67620、NEO-66022、NEO-65774、NEO-65633、NEO-64199、NEO-63706、NEO-63705、NEO-63287、NEO-63197、NEO-62575、NEO-60250、NEO-60192、NEO-58596、NEO-58314、NEO-58004、NEO-40054

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