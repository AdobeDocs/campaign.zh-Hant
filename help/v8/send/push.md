---
title: 向Adobe Campaign發送推送通知
description: 在市場活動中開始推送通知
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 6%

---

# 建立和發送推送通知

移動應用程式交付，可以向iOS和Android系統發送通知。

要在Adobe Campaign發送推送通知，您需要：

1. 配置市場活動環境
1. 為移動應用程式建立移動應用程式類型資訊服務。
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
>在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，移動註冊現在 **非同步**。 [了解更多](../architecture/staging.md)

要建立新交貨，請瀏覽至 **[!UICONTROL Campaigns]** 按鈕 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 有關如何建立交貨的全局資訊，請參閱 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;

### 在iOS發送通知 {#send-notifications-on-ios}

>[!NOTE]
>
>此功能可從 Campaign v8.3 開始使用。若要檢查您的版本，請參閱[此章節](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. 選擇 **[!UICONTROL Deliver on iOS]** 交貨模板。

   ![](assets/push_ios_1.png)

1. 要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**。

   ![](assets/push_ios_2.png)

1. 選擇 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，選擇與您的移動應用程式相關的服務，然後選擇應用程式的iOS版本。

   ![](assets/push_ios_3.png)

1. 選擇 **[!UICONTROL Notification type]** 間 **[!UICONTROL General notification (Alert, Sound, Badge)]** 或 **[!UICONTROL Silent notification]**。

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >的 **靜默推送** 模式允許將「靜默」通知發送到移動應用程式。 用戶未意識到通知的到達。 直接轉給申請。

1. 在 **[!UICONTROL Title]** 欄位，輸入要顯示在通知中心可用通知清單中的標題標籤。

   此欄位允許您定義 **標題** iOS通知負載的參數。

1. 可以添加 **[!UICONTROL Subtitle]**, **字幕** iOS通知負載的參數。

1. 在 **[!UICONTROL Message content]** 的子菜單。

1. 從 **[!UICONTROL Sound and Badge]** 頁籤中，可以編輯以下選項：

   * **[!UICONTROL Clean Badge]**:啟用此選項以刷新標籤值。

   * **[!UICONTROL Value]**:設定一個數字，該數字將用於直接在應用程式表徵圖上顯示新未讀資訊的數量。

   * **[!UICONTROL Critical alert mode]**:啟用此選項可在用戶的電話設定為焦點模式或iPhone靜音時，將聲音添加到通知中。

   * **[!UICONTROL Name]**:選擇當收到通知時由移動終端播放的聲音。

   * **[!UICONTROL Volume]**:聲音從0到100。

      >[!NOTE]
      > 
      >聲音必須包括在應用程式中並在建立服務時定義。
      >
      >有關iOS的配置指南，請參見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target=&quot;_blank&quot;}。
   ![](assets/push_ios_5.png)

1. 從 **[!UICONTROL Application variables]** 頁籤 **[!UICONTROL Application variables]** 的子菜單。 它們允許您定義通知行為，例如，您可以配置特定應用程式螢幕以在用戶激活通知時顯示。

   如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target=&quot;_blank&quot;}。

1. 從 **[!UICONTROL Advanced]** 頁籤中，可以編輯以下常規選項：

   * **[!UICONTROL Mutable content]**:啟用此選項可允許移動應用程式下載媒體內容。

   * **[!UICONTROL Thread-id]**:用於將相關通知分組在一起的標識符。

   * **[!UICONTROL Category]**:將顯示操作按鈕的類別ID的名稱。 這些通知可讓使用者以更快的方式回應通知，執行不同的工作，而不需在應用程式中開啟或導覽。

   ![](assets/push_ios_6.png)

1. 對於時間敏感通知，可以指定以下選項：

   * **[!UICONTROL Target content ID]**:用於在開啟通知時要轉發的應用程式窗口的目標標識符。

   * **[!UICONTROL Launch image]**:要顯示的啟動映像檔案的名稱。 如果用戶選擇啟動您的應用程式，則將顯示所選影像，而不是應用程式的啟動螢幕。

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**:預設情況下，系統會立即顯示通知，開啟螢幕並播放聲音。 通知不會突破焦點模式。

      * **[!UICONTROL Passive]**:系統將通知添加到通知清單，而不點亮螢幕或播放聲音。 通知不會突破焦點模式。

      * **[!UICONTROL Time sensitive]** 系統會立即發出通知，點亮螢幕，播放聲音並突破焦點模式。 這一級別不需要Apple的特別許可。

      * **[!UICONTROL Critical]** 系統會立即顯示通知，點亮螢幕，並繞過靜音開關或聚焦模式。 請注意，此級別需要獲得Apple的特別許可。
   * **[!UICONTROL Relevance score]**:將相關性分數設定為0到100。 系統使用此選項對通知摘要中的通知進行排序。

   ![](assets/push_ios_7.png)

1. 配置通知後，按一下 **[!UICONTROL Preview]** 的子菜單。

   ![](assets/push-ios-preview.png)

### 在Android上發送通知 {#send-notifications-on-android}

1. 選擇 **[!UICONTROL Deliver on Android (android)]** 交貨模板。

   ![](assets/push-template-android.png)

1. 要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**。

   ![](assets/push-android-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an Android mobile application]**，選擇與您的移動應用程式相關的服務（Neotrips，在本例中），然後選擇該應用程式的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下 **[!UICONTROL Insert emoticon]** 表徵圖，將圖釋插入推送通知。

1. 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以配置特定應用程式螢幕，以便在用戶激活通知時顯示。

1. 配置通知後，按一下 **[!UICONTROL Preview]** 的子菜單。

   <!--![](assets/push-android-preview.png)-->

## Test、發送和監視推送通知

要發送證據併發送最終交貨，請使用與電子郵件交貨相同的流程。 在 Campaign Classic v7 文件進一步瞭解：

* 驗證交貨併發送校樣
   ![](../assets/do-not-localize/book.png) [瞭解驗證交付的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target=&quot;_blank&quot;

* 確認併發送交貨
   ![](../assets/do-not-localize/book.png) [瞭解發送遞送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html){target=&quot;_blank&quot;

發送消息後，您可以監視和跟蹤交貨。 在 Campaign Classic v7 文件進一步瞭解：

* 推送通知隔離
   ![](../assets/do-not-localize/book.png) [瞭解有關推送通知隔離的詳細資訊](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html#push-notification-quarantines){target=&quot;_blank&quot;

* 疑難排解
   ![](../assets/do-not-localize/book.png) [瞭解如何排除推式通知故障](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html){target=&quot;_blank&quot;
