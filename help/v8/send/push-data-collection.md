---
title: 使用Adobe Campaign傳送推播通知
description: 開始使用Campaign中的推播通知
feature: Push
role: Data Engineer
level: Intermediate
badge: label="有限可用性" type="Informative"
exl-id: 0f22b17c-ed01-4add-8300-8689b8a9f963
source-git-commit: 1fb93efac4fee4965213f8b42f518f2c10638e20
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 2%

---

# 已修訂推播通知設定 {#push-notifications-config}

Campaign v8.5推出我們最新的推播通知服務，並以現代尖端技術為基礎，提供強大的架構。 此服務旨在解鎖全新等級的擴充能力，確保您的通知能夠以順暢的效率觸及更廣泛的對象。 透過我們增強的基礎架構和最佳化程式，您可以期待更大規模且更可靠的服務，讓您以前所未有的方式與行動應用程式使用者互動和交流。

>[!AVAILABILITY]
>
> 從Campaign v8.5開始，新客戶可獨家存取此功能，並逐步向一組選定客戶推出。 如果您的環境是在2023年6月之前布建，此頁面不適用於您，您必須遵循此頁面](push-settings.md)中詳述的程式[。

關於此更新的實作，若要在Adobe Campaign中傳送推播通知，請遵循下列步驟：

1. [在Adobe Experience Platform資料彙集中建立應用程式表面](#create-app-surface)

1. [在Adobe Campaign中設定您的應用程式設定](#push-config-campaign)

1. [在Adobe Experience Platform Data Collection中建立及設定行動屬性](#create-mobile-property)

1. [新增Adobe Adobe Experience Platform Assurance擴充功能](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}（建議）

1. [將Campaign Classic新增至您的行動應用程式](#campaign-mobile-ap)

1. [建立iOS和Android的傳遞](##push-create)

>[!NOTE]
>
> 資料收集不支援舊版FCM和APNS p12。

## 在Adobe Experience Platform資料彙集中建立應用程式表面 {#create-app-surface}

您必須在[!DNL Adobe Experience Platform Data Collection]中新增行動應用程式推送認證。

行動應用程式推播認證註冊為必填，才能授權Adobe代表您傳送推播通知。 請參閱以下詳細步驟：

1. 從[!DNL Adobe Experience Platform Data Collection]中，選取左側面板中的&#x200B;**[!UICONTROL App Surfaces]**&#x200B;索引標籤。

1. 按一下&#x200B;**[!UICONTROL Create App Surface]**&#x200B;以建立新的組態。

   ![](assets/push-config-1.png)

1. 輸入組態的&#x200B;**[!UICONTROL Name]**。

1. 從&#x200B;**[!UICONTROL Mobile Application Configuration]**&#x200B;中，選取作業系統：

   * 適用於iOS **的**

     ![](assets/push-config-2.png)

      1. 在&#x200B;**[!UICONTROL App ID (iOS Bundle ID)]**&#x200B;欄位中輸入行動應用程式&#x200B;**套件組合識別碼**。

         您可以在Apple開發人員帳戶的&#x200B;**XCode**&#x200B;中主要目標的&#x200B;**一般**&#x200B;標籤中找到應用程式套件組合識別碼。

      1. 開啟&#x200B;**[!UICONTROL Push Credentials]**&#x200B;以新增您的認證。

      1. 拖放您的.p8 Apple推播通知驗證金鑰檔案。

         此金鑰可從Apple開發人員帳戶的&#x200B;**憑證**、**識別碼**&#x200B;和&#x200B;**設定檔**&#x200B;頁面取得。

      1. 提供&#x200B;**金鑰識別碼**。 這是在p8驗證金鑰建立期間指派的10字元字串。

         您可以在Apple開發人員帳戶的&#x200B;**憑證**、**識別碼**&#x200B;和&#x200B;**設定檔**&#x200B;頁面中的&#x200B;**金鑰**&#x200B;標籤下找到它。

      1. 提供&#x200B;**團隊識別碼**。 這是可在&#x200B;**成員資格**&#x200B;標籤下找到的字串值。

   * 適用於Android **的**

     ![](assets/push-config-3.png)

      1. 提供&#x200B;**[!UICONTROL App ID (Android package name)]**。 封裝名稱通常是您`build.gradle`檔案中的應用程式ID。

      1. 切換&#x200B;**[!UICONTROL Push Credentials]**&#x200B;以新增您的認證。

      1. 拖放FCM推送認證。 如需有關如何取得推送認證的詳細資訊，請參閱[Google檔案](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}。

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以建立您的應用程式設定。

## 在Adobe Campaign中設定您的應用程式設定{#push-config-campaign}

### 建立服務 {#create-service}

在傳送推播通知之前，您必須在Adobe Campaign中定義iOS和Android應用程式設定。

推播通知會透過專用服務傳送給您的應用程式使用者。 使用者安裝您的應用程式時，會訂閱此服務： Adobe Campaign仰賴此服務，僅鎖定您應用程式的訂閱者。 在此服務中，您需要新增iOS和Android應用程式，以在iOS和Android裝置上傳送。

若要建立服務以傳送推播通知，請遵循下列步驟：

1. 瀏覽至&#x200B;**[!UICONTROL Profiles and Targets > Services and Subscriptions]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/push-config-4.png){width="800" align="left"}

1. 輸入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**，然後選取&#x200B;**[!UICONTROL Mobile application]**&#x200B;型別。

   >[!NOTE]
   >
   >預設&#x200B;**[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]**&#x200B;目標對應已連結至收件者表格。 如果您想使用不同的目標對應，則需要建立新的目標對應，並在服務的&#x200B;**[!UICONTROL Target mapping]**&#x200B;欄位中輸入它。 在[此頁面](../audiences/target-mappings.md)中進一步瞭解目標對應。

1. 然後使用右側的&#x200B;**[!UICONTROL Add]**&#x200B;圖示來定義使用此服務的行動應用程式。

   ![](assets/push-config-5.png)

### 建立行動應用程式 {#create-sapp}

建立服務後，您現在需要定義將使用此服務的行動應用程式。

>[!BEGINTABS]

>[!TAB iOS]

若要為iOS裝置建立應用程式，請遵循下列步驟：

1. 從您的服務中，按一下&#x200B;**[!UICONTROL Add]**，然後選取&#x200B;**[!UICONTROL Create an iOS application]**。 按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/push-config-6.png)

1. 從&#x200B;**[!UICONTROL Launch app configurations list]**&#x200B;視窗中，選取先前在此區段中建立的應用程式表面。 按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/push-config-7.png)

1. （選擇性）您可以使用約&#x200B;**[!UICONTROL Application variables]**&#x200B;擴充推送訊息內容。 這些都是可完全自訂的專案，而且是傳送至行動裝置的訊息裝載的一部分。

   在下列範例中，已新增&#x200B;**mediaURl**&#x200B;和&#x200B;**mediaExt**&#x200B;變數來建立豐富推播通知，然後為應用程式提供要在通知內顯示的影像。

   ![](assets/push-config-8.png)

1. 瀏覽至&#x200B;**[!UICONTROL Subscription parameters]**&#x200B;標籤以定義具有&#x200B;**[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**&#x200B;結構描述副檔名的對應。

1. 瀏覽至&#x200B;**[!UICONTROL Sounds]**&#x200B;索引標籤以定義要播放的聲音。 按一下&#x200B;**[!UICONTROL Add]**&#x200B;並填入&#x200B;**[!UICONTROL Internal name]**&#x200B;欄位，欄位必須包含內嵌於應用程式中的檔案名稱或系統聲音名稱。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;開始設定開發應用程式。

1. **[!UICONTROL Integration key]**&#x200B;是每個應用程式專屬的。 此維度會將行動應用程式連結至Adobe Campaign，並將在設定Campaign擴充功能時使用。

   請確定透過SDK在Adobe Campaign和應用程式程式碼中定義了相同的&#x200B;**[!UICONTROL Integration key]**。

   在[開發人員檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}中進一步瞭解


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;可使用字串值完全自訂，但必須與SDK中指定的完全相同。
   >
   > 您不能對應用程式的開發版本（沙箱）和生產版本使用相同的憑證。

   ![](assets/push-config-9.png)

1. 從&#x200B;**[!UICONTROL Application icon]**&#x200B;欄位中選取圖示，以個人化您服務中的行動應用程式。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;開始設定生產應用程式，並依照上述步驟執行。 請注意，您無法將相同的&#x200B;**[!UICONTROL Integration key]**&#x200B;用於應用程式的開發版本（沙箱）和生產版本。

1. 按一下&#x200B;**[!UICONTROL Finish]**。

您的iOS應用程式現在已準備好在Campaign中使用。

>[!TAB Android]

若要為Android裝置建立應用程式，請遵循下列步驟：

1. 從您的服務中，按一下&#x200B;**[!UICONTROL Add]**，然後選取&#x200B;**[!UICONTROL Create an Android application]**。 按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/push-config-10.png)

1. 從&#x200B;**[!UICONTROL Launch app configurations list]**&#x200B;視窗中，選取在此區段中建立的應用程式表面，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/push-config-11.png)

1. 整合金鑰是每個應用程式專屬的。 此維度會將行動應用程式連結至Adobe Campaign，並將在設定Campaign擴充功能時使用。

   請確定透過SDK在Adobe Campaign和應用程式程式碼中定義了相同的&#x200B;**[!UICONTROL Integration key]**。

   在[開發人員檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}中進一步瞭解

   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;可使用字串值完全自訂，但必須與SDK中指定的完全相同。

   ![](assets/push-config-12.png)

1. 從&#x200B;**[!UICONTROL Application icon]**&#x200B;欄位中選取圖示，以個人化您服務中的行動應用程式。

1. （選擇性）如有需要，您可以使用約&#x200B;**[!UICONTROL Application variables]**&#x200B;擴充推送訊息內容。 這些都是可完全自訂的專案，而且是傳送至行動裝置的訊息裝載的一部分。

1. 瀏覽至&#x200B;**[!UICONTROL Subscription parameters]**&#x200B;標籤以定義具有&#x200B;**[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**&#x200B;結構描述副檔名的對應。

1. 按一下 **[!UICONTROL Finish]**，之後 **[!UICONTROL Save]**。

您的Android應用程式現在已準備好在Campaign中使用。

>[!ENDTABS]

以下是FCM裝載名稱，可進一步個人化您的推播通知：

| 訊息類型 | 可設定的訊息元素（FCM裝載名稱） | 可設定的選項（FCM裝載名稱） |
|:-:|:-:|:-:|
| 資料訊息 | N/A | validate_only |
| 通知訊息 | title，內文， android_channel_id，圖示，聲音，標籤，顏色，點按動作，影像，提示，粘性，可見度，通知優先順序，通知計數<br> | validate_only |

## 在Adobe Experience Platform資料彙集中設定行動屬性 {#create-mobile-property}

1. 從資料收集首頁，存取標籤功能表。

1. 按一下&#x200B;**[!UICONTROL New Property]**。

   ![](assets/push-config-13.png)

1. 輸入屬性的名稱，並選取&#x200B;**[!UICONTROL Mobile]**&#x200B;做為平台。

   ![](assets/push-config-14.png)

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以建立行動屬性。

1. 存取您新建立的行動屬性。

1. 從您的行動屬性儀表板，存取&#x200B;**[!UICONTROL Extensions]**&#x200B;功能表及&#x200B;**[!UICONTROL Catalog]**&#x200B;標籤。

   ![](assets/push-config-15.png)

1. 安裝&#x200B;**[!DNL Adobe Campaign Classic]**&#x200B;擴充功能。 [進一步瞭解Campaign擴充功能](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configure-campaign-classic-extension)

   ![](assets/push-config-16.png)

1. 填寫執行個體的詳細資訊：

   * 在Campaign的&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Advanced]** > **[!UICONTROL Deployment wizard]**&#x200B;功能表中可以找到&#x200B;**[!UICONTROL Registration endpoint]**&#x200B;或&#x200B;**[!UICONTROL Tracking endpoint]**&#x200B;個URL。
   * 在[此區段](#create-app)設定的行動應用程式中找到&#x200B;**[!UICONTROL Integration keys]**。

   ![](assets/push-config-17.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 您現在需要從&#x200B;**[!UICONTROL Publishing flow]**&#x200B;功能表發佈設定。 [了解更多](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

您的行動屬性現在將自動與&#x200B;**[!UICONTROL Adobe Experience Platform Data Collection]**&#x200B;技術工作流程同步。 [了解更多](../../automation/workflow/technical-workflows.md#list-technical-workflows)

## 將Campaign Classic新增至您的行動應用程式 {#campaign-mobile-app}

Adobe Experience Platform Mobile SDK 有助於在行動應用程式中，強化 Adobe Experience Cloud 解決方案與服務。 SDK的設定可透過資料收集UI進行管理，以進行靈活設定和可擴充的規則型整合。

[在Adobe Developer檔案中進一步瞭解](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}。

## 建立推播通知{#push-create}

在資料收集中成功設定行動應用程式後，您現在可以在Adobe Campaign中建立和傳送推播通知。

如需iOS和Android通知傳送的特定詳細元素，請參閱[此頁面](push.md#push-create)。
