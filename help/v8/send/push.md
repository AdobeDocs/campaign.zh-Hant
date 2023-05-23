---
title: 向Adobe Campaign發送推送通知
description: 在市場活動中開始推送通知
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: e7c255d30e38c4e17779ef820e8984668ac5d48b
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# 建立和發送推送通知{#push-notifications-create}

移動應用程式交付功能，讓您向iOS和Android設備發送通知。

要在Adobe Campaign發送推送通知，您需要：

1. 將SDK與應用整合。 [了解更多](#push-sdk)
1. 為您的移動應用程式建立移動應用程式類型資訊服務，並將應用程式的iOS和Android版本添加到該服務。 [了解更多](#push-config)
1. 為iOS和Android建立交付。 [了解更多](#push-create)

## 整合SDK {#push-sdk}

要向Adobe Campaign發送推送通知，必須在Adobe Experience Platform移動SDK的資料收集UI中配置Adobe Campaign擴展。

Adobe Experience Platform移動軟體開發工具包幫助您的移動應用中提供Adobe的Experience Cloud解決方案和服務。 SDK配置通過資料收集UI進行管理，以實現靈活的配置和可擴展的、基於規則的整合。

[在Adobe Developer文檔中瞭解更多資訊](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}。


## 在市場活動中配置你的應用設定{#push-config}

在發送推送通知之前，必須在Adobe Campaign定義您的iOS和Android應用設定。

推送通知通過專用服務發送給您的應用用戶。 當用戶安裝你的應用時，他們訂閱此服務：Adobe Campaign只依賴此服務來瞄準你的應用的訂閱者。 在此服務中，您需要添加您的iOS和Android應用，以在iOS和Android設備上發送。

要建立發送推送通知的服務，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Profiles and Targets > Services and Subscriptions]** ，然後按一下 **[!UICONTROL Create]**。

   ![](assets/new-service-push.png){width="800" align="left"}

1. 輸入 **[!UICONTROL Label]** 和 **[!UICONTROL Internal name]**，然後選擇 **[!UICONTROL Mobile application]** 的雙曲餘切值。

   >[!NOTE]
   >
   >預設 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 目標映射連結到收件人表。 如果要使用其他目標映射，則需要建立新的目標映射，並在 **[!UICONTROL Target mapping]** 服務欄位。 瞭解有關中目標映射的詳細資訊 [此頁](../audiences/target-mappings.md)。

1. 然後使用 **[!UICONTROL Add]** 表徵圖，定義使用此服務的移動應用程式。

>[!BEGINTABS]

>[!TAB iOS]

要為iOS設備建立應用，請執行以下步驟：

1. 選取 **[!UICONTROL Create an iOS application]** 並按一下 **[!UICONTROL Next]**。

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 在 **[!UICONTROL Label]** 的子菜單。
1. （可選）您可以通過一些 **[!UICONTROL Application variables]**。 這些是完全可定製的，並且是發送到移動設備的消息負載的一部分。

   在下面的示例中， **媒體URl** 和 **媒體擴展** 添加變數以建立富推送通知，然後向應用程式提供要在通知中顯示的影像。

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 瀏覽到 **[!UICONTROL Subscription parameters]** 的子菜單。 **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 架構。

1. 瀏覽到 **[!UICONTROL Sounds]** 的子菜單。 按一下 **[!UICONTROL Add]** 填充 **[!UICONTROL Internal name]** 欄位，該欄位必須包含應用程式中嵌入的檔案名稱或系統聲音的名稱。

1. 按一下 **[!UICONTROL Next]** 開始配置開發應用程式。

1. 整合密鑰特定於每個應用程式。 它把移動應用程式與Adobe Campaign連接起來。

   確保這樣 **[!UICONTROL Integration key]** 在Adobe Campaign和應用程式碼中通過SDK定義。

   瞭解詳情 [開發人員文檔](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 的 **[!UICONTROL Integration key]** 完全可自定義，但需要與SDK中指定的值完全相同。
   >
   > 您不能對應用程式的開發版本（沙盒）和生產版本使用相同的證書。

1. 從 **[!UICONTROL Application icon]** 欄位來個性化服務中的移動應用程式。

1. 選取 **[!UICONTROL Authentication mode]**。有兩種模式可用：

   * （推薦） **[!UICONTROL Token-based authentication]**:填寫APN連接設定 **[!UICONTROL Key Id]**。 **[!UICONTROL Team Id]** 和 **[!UICONTROL Bundle Id]** 然後按一下 **[!UICONTROL Enter the private key...]**。 更多內容 **[!UICONTROL Token-based authentication]**，請參閱 [Apple文檔](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}。

   * **[!UICONTROL Certificate-based authentication]**:按一下 **[!UICONTROL Enter the certificate...]**  然後選擇p12密鑰並輸入移動應用程式開發人員提供的密碼。
   以後，您可以在 **[!UICONTROL Certificate]** 頁籤。

1. 使用 **[!UICONTROL Test the connection]** 按鈕以驗證配置。

1. 按一下 **[!UICONTROL Next]** 開始配置生產應用程式，並執行與上面詳述的步驟相同。

1. 按一下&#x200B;**[!UICONTROL Finish]**。

您的iOS應用程式現已準備好用於市場活動。

>[!TAB Android]

要為Android設備建立應用，請執行以下步驟：

1. 選取 **[!UICONTROL Create an Android application]** 並按一下 **[!UICONTROL Next]**。

   ![](assets/new-android-app.png){width="600" align="left"}

1. 在 **[!UICONTROL Label]** 的子菜單。
1. 整合密鑰特定於每個應用程式。 它把移動應用程式與Adobe Campaign連接起來。

   確保這樣 **[!UICONTROL Integration key]** 在Adobe Campaign和應用程式碼中通過SDK定義。

   瞭解詳情 [開發人員文檔](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 的 **[!UICONTROL Integration key]** 完全可自定義，但需要與SDK中指定的值完全相同。

1. 從 **[!UICONTROL Application icon]** 欄位來個性化服務中的移動應用程式。
1. 選擇 **HTTP v1** 在  **[!UICONTROL API version]** 的子菜單。
1. 按一下 **[!UICONTROL Load project json file to extract project details...]** 連結以載入JSON密鑰檔案。 有關如何提取JSON檔案的詳細資訊，請參閱 [Google火庫文檔](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}。

   您還可以人工輸入以下詳細資訊：
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 使用 **[!UICONTROL Test the connection]** 按鈕以驗證配置。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Test connection]** 按鈕不檢查MID伺服器是否具有訪問FCM伺服器的權限。

1. （可選）您可以通過一些 **[!UICONTROL Application variables]** 如果需要。 這些是完全可定製的，並且是發送到移動設備的消息負載的一部分。

1. 按一下 **[!UICONTROL Finish]**，之後 **[!UICONTROL Save]**。您的Android應用程式現在已準備好在市場活動中使用。

以下是FCM負載名稱，以進一步個性化推送通知：

| 訊息類型 | 可配置消息元素（FCM負載名稱） | 可配置選項（FCM負載名稱） |
|:-:|:-:|:-:|
| 資料消息 | N/A | validate_only |
| 通知消息 | title, body, android_channelid，表徵圖， sound，標籤，color, click_action，影像，ticker,sticky，可見性，notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## 建立第一個推送通知{#push-create}

本節詳細介紹iOS和Android通知傳遞的特定元素。

>[!CAUTION]
>
>在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，移動註冊現在 **非同步**。 [了解更多](../architecture/staging.md)

要建立新交貨，請瀏覽至 **[!UICONTROL Campaigns]** 按鈕 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

要在iOS設備上發送通知，請執行以下步驟：

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
   ![](assets/push_ios_5.png)

1. 從 **[!UICONTROL Application variables]** 頁籤 **[!UICONTROL Application variables]** 的子菜單。 它們允許您定義通知行為，例如，您可以配置特定應用程式螢幕以在用戶激活通知時顯示。

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


>[!TAB Android]

要在Android設備上發送通知，請執行以下步驟：

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

>[!ENDTABS]


## Test、發送和監視推送通知

要發送證明併發送最終交貨，請使用與其他交貨相同的流程。

瞭解如何驗證交付 [此頁](preview-and-proof.md)。

瞭解如何確認和發送交貨 [此頁](send.md)

發送消息後，您可以監視和跟蹤交貨。 瞭解有關推送通知傳遞失敗原因的詳細資訊，請參閱 [此頁](delivery-failures.md#push-error-types)。

