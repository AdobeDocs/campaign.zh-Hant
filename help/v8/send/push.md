---
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 6%

---

# 建立和傳送推播通知{#push-notifications-create}

行動應用程式傳送可讓您傳送通知至iOS和Android系統。

若要在Adobe Campaign中傳送推播通知，您必須：

1. 設定您的Campaign環境
1. 為行動應用程式建立行動應用程式類型的資訊服務。
1. 將應用程式的iOS和Android版本新增至此服務。
1. 建立iOS和Android的傳送。

![](../assets/do-not-localize/book.png) 了解如何開始使用 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target="_blank"}

## 整合SDK {#push-sdk}

您可以在資料收集UI中設定Adobe Experience Platform擴充功能，以使用Adobe Campaign Mobile SDK。 Adobe Experience Platform Mobile SDK可協助您在行動應用程式中支援Adobe的Experience Cloud解決方案和服務。 SDK設定可透過資料收集UI管理，以進行彈性的設定和可擴充的規則型整合。 [進一步了解Adobe Developer檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

了解如何配置和安裝Adobe Experience Platform Mobile SDK [在此視頻中](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/sending-messages/push-channel/configure-push-using-aep-mobile-sdk.html?lang=en){target="_blank"}.

您也可以整合Campaign SDK，以促進行動應用程式與Adobe Campaign平台的整合。 相容的SDK版本列於 [Campaign相容性矩陣](../start/compatibility-matrix.md#MobileSDK).

了解如何在中，將Campaign Android和iOS SDK與您的應用程式整合 [本頁](../config/push-config.md)

## 在Campaign中配置您的應用程式設定{#push-config}

您必須在Adobe Campaign中定義iOS和Android應用程式設定。

![](../assets/do-not-localize/book.png) iOS的設定准則於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target="_blank"}

![](../assets/do-not-localize/book.png) Anddroid的設定准則於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target="_blank"}

## 建立您的第一個推播通知{#push-create}

本節詳細說明傳送iOS和Android通知的特定元素。

>[!CAUTION]
>
>在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，行動註冊現在 **非同步**. [了解更多](../architecture/staging.md)

若要建立新傳送，請瀏覽至 **[!UICONTROL Campaigns]** 按一下 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 如需如何建立傳送的全域資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target="_blank"}

### 在iOS上傳送通知 {#send-notifications-on-ios}

>[!NOTE]
>
>此功能可從 Campaign v8.3 開始使用。若要檢查您的版本，請參閱[此章節](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. 選取 **[!UICONTROL Deliver on iOS]** 傳遞範本。

   ![](assets/push_ios_1.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 選擇 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，請選取與行動應用程式相關的服務，然後選取應用程式的iOS版本。

   ![](assets/push_ios_3.png)

1. 選擇您的 **[!UICONTROL Notification type]** 介於 **[!UICONTROL General notification (Alert, Sound, Badge)]** 或 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >此 **靜默推** 模式可將「靜默」通知傳送至行動應用程式。 使用者未得知通知的到達。 會直接轉送至應用程式。

1. 在 **[!UICONTROL Title]** 欄位中，輸入要在通知中心可用通知清單中顯示的標題標籤。

   此欄位可讓您定義 **標題** iOS通知裝載的參數。

1. 您可以新增 **[!UICONTROL Subtitle]**，值 **字幕** iOS通知裝載的參數。

1. 在 **[!UICONTROL Message content]** 的子句。

1. 從 **[!UICONTROL Sound and Badge]** 頁簽，您可以編輯下列選項：

   * **[!UICONTROL Clean Badge]**:啟用此選項可刷新徽章值。

   * **[!UICONTROL Value]**:設定一個數字，該數字將用於直接在應用程式表徵圖上顯示新未讀資訊的數量。

   * **[!UICONTROL Critical alert mode]**:啟用此選項，即使使用者的手機設定為焦點模式或iPhone已靜音，仍可將音效新增至通知。

   * **[!UICONTROL Name]**:在收到通知時，選擇要由移動終端播放的聲音。

   * **[!UICONTROL Volume]**:音量從0到100。

      >[!NOTE]
      > 
      >應用程式中必須包含聲音，並在建立服務時定義聲音。
      >
      >iOS的設定准則於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target="_blank"}.
   ![](assets/push_ios_5.png)

1. 從 **[!UICONTROL Application variables]** 標籤 **[!UICONTROL Application variables]** 會自動新增。 它們可讓您定義通知行為，例如，您可以設定當使用者啟動通知時顯示的特定應用程式畫面。

   如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target="_blank"}.

1. 從 **[!UICONTROL Advanced]** 頁簽中，可以編輯以下常規選項：

   * **[!UICONTROL Mutable content]**:啟用此選項可允許行動應用程式下載媒體內容。

   * **[!UICONTROL Thread-id]**:用於將相關通知分組的標識符。

   * **[!UICONTROL Category]**:將顯示動作按鈕的類別ID名稱。 這些通知可讓使用者以更快的方式回應通知，執行不同的工作，而不需在應用程式中開啟或導覽。

   ![](assets/push_ios_6.png)

1. 對於時間敏感通知，您可以指定下列選項：

   * **[!UICONTROL Target content ID]**:用於定位在開啟通知時要前進的應用程式視窗的識別碼。

   * **[!UICONTROL Launch image]**:要顯示的launch影像檔案名稱。 如果使用者選擇啟動您的應用程式，則會顯示選取的影像，而非您應用程式的啟動畫面。

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**:預設設定後，系統會立即顯示通知、點亮螢幕並播放聲音。 通知不會中斷焦點模式。

      * **[!UICONTROL Passive]**:系統將通知添加到通知清單中，而不用點亮螢幕或播放聲音。 通知不會中斷焦點模式。

      * **[!UICONTROL Time sensitive]** 系統會立即顯示通知，將螢幕燈亮起，可以播放聲音並突破焦點模式。 此層級不需要Apple的特殊許可。

      * **[!UICONTROL Critical]** 系統會立即顯示通知、點亮螢幕，並繞過靜音開關或聚焦模式。 請注意，此層級需要Apple的特殊權限。
   * **[!UICONTROL Relevance score]**:將關聯分數從0設定為100。 系統會使用此功能來排序通知摘要中的通知。

   ![](assets/push_ios_7.png)

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤來預覽通知。

   ![](assets/push-ios-preview.png)

### 在Android上傳送通知 {#send-notifications-on-android}

1. 選取 **[!UICONTROL Deliver on Android (android)]** 傳遞範本。

   ![](assets/push-template-android.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 選擇 **[!UICONTROL Subscribers of an Android mobile application]**，選擇與行動應用程式相關的服務（在此例中為Neotrips），然後選取應用程式的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下 **[!UICONTROL Insert emoticon]** 圖示將表情符號插入推播通知。

1. 在 **[!UICONTROL Application variables]** 欄位，輸入每個變數的值。 例如，您可以設定特定應用程式畫面，以在使用者啟動通知時顯示。

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤來預覽通知。

   <!--![](assets/push-android-preview.png)-->

## 測試、傳送及監視您的推播通知

若要傳送校樣並傳送最終傳送，請使用與電子郵件傳送相同的程式。 在 Campaign Classic v7 文件進一步瞭解：

* 驗證傳遞並傳送校樣
   ![](../assets/do-not-localize/book.png) [了解驗證傳送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target="_blank"}

* 確認並傳送傳送
   ![](../assets/do-not-localize/book.png) [了解傳送傳遞的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html){target="_blank"}

傳送訊息後，您可以監控及追蹤您的傳送。 在 Campaign Classic v7 文件進一步瞭解：

* 推播通知隔離
   ![](../assets/do-not-localize/book.png) [深入了解推播通知隔離](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html#push-notification-quarantines){target="_blank"}

* 疑難排解
   ![](../assets/do-not-localize/book.png) [了解如何疑難排解推播通知](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html){target="_blank"}
