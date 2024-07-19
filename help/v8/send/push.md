---
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 48aba38f3dc8bb322e6d0b38c1b743e980671cd7
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 6%

---

# 建立和傳送推播通知{#push-notifications-create}

行動應用程式傳送功能可讓您傳送通知至iOS和Android裝置。

開始使用Adobe Campaign傳送推播通知之前，您需要確保行動應用程式上和Adobe Experience Platform中的標籤已具備設定和整合。 [進一步瞭解推播設定。](push-settings.md)。

>[!CAUTION]
>
>Android Firebase Cloud Messaging (FCM)服務的一些重要變更將於2024年發行，可能會影響您的Adobe Campaign實施。 Android 推播訊息訂閱服務設定可能需要更新，才能支援此變更。您已經可以檢查並採取行動。 [了解更多](../../technotes/upgrades/push-technote.md)。


## 建立您的第一個推播通知 {#push-create}

本節詳細說明特定於iOS和Android通知傳送的元素。

>[!IMPORTANT]
>
>在[企業(FFDA)部署](../architecture/enterprise-deployment.md)的內容中，行動註冊現在是&#x200B;**非同步**。 [了解更多](../architecture/staging.md)


若要建立新傳遞，請瀏覽至&#x200B;**[!UICONTROL Campaigns]**&#x200B;標籤，按一下&#x200B;**[!UICONTROL Deliveries]**&#x200B;並按一下現有傳遞清單上方的&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

![](assets/delivery_step_1.png)


依預設，Adobe Campaign隨附兩個傳送範本：一個適用於iOS，一個適用於Android。 您可以複製它們以定義您自己的設定。 根據這些範本設定推播傳送的步驟詳述如下。

>[!BEGINTABS]

>[!TAB iOS]

若要在iOS裝置上傳送通知，請執行下列步驟：

1. 選取&#x200B;**[!UICONTROL Deliver on iOS]**&#x200B;傳遞範本。

   ![](assets/push_ios_1.png)

1. 若要定義通知的目標，請按一下&#x200B;**[!UICONTROL To]**&#x200B;連結，然後按一下&#x200B;**[!UICONTROL Add]**。

   ![](assets/push_ios_2.png)

1. 選取&#x200B;**[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，選取與您的行動應用程式相關的服務，然後選取應用程式的iOS版本。

   ![](assets/push_ios_3.png)

1. 在&#x200B;**[!UICONTROL General notification (Alert, Sound, Badge)]**&#x200B;或&#x200B;**[!UICONTROL Silent notification]**&#x200B;之間選擇您的&#x200B;**[!UICONTROL Notification type]**。

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >**無訊息推播**&#x200B;模式允許將「無訊息」通知傳送至行動應用程式。 使用者不會發現有通知傳到。而是直接傳輸到應用程式。

1. 在&#x200B;**[!UICONTROL Title]**&#x200B;欄位中，輸入您要顯示在通知中心可用通知清單中的標題標籤。

   此欄位可讓您定義iOS通知承載的&#x200B;**title**&#x200B;引數值。

1. 您可以新增iOS通知承載之&#x200B;**subtitle**&#x200B;引數的&#x200B;**[!UICONTROL Subtitle]**&#x200B;值。

1. 在精靈的&#x200B;**[!UICONTROL Message content]**&#x200B;區段中輸入訊息的內容。

1. 您可以從&#x200B;**[!UICONTROL Sound and Badge]**&#x200B;標籤編輯下列選項：

   * **[!UICONTROL Clean Badge]**：啟用此選項以重新整理徽章值。

   * **[!UICONTROL Value]**：設定將用來直接在應用程式圖示上顯示新未讀取資訊的數字。

   * **[!UICONTROL Critical alert mode]**：啟用此選項，即使使用者的電話設定為焦點模式或iPhone已靜音，也可以將聲音加入您的通知。

   * **[!UICONTROL Name]**：選取在收到通知時，由行動終端機播放的音效。

   * **[!UICONTROL Volume]**：聲音的音量從0到100。

     >[!NOTE]
     > 
     >聲音必須包含在應用程式中，並在建立服務時定義。
     >

   ![](assets/push_ios_5.png)

1. 從&#x200B;**[!UICONTROL Application variables]**&#x200B;索引標籤，會自動新增您的&#x200B;**[!UICONTROL Application variables]**。 它們可讓您定義通知行為，例如，您可以設定當使用者啟動通知時顯示的特定應用程式畫面。

1. 您可以從&#x200B;**[!UICONTROL Advanced]**&#x200B;標籤編輯下列一般選項：

   * **[!UICONTROL Mutable content]**：啟用此選項以允許行動應用程式下載媒體內容。

   * **[!UICONTROL Thread-id]**：用來將相關通知分組在一起的識別碼。

   * **[!UICONTROL Category]**：將顯示動作按鈕的類別ID名稱。 這些通知可讓使用者以更快的方式回應通知，執行不同的工作，而不需在應用程式中開啟或導覽。

   ![](assets/push_ios_6.png)

1. 對於時效性通知，您可以指定下列選項：

   * **[!UICONTROL Target content ID]**：識別碼，用於鎖定在開啟通知時要轉送的應用程式視窗。

   * **[!UICONTROL Launch image]**：要顯示的啟動影像檔名稱。 如果使用者選擇啟動您的應用程式，則會顯示選取的影像，而非您應用程式的啟動畫面。

   * **[!UICONTROL Interruption level]**：

      * **[!UICONTROL Active]**：依預設設定，系統會立即顯示通知、開啟熒幕，並可播放音效。 通知不會突破焦點模式。

      * **[!UICONTROL Passive]**：系統會將通知新增至通知清單，而不需開啟熒幕或播放音效。 通知不會突破焦點模式。

      * **[!UICONTROL Time sensitive]**&#x200B;系統會立即顯示通知、讓熒幕亮起、播放聲音並突破焦點模式。 此層級不需要Apple的特殊許可權。

      * **[!UICONTROL Critical]**&#x200B;系統會立即顯示通知、讓熒幕亮起，並略過靜音切換或焦點模式。 請注意，此層級需要Apple的特殊許可權。

   * **[!UICONTROL Relevance score]**：將關聯性分數設定為0到100。 系統會使用此選項來排序通知摘要中的通知。

   ![](assets/push_ios_7.png)

1. 設定通知後，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;標籤以預覽通知。

   ![](assets/push-ios-preview.png)


>[!TAB Android]

若要在Android裝置上傳送通知，請執行下列步驟：

1. 選取&#x200B;**[!UICONTROL Deliver on Android (android)]**&#x200B;傳遞範本。

   ![](assets/push-template-android.png)

   >[!NOTE]
   > 
   >您必須使用最新的FCM API (HTTP v1)更新Android推播通知的&#x200B;**傳遞範本**，以增加批次訊息的數量。 若要這麼做，請瀏覽至您的Android傳遞範本的屬性，並在&#x200B;**傳遞**&#x200B;索引標籤中，將[訊息批次數量](../../v8/send/configure-and-send.md#delivery-batch-quantity)設定為&#x200B;**256**。 將此變更套用至Android傳遞使用的所有傳遞範本，以及所有現有的Android傳遞。


1. 若要定義通知的目標，請按一下&#x200B;**[!UICONTROL To]**&#x200B;連結，然後按一下&#x200B;**[!UICONTROL Add]**。

   ![](assets/push-android-select-target.png)

1. 選取&#x200B;**[!UICONTROL Subscribers of an Android mobile application]**，選擇與您的行動應用程式相關的服務（在此案例中為Neotrips），然後選取應用程式的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然後輸入通知的內容。

   ![](assets/push-android-content.png)

1. 按一下&#x200B;**[!UICONTROL Insert emoticon]**&#x200B;圖示，將表情符號插入推播通知。

1. 在&#x200B;**[!UICONTROL Application variables]**&#x200B;欄位中，輸入每個變數的值。 例如，您可以設定當使用者啟動通知時要顯示的特定應用程式畫面。

1. 設定通知後，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;標籤以預覽通知。

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## 測試、傳送及監控推播通知 {#push-test}

若要傳送證明並傳送最終傳遞，請使用與其他傳遞相同的程式。

瞭解如何在[此頁面](preview-and-proof.md)中驗證傳遞。

瞭解如何在[此頁面](send.md)中確認並傳送傳遞

傳送訊息後，您可以監視和追蹤您的傳遞。 在[此頁面](delivery-failures.md#push-error-types)中進一步瞭解推播通知傳送失敗的原因。

