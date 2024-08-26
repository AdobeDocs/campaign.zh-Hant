---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 0b4fc6da8761d2efe57d8eb0ff87cd11d0e2d250
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 90%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。**在發行日期之前，以下早期發行說明如有更改，恕不另行通知**。連結、畫面和更新文件會於發行日期在[發行說明](release-notes.md)中發佈。

<!--
## Release 8.7.2 {#release-8-7-2}

_July 30, 2024_


>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### New features {#new-8-7-2}

* **New SMS sending connector** - The SMS sending connector has been modernized and improved to enable transceiver mode SMPP connections, enable persistent SMPP connections, and ensure better compatibility for environments transitioning from Adobe Campaign Standard. A new SMS External account is now available for all new SMS implementations. Existing implementation are still supported, however recommendation is to move to this new modern and extended connector.

* **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 

* **Branding** - Branding options are now available for all channels, including SMS and Direct mail. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}


### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.
-->

## 發行版本 8.6.3 {#release-8-6-3}

_2024 年 7 月 30 日_

### 新功能 {#new-8-6-3}

* **豐富推播通知** - 您現在可以傳送豐富推播通知。 豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* 自此版本開始，Adobe 已棄用服務帳戶 (JWT) 認證，Campaign 與 Adobe 解決方案和應用程式的輸出整合現在需依賴 OAuth 伺服器對伺服器認證。 [了解更多](release-notes.md#change-8-7-1)

### 一般改善 {#improvements-8-6-3}

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

### 修正 {#fixes-8-6-3}

此版本已修正下列問題：

NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->