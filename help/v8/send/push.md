---
solution: Campaign Classic
product: campaign
title: 傳送推播通知給Adobe Campaign
description: 開始使用Campaign中的推播通知
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 32f73f8ecf2ce66fa6e58adb5bce7320fc65f94c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 建立和傳送推播通知

行動應用程式傳送可讓您傳送通知至iOS和Android系統。

若要在Adobe Campaign傳送推播通知，您必須：

1. 設定您的促銷活動環境
1. 為您的行動應用程式建立行動應用程式類型的資訊服務。
1. 將應用程式的iOS和Android版本新增至此服務。
1. 建立iOS和Android的傳送。

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)中瞭解如何開始使用行動應用程式

## 與AdobeSDK整合

### 整合Campaign SDK

Campaign SDK可協助您將行動應用程式整合至Adobe Campaign平台。

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)中瞭解如何將Campaign SDK與您的應用程式整合

### 在啟動中設定促銷活動擴充功能

您可以運用Campaign Classic擴充功能，將Adobe Experience Platform Launch SDK與Campaign整合。

:arrow_upper_right:進一步瞭解[Adobe行動SDK檔案](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## 在Campaign中設定您的應用程式設定

您必須在Adobe Campaign定義您的iOS和Android應用程式設定。

:arrow_upper_right:iOS的配置指南詳見[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

:arrow_upper_right:[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)中詳細說明了Anddroid的配置指南

## 建立您的第一個推播通知

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)中建立您的第一個推播通知
