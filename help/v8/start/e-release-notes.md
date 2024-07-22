---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 65efda7469c5ad35e8d03703951c3d1480b015f4
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。**在發行日期之前，以下早期發行說明如有更改，恕不另行通知**。連結、畫面和更新文件會於發行日期在[發行說明](release-notes.md)中發佈。

## 發行版本 8.7.2 {#release-8-7-2}

_2024年7月30日_


>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-2}

* **新的SMS傳送聯結器** - SMS傳送聯結器已經過現代化及改善，可啟用收發器模式SMPP連線、啟用永久性SMPP連線，並確保轉換自Adobe Campaign Standard的環境有更好的相容性。 新的SMS外部帳戶現在可用於所有新的SMS實施。 仍支援現有的實施，但建議改用此新的現代化及擴充聯結器。

* **豐富推送通知(GA)** — 您現在可以傳送豐富推送通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 此版本中，豐富推送通知的一組範本現在可供您的iOS和Android應用程式使用。 [閱讀全文](../send/rich-push.md)。

* **品牌化** — 品牌化選項現在可供所有管道使用，包括SMS和直接郵件。 [閱讀全文](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-Hant){target="_blank"}


### 修正 {#fixes-8-7-2}

此版本已修正下列問題：

NEO-76592、NEO-75400、NEO-77406、NEO-77674、NEO-77899、NEO-73989、NEO-76064、NEO-76039、NEO-76040、NEO-76845、NEO-76664、NEO-76682、NEO-76663、NEO-73602、NEO-72915、NEO-78134、NEO-77000、NEO-77002、NEO-76955、NEO-76864、NEO-76926、NEO-76495 -77168， NEO-41058， NEO-75581， NEO-74647， NEO-74585 74586 74831 77319 78607。

## 發行版本 8.6.3 {#release-8-6-3}

_2024年7月30日_

### 新功能 {#new-8-6-3}

* **豐富推送通知** — 您現在可以傳送豐富推送通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 此版本中，豐富推送通知的一組範本現在可供您的iOS和Android應用程式使用。 [閱讀全文](../send/rich-push.md)。

* 自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](release-notes.md#change-8-7-1)

### 一般改善 {#improvements-8-6-3}

* 為了提高應用程式之間所有通訊的安全性，外部API呼叫現在支援mTLS。

### 修正 {#fixes-8-6-3}

此版本已修正下列問題：

NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->