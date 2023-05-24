---
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: e7c255d30e38c4e17779ef820e8984668ac5d48b
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# 建立和傳送推播通知{#push-notifications-create}

行動應用程式傳送可讓您傳送通知至iOS和Android裝置。

若要在Adobe Campaign中傳送推播通知，您需要：

1. 將SDK與應用程式整合。 [了解更多](#push-sdk)
1. 為您的行動應用程式建立行動應用程式型別的資訊服務，並將應用程式的iOS和Android版本新增到該服務。 [了解更多](#push-config)
1. 建立iOS和Android的傳遞。 [了解更多](#push-create)

## 整合SDK {#push-sdk}

若要使用Adobe Campaign傳送推播通知，您必須在Adobe Experience Platform Mobile SDK的資料收集UI中設定Adobe Campaign擴充功能。

Adobe Experience Platform Mobile SDK有助於在行動應用程式中強化Adobe的Experience Cloud解決方案和服務。 SDK的設定可透過資料收集UI進行管理，以彈性設定和可擴充的規則型整合。

[進一步瞭解Adobe Developer檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.


## 在Campaign中設定應用程式設定{#push-config}

在傳送推播通知之前，您必須在Adobe Campaign中定義iOS和Android應用程式設定。

推播通知會透過專用服務傳送給您的應用程式使用者。 使用者安裝您的應用程式時，會訂閱此服務： Adobe Campaign仰賴此服務，僅鎖定您應用程式的訂閱者。 在此服務中，您需要新增iOS和Android應用程式，才能在iOS和Android裝置上傳送。

若要建立服務以傳送推播通知，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Profiles and Targets > Services and Subscriptions]** 標籤，然後按一下 **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. 輸入 **[!UICONTROL Label]** 和 **[!UICONTROL Internal name]**，並選取 **[!UICONTROL Mobile application]** 型別。

   >[!NOTE]
   >
   >預設 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 目標對應會連結至收件者表格。 如果您想使用不同的目標對應，您需要建立新的目標對應，並在 **[!UICONTROL Target mapping]** 服務的欄位。 進一步瞭解中的目標對應 [此頁面](../audiences/target-mappings.md).

1. 然後使用 **[!UICONTROL Add]** 圖示來定義使用此服務的行動應用程式。

>[!BEGINTABS]

>[!TAB iOS]

若要為iOS裝置建立應用程式，請遵循下列步驟：

1. 選取 **[!UICONTROL Create an iOS application]** 並按一下 **[!UICONTROL Next]**。

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 在中輸入應用程式的名稱 **[!UICONTROL Label]** 欄位。
1. （選用）您可以使用一些專案豐富推送訊息內容 **[!UICONTROL Application variables]**. 這些都是可完全自訂的專案，而且是傳送至行動裝置的訊息裝載的一部分。

   在下列範例中， **mediaURl** 和 **mediaExt** 會新增變數來建立豐富推送通知，然後為應用程式提供要在通知內顯示的影像。

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 瀏覽至 **[!UICONTROL Subscription parameters]** 標籤來定義副檔名為的對應 **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 結構描述。

1. 瀏覽至 **[!UICONTROL Sounds]** 索引標籤來定義要播放的聲音。 按一下 **[!UICONTROL Add]** 和填滿 **[!UICONTROL Internal name]** 欄位，必須包含內嵌於應用程式中的檔案名稱或系統聲音名稱。

1. 按一下 **[!UICONTROL Next]** 以開始設定開發應用程式。

1. 整合金鑰是每個應用程式專屬的。 它會將行動應用程式連結至Adobe Campaign。

   請確定相同 **[!UICONTROL Integration key]** 是透過SDK在Adobe Campaign和應用程式程式碼中定義的。

   進一步瞭解 [開發人員檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 此 **[!UICONTROL Integration key]** 可完全自訂字串值，但必須與SDK中指定的值完全相同。
   >
   > 您不能對應用程式的開發版本（沙箱）和生產版本使用相同的憑證。

1. 選取圖示，從 **[!UICONTROL Application icon]** 欄位來個人化您服務中的行動應用程式。

1. 選取 **[!UICONTROL Authentication mode]**。提供兩種模式：

   * （建議） **[!UICONTROL Token-based authentication]**：填寫APN連線設定 **[!UICONTROL Key Id]**， **[!UICONTROL Team Id]** 和 **[!UICONTROL Bundle Id]** 然後按一下「 」，選取您的p8憑證 **[!UICONTROL Enter the private key...]**. 有關詳細資訊 **[!UICONTROL Token-based authentication]**，請參閱 [Apple檔案](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**：按一下 **[!UICONTROL Enter the certificate...]**  然後選取您的p12金鑰，並輸入行動應用程式開發人員提供的密碼。
   您稍後可以在中變更您的驗證模式 **[!UICONTROL Certificate]** 行動應用程式的索引標籤。

1. 使用 **[!UICONTROL Test the connection]** 按鈕來驗證您的設定。

1. 按一下 **[!UICONTROL Next]** 以開始設定生產應用程式，並依照上述步驟操作。

1. 按一下&#x200B;**[!UICONTROL Finish]**。

您的iOS應用程式現在已準備好在Campaign中使用。

>[!TAB Android]

若要為Android裝置建立應用程式，請執行下列步驟：

1. 選取 **[!UICONTROL Create an Android application]** 並按一下 **[!UICONTROL Next]**。

   ![](assets/new-android-app.png){width="600" align="left"}

1. 在中輸入應用程式的名稱 **[!UICONTROL Label]** 欄位。
1. 整合金鑰是每個應用程式專屬的。 它會將行動應用程式連結至Adobe Campaign。

   請確定相同 **[!UICONTROL Integration key]** 是透過SDK在Adobe Campaign和應用程式程式碼中定義的。

   進一步瞭解 [開發人員檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 此 **[!UICONTROL Integration key]** 可完全自訂字串值，但必須與SDK中指定的值完全相同。

1. 選取圖示，從 **[!UICONTROL Application icon]** 欄位來個人化您服務中的行動應用程式。
1. 選取 **HTTP v1** 在  **[!UICONTROL API version]** 下拉式清單。
1. 按一下 **[!UICONTROL Load project json file to extract project details...]** 連結以載入您的JSON金鑰檔案。 有關如何解壓縮JSON檔案的詳細資訊，請參閱 [Google Firebase檔案](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   您也可以手動輸入下列詳細資訊：
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 使用 **[!UICONTROL Test the connection]** 按鈕來驗證您的設定。

   >[!CAUTION]
   >
   >此 **[!UICONTROL Test connection]** 按鈕不會檢查MID伺服器是否可存取FCM伺服器。

1. （選用）您可以使用一些專案豐富推送訊息內容 **[!UICONTROL Application variables]** 視需要而定。 這些都是可完全自訂的專案，而且是傳送至行動裝置的訊息裝載的一部分。

1. 按一下 **[!UICONTROL Finish]**，之後 **[!UICONTROL Save]**。您的Android應用程式現在已準備好在Campaign中使用。

以下是FCM裝載名稱，可進一步個人化您的推播通知：

| 訊息類型 | 可設定的訊息元素（FCM裝載名稱） | 可設定的選項（FCM裝載名稱） |
|:-:|:-:|:-:|
| 資料訊息 | N/A | validate_only |
| 通知訊息 | title，內文， android_channel_id，圖示，聲音，標籤，顏色，點按動作，影像，提示，粘性，可見度， notification_priority， notification_count <br> | validate_only |


>[!ENDTABS]


## 建立您的第一個推播通知{#push-create}

本節詳細說明特定於iOS和Android通知傳送的元素。

>[!CAUTION]
>
>在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，行動註冊現在為 **非同步**. [了解更多](../architecture/staging.md)

若要建立新傳送，請瀏覽至 **[!UICONTROL Campaigns]** 標籤，按一下 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕來標籤現有傳遞清單。

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

若要在iOS裝置上傳送通知，請遵循下列步驟：

1. 選取 **[!UICONTROL Deliver on iOS]** 傳遞範本。

   ![](assets/push_ios_1.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 選取 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，選取與您的行動應用程式相關的服務，然後選取應用程式的iOS版本。

   ![](assets/push_ios_3.png)

1. 選擇您的 **[!UICONTROL Notification type]** 介於 **[!UICONTROL General notification (Alert, Sound, Badge)]** 或 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >此 **靜音推播** 模式允許將「無訊息」通知傳送至行動應用程式。 使用者未意識到通知的到達。 它會直接傳輸到應用程式。

1. 在 **[!UICONTROL Title]** 欄位，輸入您要在通知中心可用通知清單中顯示的標題標籤。

   此欄位可讓您定義 **標題** iOS通知裝載的引數。

1. 您可以新增 **[!UICONTROL Subtitle]**，的值 **子標題** iOS通知裝載的引數。

1. 在「 」中輸入訊息的內容 **[!UICONTROL Message content]** 區段。

1. 從 **[!UICONTROL Sound and Badge]** 標籤中，您可以編輯下列選項：

   * **[!UICONTROL Clean Badge]**：啟用此選項以重新整理徽章值。

   * **[!UICONTROL Value]**：設定將用於直接在應用程式圖示上顯示的新未讀取資訊數量。

   * **[!UICONTROL Critical alert mode]**：啟用此選項，即使使用者的手機設定為焦點模式或iPhone設為靜音，也可以將聲音新增到您的通知中。

   * **[!UICONTROL Name]**：選取在收到通知時由行動終端機播放的聲音。

   * **[!UICONTROL Volume]**：音量從0到100。

      >[!NOTE]
      > 
      >聲音必須包含在應用程式中，並在建立服務時定義。
   ![](assets/push_ios_5.png)

1. 從 **[!UICONTROL Application variables]** 標籤，您的 **[!UICONTROL Application variables]** 會自動新增。 它們可讓您定義通知行為，例如，您可以設定當使用者啟動通知時顯示的特定應用程式畫面。

1. 從 **[!UICONTROL Advanced]** 標籤中，您可以編輯下列一般選項：

   * **[!UICONTROL Mutable content]**：啟用此選項可允許行動應用程式下載媒體內容。

   * **[!UICONTROL Thread-id]**：用於將相關通知分組在一起的識別碼。

   * **[!UICONTROL Category]**：將顯示動作按鈕的類別ID名稱。 這些通知可讓使用者以更快的方式回應通知，執行不同的工作，而不需在應用程式中開啟或導覽。

   ![](assets/push_ios_6.png)

1. 對於時效性通知，您可以指定下列選項：

   * **[!UICONTROL Target content ID]**：用來在通知開啟時鎖定要轉送的應用程式視窗的識別碼。

   * **[!UICONTROL Launch image]**：要顯示的啟動影像檔名稱。 如果使用者選擇啟動您的應用程式，則會顯示選取的影像，而非您的應用程式啟動畫面。

   * **[!UICONTROL Interruption level]**：

      * **[!UICONTROL Active]**：根據預設，系統會立即顯示通知、在畫面上點亮，並可播放音效。 通知不會突破焦點模式。

      * **[!UICONTROL Passive]**：系統會將通知新增至通知清單，而不會點亮熒幕或播放音效。 通知不會突破焦點模式。

      * **[!UICONTROL Time sensitive]** 系統會立即顯示通知、讓熒幕亮起、播放聲音並突破焦點模式。 此層級不需要Apple的特殊許可權。

      * **[!UICONTROL Critical]** 系統會立即顯示通知、讓熒幕亮起，並略過靜音開關或聚焦模式。 請注意，此層級需要Apple的特殊許可權。
   * **[!UICONTROL Relevance score]**：將關聯性分數設定為0到100。 系統會使用此選項來排序通知摘要中的通知。

   ![](assets/push_ios_7.png)

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤以預覽通知。

   ![](assets/push-ios-preview.png)


>[!TAB Android]

若要在Android裝置上傳送通知，請執行下列步驟：

1. 選取 **[!UICONTROL Deliver on Android (android)]** 傳遞範本。

   ![](assets/push-template-android.png)

1. 若要定義通知的目標，請按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 選取 **[!UICONTROL Subscribers of an Android mobile application]**，選擇與您的行動應用程式相關的服務（在此案例中為Neotrips），然後選取應用程式的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下 **[!UICONTROL Insert emoticon]** 圖示來插入表情符號至推播通知。

1. 在 **[!UICONTROL Application variables]** 欄位中，輸入每個變數的值。 例如，您可以設定當使用者啟動通知時顯示的特定應用程式畫面。

1. 設定通知後，按一下 **[!UICONTROL Preview]** 標籤以預覽通知。

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## 測試、傳送及監控您的推播通知

若要傳送證明並傳送最終傳遞，請使用與其他傳遞相同的程式。

瞭解如何在中驗證傳遞 [此頁面](preview-and-proof.md).

瞭解如何確認並傳入傳遞 [此頁面](send.md)

傳送訊息後，您可以監視和追蹤您的傳遞。 若要深入瞭解推播通知傳送失敗的原因，請參閱 [此頁面](delivery-failures.md#push-error-types).

