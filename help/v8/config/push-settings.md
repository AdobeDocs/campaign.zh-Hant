---
title: 整合AEP SDK和活動
description: 瞭解如何將Adobe Experience Platform移動軟體開發工具包與您的應用整合
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


# AEP SDK +活動：配置推送通知通道 {#push-notification-configuration}

在開始向Adobe Campaign發送推送通知之前，您需要確保移動應用和Adobe Experience Platform的標籤上都有配置和整合。

Adobe Experience Platform移動SDK通過Android和iOS相容的SDK為您的手機提供客戶端整合API。

要使用Adobe Experience Platform移動SDK設定應用，請執行以下步驟：

1. 檢查 [先決條件](#before-starting)。
1. 設定 [移動標籤屬性](#launch-property) 在Adobe Experience Platform資料收集中。
1. 詳細瞭解Adobe Experience Platform移動軟體開發工具包 [此頁](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}。
1. （可選）啟用日誌記錄和生命週期度量，如詳細說明 [此頁](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}。
1. （可選）添加 [Adobe Experience Platform對你的應用的保證](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}。
1. 關注 [Adobe Experience Platform移動SDK文檔](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} 在您的應用中使用Adobe Experience Platform移動軟體開發工具包進行設定。
1. 安裝和配置 [Adobe Campaign分機](#configure-extension) 你的移動房產。
1. 在Adobe Campaign配置您的iOS和Android移動服務 [此頁](../send/push.md#push-config)。


## 必要條件 {#before-starting}

### 設定權限 {#setup-permissions}

在建立移動應用程式之前，首先需要確保您在Adobe Experience Platform擁有或分配了正確的標籤用戶權限。 Adobe Experience Platform中標籤的用戶權限通過Adobe Admin Console分配給用戶。 瞭解詳情 [標籤文檔](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}。

>[!CAUTION]
>
>推送配置必須由專家用戶執行。 根據您的實施模式和參與此實施的人員，您可能需要將完整權限集分配給單個產品配置檔案，或在應用程式開發人員與 **Adobe Campaign** 管理員。

分配 **屬性** 和 **公司** ，請執行以下步驟：

1. 訪問 **[!DNL Admin Console]**。
1. 從 **[!UICONTROL Products]** 頁籤 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡。
1. 選擇現有 **[!UICONTROL Product Profile]** 或用 **[!UICONTROL New profile]** 按鈕 瞭解如何建立新 **[!UICONTROL New profile]** 的 [管理控制台文檔](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}。
1. 在&#x200B;**[!UICONTROL Permissions]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Property Rights]**。
1. 按一下 **[!UICONTROL Add all]**。這將在您的產品配置檔案中添加以下權限：
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   安裝和發佈Adobe Campaign擴展，以及在中發佈應用屬性需要這些權限 **Adobe Experience Platform移動SDK**。

1. 然後，選擇 **[!UICONTROL Company rights]** 的上界。
1. 添加以下權限：

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   這些權限是移動應用程式開發人員在中設定推送憑據所必需的 **Adobe Experience Platform資料收集**。

1. 按一下&#x200B;**[!UICONTROL Save]**。

分配此 **[!UICONTROL Product profile]** 對於用戶，請執行以下步驟：

1. 訪問 **[!DNL Admin Console]**。
1. 從 **[!UICONTROL Products]** 頁籤 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡。
1. 選取您先前設定的&#x200B;**[!UICONTROL Product profile]**。
1. 在 **[!UICONTROL Users]** 索引標籤中，按一下 **[!UICONTROL Add user]**。
1. 鍵入用戶名或電子郵件地址並選擇用戶。 然後，按一下 **[!UICONTROL Save]**。

   >[!NOTE]
   >
   >如果用戶以前未在管理控制台中建立，請參閱 [添加用戶文檔](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}。

### 配置你的應用 {#configure-app}

技術設定涉及應用程式開發人員與業務管理員之間的密切合作。 開始發送推送通知之前 [!DNL Adobe Campaign]，您需要在 [!DNL Adobe Experience Platform Data Collection] 並將您的移動應用與Adobe Experience Platform移動軟體開發工具包整合。

按照以下連結中詳述的實施步驟操作：

* 對於 **AppleiOS**:瞭解如何在中的APN中註冊您的應用 [Apple文檔](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* 對於 **Google安卓**:瞭解如何在Android中設定Firebase雲消息客戶端應用 [Google文檔](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

## 在Adobe Experience Platform資料收集中設定移動標籤屬性 {#launch-property}

設定移動屬性允許移動應用開發者或營銷者配置移動SDK。 通常，您會為要管理的每個移動應用程式建立一個移動屬性。 瞭解如何在中建立和配置移動屬性 [Adobe Experience Platform移動SDK文檔](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}。
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

瞭解有關 [!DNL Adobe Experience Platform Data Collection] 標籤 [Adobe Experience Platform文檔](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}。

建立後，開啟新標籤屬性並建立庫。 操作步驟：

1. 瀏覽到 **發佈流** 在左側導航中，然後選擇 **添加庫**。
1. 輸入庫名稱並選擇環境。
1. 選擇 **添加所有更改的資源**, **保存並生成到開發**。
1. 最後，將此庫設定為您的工作庫 **選擇工作庫** 按鈕


## 在移動屬性中配置Adobe Campaign分機 {#configure-extension}

的 **Adobe Campaign Classic擴展** 對於Adobe Experience Platform移動軟體開發工具包，它可為您的移動應用提供推送通知功能，並幫助您收集用戶推送令牌並管理與Adobe Experience Platform服務的交互測量。

此擴展適用於Campaign Classicv7和營銷活動v8 ，它預裝在您的環境中，必須進行配置。 要為移動標籤屬性配置擴展，請執行以下步驟：

1. 開啟之前建立的標籤屬性。
1. 從左側導航，瀏覽到 **擴展**，然後開啟 **目錄** 頁籤。 使用搜索欄位查找 **Adobe Campaign Classic** 擴展。
1. 在Campaign Classic卡上，按一下 **安裝** 按鈕
1. 按中所述輸入設定 [Adobe Experience Platform移動SDK文檔](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}。

您現在可以將市場活動添加到您的應用中，如中所述  [Adobe Experience Platform移動SDK文檔](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}。

## 在市場活動中配置您的移動服務{#push-service}

在中設定你的移動應用後 [!DNL Adobe Experience Platform Data Collection]您需要建立兩個服務(一個用於iOS設備，一個用於安卓設備)，以便能夠從 **[!DNL Adobe Campaign]**。

瞭解如何在中為iOS和Android推送通知建立和配置服務 [此部分](../send/push.md#push-config)。
