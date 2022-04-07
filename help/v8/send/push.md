---
title: 向Adobe Campaign發送推送通知
description: 在市場活動中開始推送通知
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: a18141274b4934d45ecc82ce5d872c86e141a96f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# 建立和發送推送通知

移動應用程式交付，可以向iOS和Android系統發送通知。

要在Adobe Campaign發送推送通知，您需要：

1. 配置市場活動環境
1. 為您的移動應用程式建立Mobile應用程式類型資訊服務。
1. 將應用程式的iOS和Android版本添加到此服務。
1. 為iOS和Android建立交付。

![](../assets/do-not-localize/book.png) 瞭解如何在中開始使用移動應用 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;

## 整合市場活動SDK

市場活動SDK有助於將您的移動應用程式整合到Adobe Campaign平台。

相容SDK版本列於 [市場活動相容性清單](../start/compatibility-matrix.md#MobileSDK)。

![](../assets/do-not-localize/glass.png) 瞭解如何將營銷活動Android和iOSSDK與您的應用程式整合 [此部分](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## 在市場活動中配置你的應用設定

您必須在Adobe Campaign定義您的iOS和Android應用設定。

![](../assets/do-not-localize/book.png) 有關iOS的配置指南，請參見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;

![](../assets/do-not-localize/book.png) Anddroid的配置指南詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;

## 建立第一個推送通知

本節詳細介紹iOS和Android通知傳遞的特定元素。

>[!CAUTION]
>
>使用Campaign v8，移動註冊現在 **非同步**。 [了解更多](../dev/staging.md)

要建立新交貨，請瀏覽至 **[!UICONTROL Campaigns]** 按鈕 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 有關如何建立交貨的全局資訊，請參閱 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;

### 在iOS發送通知 {#send-notifications-on-ios}

1. 選擇 **[!UICONTROL Deliver on iOS]** 交貨模板，按一下 **[!UICONTROL Continue]**。

   ![](assets/push-template-ios.png)

1. 要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**。

   ![](assets/push-ios-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，選擇與您的移動應用程式相關的服務，然後選擇應用程式的iOS版本。

   ![](assets/push-ios-subscribers.png)

1. 選擇通知類型： **[!UICONTROL Alert]**。 **[!UICONTROL Badge]**。 **[!UICONTROL Alert and badge]** 或 **[!UICONTROL Silent Push]**。

   ![](assets/push-ios-alert.png)

1. 在 **[!UICONTROL Title]** 欄位中，輸入要在通知中顯示的標題的標籤。

1. 輸入 **[!UICONTROL Message]** 和 **[!UICONTROL Value of the badge]** 基於所選通知類型。

1. 您還可以定義以下元素：

   * 的 **[!UICONTROL Action button]** 允許您為出現在警報通知中的操作按鈕定義標籤(**操作_loc_key** 有效負載欄位)。

   * 在 **[!UICONTROL Play a sound]** 欄位中，選擇當收到通知時由移動終端播放的聲音。

   * 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以配置特定應用程式螢幕，以便在用戶激活通知時顯示。

1. 配置通知後，按一下 **[!UICONTROL Preview]** 的子菜單。

   ![](assets/push-ios-preview.png)


### 在Android上發送通知 {#send-notifications-on-android}

1. 選擇 **[!UICONTROL Deliver on Android (android)]** 交貨模板。

   ![](assets/push-template-android.png)

1. 要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**。

   ![](assets/push-android-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an Android mobile application]**，選擇與您的移動應用程式相關的服務（Neotrips，在本例中），然後選擇該應用程式的Android版本。

   ![](assets/push-ios-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下 **[!UICONTROL Insert emoticon]** 表徵圖，將圖釋插入推送通知。

1. 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以配置特定應用程式螢幕，以便在用戶激活通知時顯示。

1. 配置通知後，按一下 **[!UICONTROL Preview]** 的子菜單。

   <!--![](assets/push-android-preview.png)-->

## Test、發送和監視推送通知

要發送證據併發送最終交貨，請使用與電子郵件交貨相同的流程。 在 Campaign Classic v7 文件進一步瞭解：

* 驗證交貨併發送校樣
   ![](../assets/do-not-localize/book.png) [瞭解驗證交付的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;

* 確認併發送交貨
   ![](../assets/do-not-localize/book.png) [瞭解發送遞送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;

發送消息後，您可以監視和跟蹤交貨。 在 Campaign Classic v7 文件進一步瞭解：

* 推送通知隔離
   ![](../assets/do-not-localize/book.png) [瞭解有關推送通知隔離的詳細資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;

* 疑難排解
   ![](../assets/do-not-localize/book.png) [瞭解如何排除推式通知故障](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;
