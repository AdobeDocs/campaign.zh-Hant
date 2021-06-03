---
product: Adobe Campaign
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# 建立和傳送推播通知

行動應用程式傳送可讓您傳送通知至iOS和Android系統。

若要在Adobe Campaign中傳送推播通知，您必須：

1. 設定您的Campaign環境
1. 為行動應用程式建立行動應用程式類型的資訊服務。
1. 將應用程式的iOS和Android版本新增至此服務。
1. 建立iOS和Android的傳送。

[!DNL :arrow_upper_right:] 在Campaign Classicv7檔案中了解如何開始使用 [行動應用程式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## 與AdobeSDK整合

### 整合Campaign SDK

Campaign SDK可促進行動應用程式與Adobe Campaign平台的整合。

[!DNL :arrow_upper_right:] 在Campaign Classicv7檔案中了解如何將Campaign SDK與您的應 [用程式整合](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### 在Launch中設定Campaign擴充功能

您可以善用Campaign Classic擴充功能，將Adobe Experience Platform Launch SDK與Campaign整合。

[!DNL :arrow_upper_right:] 進一步了 [解AdobeMobile SDK檔案](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## 在Campaign中配置您的應用程式設定

您必須在Adobe Campaign中定義iOS和Android應用程式設定。

[!DNL :arrow_upper_right:] iOS的設定准則在 [Campaign Classicv7檔案中詳細說明](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Campaign Classicv7檔案中會詳細說明 [Anddroid的設定准則](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## 建立您的第一個推播通知

[!DNL :arrow_upper_right:] 在Campaign Classicv7檔案中了解如何建立第 [一個推播通知](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>若使用Campaign v8行動註冊現在為&#x200B;**非同步**。 [瞭解更多](../dev/staging.md)
