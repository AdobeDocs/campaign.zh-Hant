---
title: Campaign v8 （主控台） 2023年發行說明
description: 2023 Campaign v8 版本隨附的功能與改進清單
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: fe96eb65ac04fc2b89f0dfe1e8ed4286223c3f85
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 92%

---

# 2024 年發行說明 {#2024-rn}

此頁面列出&#x200B;**2024 Campaign v8版本**&#x200B;的新功能、改善和修正。

>[!BEGINSHADEBOX]

**在此頁面**

* Campaign v8.7 - [版本8.7.1](#release-8-7-1) | [版本8.7.2](#release-8-7-2)
* Campaign v8.6 - [版本8.6.1](#release-8-6-1) | [版本8.6.2](#release-8-6-2) | [版本8.6.3](#release-8-6-3)
* Campaign v8.5 - [版本8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]


## 發行版本 8.7.2 {#release-8-7-2}

_2024 年 9 月 3 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-2}

* **新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充連接器。[閱讀全文](../send/sms/sms.md)。

* **豐富推播通知 (GA)** - 您現在可以傳送豐富推播通知。豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* **品牌化** - 品牌化選項現在可供所有管道使用，包括 SMS 和直接郵件。[閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hant){target="_blank"}

### 修正 {#fixes-8-7-2}

此版本已修正下列問題：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。



## 發行版本 8.7.1 {#release-8-7-1}

_2024 年 5 月 2 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-1}

* **豐富推播通知範本** - 您現可透過 Android 傳送豐富推播通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 [閱讀全文](../send/rich-push-ios.md)。

* **品牌化** - 作為 Campaign Standard 移轉使用者，您的技術管理員現可定義一個或多個品牌，以便集中影響品牌識別的參數。 這包括品牌標誌、登陸頁面存取 URL 之網域或訊息追蹤設定。您可以建立這些品牌，並將其連結至訊息或登陸頁面。 此設定在範本中管理。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hant){target="_blank"}

* **Rest API** - 作為 Campaign Standard 移轉使用者，您可使用 Rest API 來建立 Adobe Campaign 整合，並將 Adobe Campaign 與您使用的技術面板結合，以便建立您自己的生態系統。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=zh-hant){target="_blank"}

* **動態報告** - 作為 Campaign Standard 移轉使用者，您可存取動態報告，其提供完全可自訂的即時報告，以便測量行銷活動的影響。 其可新增對輪廓資料的存取權，除了功能性電子郵件行銷活動資料 (如開啟和點按) 外，還可依輪廓維度 (例如，性別、城市和年齡) 進行人口統計分析。[閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-hant){target="_blank"}

### 相容性更新 {#comp-8-7-1}

* 現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。 在[本頁](compatibility-matrix.md#FederatedDataAccessFDA)中深入瞭解。

### 移轉至 OAuth 伺服器對伺服器認證 {#change-8-7-1}

自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 Adobe 會針對您的傳出整合執行 JWT 到 OAuth 的移轉，例如 Campaign-Analytics 整合或 Experience Cloud 觸發器整合。

如果您已實施與 Campaign 的傳入整合，您必須按照[本文件](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}中詳細說明移轉您的技術帳戶。現有服務帳戶 (JWT) 憑證將繼續有效至 **2025 年 1 月 27 日**。

### 一般改善 {#improvements-8-7-1}

* 數個結構描述已從 32 位元變更為 64 位元。 這僅適用從 Campaign Standard 移轉的客戶。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=zh-Hant){target="_blank"}

* 在 Campaign 表格中，下列屬性現在預設會依伺服器日期和時間填入：`lastModified` 和 `created`。此 `createdBy-id` 屬性值現在會依預設填入目前登入的 ID。 系統會忽略使用者在 API 呼叫中提供的值。<!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

### 修正 {#fixes-8-7-1}

此版本已修正下列問題：

NEO-72648、NEO-71534、NEO-71473、NEO-70263、NEO-70195、NEO-69651、NEO-68704、NEO-68192、NEO-67814、NEO-67702、NEO-67620、NEO-66022、NEO-65774、NEO-65633、NEO-64199、NEO-63706、NEO-63705、NEO-63287、NEO-63197、NEO-62575、NEO-60250、NEO-60192、NEO-58596、NEO-58314、NEO-58004、NEO-40054



## 發行版本 8.6.3 {#release-8-6-3}

_2024 年 7 月 30 日_

### 新功能 {#new-8-6-3}

* **豐富推播通知** - 您現在可以傳送豐富推播通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* 自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](release-notes-2024.md#change-8-7-1)

### 一般改善 {#improvements-8-6-3}

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

### 修正 {#fixes-8-6-3}

此版本已修正下列問題：

NEO-79328、NEO-78843、NEO-77795、NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## 2024年5月更新 {#may-updates}

下列變更已在 5 月發行，現在已經可供 Campaign v8 使用者使用：

* **新的增強式安全性附加元件**：為了讓您的網路連線更安全，並為您的資源提供更高的安全性，Adobe Campaign 提供新的增強安全性附加元件，其中包括兩項功能：安全 CMK 整合和安全 VPN 通道。 [閱讀更多](../config/enhanced-security.md)

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

NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580 NEO-61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789



## 發行版本 8.5.3 {#release-8-5-3}

_2024 年 5 月 28 日_

### 移轉至 OAuth 伺服器對伺服器認證 {#change-8-5-3}

自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](#change-8-7-1)

### 修正 {#fixes-8-5-3}

此版本已修正下列問題：

NEO-70263、NEO-64984、NEO-63657、NEO-63387、NEO-62964、NEO-62750、NEO-62686、NEO-59544、NEO-52542