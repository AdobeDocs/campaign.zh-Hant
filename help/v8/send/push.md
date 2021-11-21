---
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# 建立和傳送推播通知

行動應用程式傳送可讓您傳送通知至iOS和Android系統。

若要在Adobe Campaign中傳送推播通知，您必須：

1. 設定您的Campaign環境
1. 為行動應用程式建立行動應用程式類型的資訊服務。
1. 將應用程式的iOS和Android版本新增至此服務。
1. 建立iOS和Android的傳送。

![](../assets/do-not-localize/book.png) 了解如何開始使用 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}

## 與AdobeSDK整合

### 整合Campaign SDK

Campaign SDK可促進行動應用程式與Adobe Campaign平台的整合。

相容的SDK版本列於 [Campaign相容性矩陣](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) 了解如何在中，將Campaign Android和iOS SDK與您的應用程式整合 [本節](../config/push-config.md)

### 在Launch中設定Campaign擴充功能

您可以善用Campaign Classic擴充功能，將Adobe Experience Platform Launch SDK與Campaign整合。

![](../assets/do-not-localize/book.png) 深入了解 [Adobe行動SDK檔案](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target=&quot;_blank&quot;}

## 在Campaign中配置您的應用程式設定

您必須在Adobe Campaign中定義iOS和Android應用程式設定。

![](../assets/do-not-localize/book.png) iOS的設定准則於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) Anddroid的設定准則於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}

## 建立您的第一個推播通知

本節詳細說明傳送iOS和Android通知的特定元素。

>[!CAUTION]
>
>有了Campaign v8，行動註冊現在已可 **非同步**. [了解更多](../dev/staging.md)

若要建立新傳送，請瀏覽至 **[!UICONTROL Campaigns]** 按一下 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 如需如何建立傳送的全域資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### 在iOS上傳送通知 {#send-notifications-on-ios}

1. 選取 **[!UICONTROL Deliver on iOS]** 傳遞範本，按一下 **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，請選取與行動應用程式相關的服務，然後選取應用程式的iOS版本。

   ![](assets/push-ios-subscribers.png)

1. 選擇通知類型： **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** 或 **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. 在 **[!UICONTROL Title]** 欄位中，輸入要在通知上顯示的標題標籤。

1. 輸入 **[!UICONTROL Message]** 和 **[!UICONTROL Value of the badge]** 根據所選通知類型。

1. 您也可以定義下列元素：

   * 此 **[!UICONTROL Action button]** 可讓您為出現在警報通知上的動作按鈕定義標籤(**action_loc_key** 有效負載的欄位)。

   * 在 **[!UICONTROL Play a sound]** 欄位中，選取接收通知時由行動終端播放的音效。

   * 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以設定特定應用程式畫面，以在使用者啟動通知時顯示。

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤來預覽通知。

   ![](assets/push-ios-preview.png)


### 在Android上傳送通知 {#send-notifications-on-android}

1. 選取 **[!UICONTROL Deliver on Android (android)]** 傳遞範本。

   ![](assets/push-template-android.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an Android mobile application]**，選擇與行動應用程式相關的服務（在此例中為Neotrips），然後選取應用程式的Android版本。

   ![](assets/push-ios-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下 **[!UICONTROL Insert emoticon]** 圖示將表情符號插入推播通知。

1. 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以設定特定應用程式畫面，以在使用者啟動通知時顯示。

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤來預覽通知。

   <!--![](assets/push-android-preview.png)-->

## 測試、傳送及監視您的推播通知

若要傳送校樣並傳送最終傳送，請使用與電子郵件傳送相同的程式。 在 Campaign Classic v7 文件進一步瞭解：

* 驗證傳遞並傳送校樣
   ![](../assets/do-not-localize/book.png) [了解驗證傳送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

* 確認並傳送傳送
   ![](../assets/do-not-localize/book.png) [了解傳送傳遞的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}

傳送訊息後，您可以監控及追蹤您的傳送。 在 Campaign Classic v7 文件進一步瞭解：

* 推播通知隔離
   ![](../assets/do-not-localize/book.png) [深入了解推播通知隔離](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* 疑難排解
   ![](../assets/do-not-localize/book.png) [了解如何疑難排解推播通知](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;}
