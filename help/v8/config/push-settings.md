---
title: 整合AEP SDK和Campaign
description: 瞭解如何將Adobe Experience Platform Mobile SDK與您的應用程式整合
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 2%

---


# AEP SDK + Campaign：設定推播通知頻道 {#push-notification-configuration}

開始使用Adobe Campaign傳送推播通知之前，您需要確保行動應用程式上和Adobe Experience Platform中的標籤的設定和整合已就緒。

Adobe Experience Platform Mobile SDK透過與Android和iOS相容的SDK，為您的行動裝置提供使用者端整合API。

若要使用Adobe Experience Platform Mobile SDK設定您的應用程式，請遵循下列步驟：

1. Check [必備條件](#before-starting).
1. 設定 [行動標籤屬性](#launch-property) (在Adobe Experience Platform資料彙集中)。
1. 取得詳細的Adobe Experience Platform Mobile SDK [在此頁面中](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. （選用）啟用記錄與生命週期量度（如詳細） [在此頁面中](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. （選用）新增 [應用程式的Adobe Experience Platform保證](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. 追隨 [Adobe Experience Platform Mobile SDK檔案](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} 以於應用程式中設定Adobe Experience Platform Mobile SDK。
1. 安裝及設定 [Adobe Campaign擴充功能](#configure-extension) 在您的行動屬性中。
1. 在Adobe Campaign中設定iOS和Android行動服務的詳細資訊 [在此頁面中](../send/push.md#push-config).


## 必要條件 {#before-starting}

### 設定許可權 {#setup-permissions}

在建立行動應用程式之前，您必須先確定您擁有或指派正確的Adobe Experience Platform標籤使用者許可權。 Adobe Experience Platform中標籤的使用者許可權會透過Adobe Admin Console指派給使用者。 進一步瞭解 [標籤檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>推播設定必須由專家使用者執行。 根據您的實作模型和此實作中涉及的角色，您可能需要將完整許可權集指派給單一產品設定檔，或在應用程式開發人員和 **Adobe Campaign** 管理員。

要指派 **屬性** 和 **公司** 許可權，請遵循下列步驟：

1. 存取 **[!DNL Admin Console]**.
1. 從 **[!UICONTROL Products]** 索引標籤中，選取 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡片。
1. 選取現有 **[!UICONTROL Product Profile]** 或建立新的，使用 **[!UICONTROL New profile]** 按鈕。 瞭解如何建立新的 **[!UICONTROL New profile]** 在 [Admin Console檔案](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. 在&#x200B;**[!UICONTROL Permissions]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Property Rights]**。
1. 按一下 **[!UICONTROL Add all]**。這會將以下許可權新增至您的產品設定檔：
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   安裝及發佈Adobe Campaign擴充功能，以及在中發佈應用程式屬性時，需要這些許可權 **Adobe Experience Platform Mobile SDK**.

1. 然後，選取 **[!UICONTROL Company rights]** 在左側功能表中。
1. 新增下列許可權：

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   行動應用程式開發人員需要這些許可權，才能在中設定推送認證 **Adobe Experience Platform資料彙集**.

1. 按一下&#x200B;**[!UICONTROL Save]**。

若要指派此專案 **[!UICONTROL Product profile]** 對於使用者，請遵循下列步驟：

1. 存取 **[!DNL Admin Console]**.
1. 從 **[!UICONTROL Products]** 索引標籤中，選取 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡片。
1. 選取您先前設定的&#x200B;**[!UICONTROL Product profile]**。
1. 在 **[!UICONTROL Users]** 索引標籤中，按一下 **[!UICONTROL Add user]**。
1. 輸入使用者的名稱或電子郵件地址，然後選取使用者。 然後，按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果先前未在Admin Console中建立使用者，請參閱 [新增使用者檔案](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### 設定您的應用程式 {#configure-app}

技術設定涉及應用程式開發人員與企業管理員之間的緊密合作。 開始使用傳送推播通知之前 [!DNL Adobe Campaign]，您必須在以下位置定義設定： [!DNL Adobe Experience Platform Data Collection] 並將您的行動應用程式與Adobe Experience Platform Mobile SDK整合。

請依照以下連結中詳述的實作步驟操作：

* 對象 **Apple iOS**：瞭解如何在中使用APN註冊您的應用程式 [Apple檔案](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* 對象 **Google Android**：瞭解如何在中設定Firebase Cloud Messaging使用者端應用程式 [Google檔案](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## 在Adobe Experience Platform資料彙集中設定行動標籤屬性 {#launch-property}

設定行動屬性可讓行動應用程式開發人員或行銷人員設定行動SDK。 您通常會為想要管理的每個行動應用程式建立行動屬性。 瞭解如何在中建立和設定行動屬性 [Adobe Experience Platform Mobile SDK檔案](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

進一步瞭解 [!DNL Adobe Experience Platform Data Collection] 中的標籤 [Adobe Experience Platform檔案](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

建立後，請開啟新標籤屬性並建立程式庫。 操作步驟：

1. 瀏覽至 **發佈流程** 在左側導覽並選取 **新增程式庫**.
1. 輸入程式庫名稱並選取環境。
1. 選取 **新增所有變更的資源**、和 **儲存並建置到開發環境**.
1. 最後，從下列位置將此程式庫設定為您的工作程式庫： **選取工作程式庫** 按鈕。


## 在行動屬性中設定Adobe Campaign擴充功能 {#configure-extension}

此 **Adobe Campaign Classic擴充功能** 適用於Adobe Experience Platform的Mobile SDK可支援行動應用程式的推播通知，並協助您收集使用者推播權杖，並管理與Adobe Experience Platform服務的互動測量。

此擴充功能同時適用於Campaign Classic v7和Campaign v8，已預先安裝在您的環境中，且必須加以設定。 若要為行動標籤屬性設定擴充功能，請遵循下列步驟：

1. 開啟您之前建立的標籤屬性。
1. 從左側導覽列瀏覽至 **擴充功能**，然後開啟 **目錄** 標籤。 使用搜尋欄位來尋找 **Adobe Campaign Classic** 副檔名。
1. 在Campaign Classic卡中，按一下 **安裝** 按鈕。
1. 依照中的說明輸入設定 [Adobe Experience Platform Mobile SDK檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

您現在可以將Campaign新增至應用程式，如所述  [Adobe Experience Platform Mobile SDK檔案](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## 在Campaign中設定行動服務{#push-service}

一旦您的行動應用程式在中設定完成 [!DNL Adobe Experience Platform Data Collection]，您需要建立兩個服務(一個用於iOS裝置，一個用於Android裝置)才能從傳送推播通知 **[!DNL Adobe Campaign]**.

瞭解如何在中為iOS和Android推播通知建立和設定服務 [本節](../send/push.md#push-config).
