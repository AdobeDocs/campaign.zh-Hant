---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 93%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。**在發行日期之前，以下早期發行說明如有更改，恕不另行通知**。連結、畫面和更新文件會於發行日期在[發行說明](release-notes.md)中發佈。


## 發行版本 8.7.2 {#release-8-7-2}

_2024 年 9 月 3 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/docs/campaign-web/v8/start/acs-migration.html?lang=zh-Hant){target="_blank"}中進一步了解此轉換。

### 新功能 {#new-8-7-2}

* **新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充聯結器。

* **豐富推播通知 (GA)** - 您現在可以傳送豐富推播通知。豐富推播通知是行動裝置通知的增強型形式，其不僅限於簡單文字訊息，而是結合多媒體元素，例如影像、互動式按鈕或其他多媒體內容。 透過此版本，您現在可以在 iOS 和 Android 應用程式中使用一組豐富推播通知範本。[閱讀全文](../send/rich-push-android.md)。

* **品牌化** - 品牌化選項現在可供所有管道使用，包括 SMS 和直接郵件。[閱讀更多](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=zh-Hant){target="_blank"}


### 修正 {#fixes-8-7-2}

此版本已修正下列問題：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。
