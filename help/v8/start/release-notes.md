---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 0c13ee22a7d40aaa9a8c27d3450ec3275a02748f
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 93%

---

# 最新版本 {#latest-release}

Adobe Campaign 會定期更新。此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。Adobe 強烈建議所有客戶升級至最新版本。本頁面列出 Campaign v8 (主控台) 最新版本中的新功能、改善和修正。[在本頁](upgrades.md)進一步了解 Campaign 版本和更新。

作為 Managed Cloud Services 使用者，您的執行個體會隨著每個新發行版本由 Adobe 升級。Adobe 將會聯絡您並升級您的環境。Campaign 用戶端主控台&#x200B;**必須升級至與 Campaign 伺服器相同的版本**。 透過[本頁](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

此外，身為客戶，請確定您使用的是列於[相容性矩陣](compatibility-matrix.md)的最新受支援系統版本。


## 發行版本 8.6.3 {#release-8-6-3}

_2024年7月30日_

### 新功能 {#new-8-6-3}

* **豐富推送通知** — 您現在可以傳送豐富推送通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 此版本中，豐富推送通知的一組範本現在可供您的iOS和Android應用程式使用。 [閱讀全文](../send/rich-push-android.md)。

* 自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](release-notes.md#change-8-7-1)

### 一般改善 {#improvements-8-6-3}

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

### 修正 {#fixes-8-6-3}

此版本已修正下列問題：

NEO-79328、NEO-78843、NEO-77795、NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## 發行版本 8.5.3 {#release-8-5-3}

_2024 年 5 月 28 日_

### 移轉至 OAuth 伺服器對伺服器認證 {#change-8-5-3}

自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](#change-8-7-1)

### 修正 {#fixes-8-5-3}

此版本已修正下列問題：

NEO-70263、NEO-64984、NEO-63657、NEO-63387、NEO-62964、NEO-62750、NEO-62686、NEO-59544、NEO-52542


## 5 月更新 {#may-updates}

下列變更已在 5 月發行，現在已經可供 Campaign v8 使用者使用：

* **新的增強式安全性附加元件**：為了讓您的網路連線更安全，並為您的資源提供更高的安全性，Adobe Campaign 提供新的增強安全性附加元件，其中包括兩項功能：安全 CMK 整合和安全 VPN 通道。 [閱讀更多](../config/enhanced-security.md)


## 發行版本 8.7.1 {#release-8-7-1}

_2024 年 5 月 2 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-1}

* **豐富推播通知範本** - 您現可透過 Android 傳送豐富推播通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 [閱讀全文](../send/rich-push-ios.md)。

* **品牌化** - 作為 Campaign Standard 移轉使用者，您的技術管理員現可定義一個或多個品牌，以便集中影響品牌識別的參數。 這包括品牌標誌、登陸頁面存取 URL 之網域或訊息追蹤設定。您可以建立這些品牌，並將其連結至訊息或登陸頁面。 此設定在範本中管理。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-Hant){target="_blank"}

* **Rest API** - 作為 Campaign Standard 移轉使用者，您可使用 Rest API 來建立 Adobe Campaign 整合，並將 Adobe Campaign 與您使用的技術面板結合，以便建立您自己的生態系統。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=zh-Hant){target="_blank"}

* **動態報告** - 作為 Campaign Standard 移轉使用者，您可存取動態報告，其提供完全可自訂的即時報告，以便測量行銷活動的影響。 其可新增對設定檔資料的存取權，除了功能性電子郵件行銷活動資料 (如開啟和點按) 外，還可依設定檔維度 (例如，性別、城市和年齡) 進行人口統計分析。[閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-Hant){target="_blank"}

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
