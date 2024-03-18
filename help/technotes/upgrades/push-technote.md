---
product: campaign
title: 推播通知頻道近期變更
description: 推播通知頻道近期變更
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="也適用於Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="套用至Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: a494ac834b1febcafe04f4bb05eb74834df7b024
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 1%

---

# 推播通知頻道變更 {#push-upgrade}

您可以使用Campaign在iOS和Android裝置上傳送推播通知。 為此，Campaign需仰賴行動應用程式訂閱服務。

Android Firebase Cloud Messaging (FCM)服務的一些重要變更將於2024年發行，可能會影響您的Adobe Campaign實施。 您可能需要更新Android推送訊息的訂閱服務設定，才能支援此變更。

此外，Adobe強烈建議改用權杖式連線來連線APN，而非更安全、更可擴充的憑證式連線。

## Google Android Firebase Cloud Messaging (FCM)服務 {#fcm-push-upgrade}

### 哪些部分有所變更？ {#fcm-changes}

為Google持續改善其服務，我們將於以下日期終止使用舊版FCM API： **2024年6月20日**. 在中進一步瞭解Firebase雲端通訊HTTP通訊協定 [Google Firebase檔案](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7和Adobe Campaign v8已支援最新API來傳送推播通知訊息。 不過，有些舊版實作仍需仰賴舊版API。 必須更新這些實作。

### 您有受到影響嗎？ {#fcm-impact}

如果您目前的實作支援使用舊版API連線至FCM的訂閱服務，則會受到影響。 轉換至最新的API是必須的，這樣才能避免任何服務中斷。 在這種情況下，Adobe團隊會與您聯絡。

若要檢查您是否受到影響，您可以篩選 **服務與訂閱** 根據以下篩選：

![](assets/filter-services-fcm.png)


* 如果您的任何使用中推播通知服務使用 **HTTP （舊版）** API，此變更將直接影響您的設定。 您必須檢閱目前的設定，並依照下方所述移至較新的API。

* 如果您的設定僅使用 **HTTP v1** Android推播通知的API，則表示您已符合法規，不需要採取任何進一步動作。

### 如何更新？ {#fcm-transition-procedure}

#### 先決條件 {#fcm-transition-prerequisites}

* 針對Campaign Classic v7,20.3.1版本已新增支援HTTP v1。 如果您的環境執行於舊版，轉換至HTTP v1的先決條件是將環境升級至 [最新Campaign Classic建置](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. 若為Campaign v8，所有發行版本都支援HTTP v1，且不需要升級。

* 需要Android Firebase Admin SDK服務的帳戶JSON檔案，才能將行動應用程式移至HTTP v1。 瞭解如何取得此檔案於 [Google Firebase檔案](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* 對於混合、託管和Managed Services部署，除了下列轉換程式外，請聯絡Adobe以更新即時(RT)執行伺服器。 中間來源伺服器不受影響。

* 身為Campaign Classic v7內部部署使用者，您必須升級行銷和即時執行伺服器。 中間來源伺服器不受影響。

#### 轉換程式 {#fcm-transition-steps}

若要將環境移至HTTP v1，請遵循下列步驟：

1. 瀏覽至您的清單 **服務與訂閱**.
1. 列出所有行動應用程式 **HTTP （舊版）** API版本。
1. 針對這些行動應用程式，設定 **API版本** 至 **HTTP v1**.
1. 按一下 **[!UICONTROL Load project json file to extract project details...]** 直接載入JSON金鑰檔案的連結。

   您也可以手動輸入下列明細：

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. 按一下 **[!UICONTROL Test the connection]** 檢查您的設定是否正確，以及行銷伺服器是否擁有FCM的存取權。 請注意，對於中間來源部署， **[!UICONTROL Test connection]** 按鈕無法檢查伺服器是否可存取Android Firebase雲端通訊(FCM)服務。
1. 或者，您也可以選擇擴充推送訊息的內容 **[!UICONTROL Application variables]** 如有需要。 這些都是可完全自訂的專案，而且是傳送至行動裝置的訊息裝載的一部分。
1. 按一下 **[!UICONTROL Finish]**，之後 **[!UICONTROL Save]**。

以下是FCM裝載名稱，可進一步個人化您的推播通知。 這些選項會詳細說明 [此處](#fcm-apps).

| 訊息類型 | 可設定的訊息元素（FCM裝載名稱） | 可設定的選項（FCM裝載名稱） |
|:-:|:-:|:-:|
| 資料訊息 | N/A | validate_only |
| 通知訊息 | 標題，內文， android_channel_id，圖示，聲音，標籤，顏色，點選動作，影像，提示，粘性，可見度，通知優先順序，通知計數 <br> | validate_only |


>[!NOTE]
>
>這些變更套用至您的所有伺服器後，所有傳送至Android裝置的新推播通知都會使用HTTP v1 API。 處於重試、進行中及使用中的現有推播傳送仍使用HTTP （舊版） API。

### 對我的Android應用程式有何影響？ {#fcm-apps}

Android行動應用程式的程式碼不需要特定變更，且通知行為不應變更。

不過，使用HTTP v1時，您可以透過進一步個人化推播通知 **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

您可以：

* 使用 **[!UICONTROL Ticker]** 欄位以設定通知的提示文字。
* 使用 **[!UICONTROL Image]** 欄位來設定要在通知中顯示的影像URL。
* 使用 **[!UICONTROL Notification Count]** 欄位來設定直接在應用程式圖示上顯示的新未讀取資訊數目。
* 設定 **[!UICONTROL Sticky]** 選項設為false，如此一來，使用者按一下通知時，就會自動將其關閉。 如果設為true，則即使使用者按一下通知，仍會顯示通知。
* 設定 **[!UICONTROL Notification Priority]** 您的通知層級為預設、最低、低或高。
* 設定 **[!UICONTROL Visibility]** 您向公開、私人或機密發出通知的層級。

如需詳細資訊，請參閱 **[!UICONTROL HTTP v1 additional options]** 以及如何填寫這些欄位，請參閱 [FCM檔案](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.




## Apple iOS推播通知服務(APN) {#apns-push-upgrade}

### 哪些部分有所變更？ {#ios-changes}

依照Apple的建議，您應使用無狀態驗證權杖來保護與Apple推播通知服務(APN)的通訊。

權杖型驗證提供與APN無狀態通訊的方式。 無狀態通訊比憑證式通訊更快，因為無狀態通訊不需要APN查閱憑證或其他與您的提供者伺服器相關的資訊。 使用權杖型驗證還有其他優點：

* 您可以使用來自多個提供者伺服器的相同Token。

* 您可以使用一個Token為貴公司的所有應用程式散發通知。

瞭解更多有關與APN的權杖型連線，位於 [Apple開發人員檔案](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7和Adobe Campaign v8同時支援權杖型和憑證型連線。 如果您的實施仰賴憑證式連線，Adobe強烈建議您將其更新為權杖式連線。

### 您有受到影響嗎？ {#ios-impact}

如果您目前的實施仰賴憑證式請求來連線至APN，則會受到影響。 建議轉換為權杖型連線。

若要檢查您是否受到影響，您可以篩選 **服務與訂閱** 根據以下篩選：

![](assets/filter-services-ios.png)


* 如果您的任何使用中推播通知服務使用 **憑證式驗證** 模式，則應檢閱您目前的實施並將其移至 **權杖型驗證** 模式，如下所述。

* 如果您的設定僅使用 **權杖型驗證** 模式使用iOS推播通知，則您的實作已處於最新狀態，不需要您採取進一步動作。

### 如何更新？ {#ios-transition-procedure}

#### 先決條件 {#ios-transition-prerequisites}

* 對於Campaign Classic v7，支援 **權杖型驗證** 模式已新增至20.2版本。 如果您的環境執行於舊版，此變更的先決條件是將環境升級至 [最新Campaign Classic建置](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. 對於Campaign v8， **權杖型驗證** 所有發行版本都支援模式，不需要升級。

* 您需要APNs驗證Token簽署金鑰才能產生您的伺服器所使用的Token。 如中所述，您需向Apple開發人員帳戶索取此金鑰 [Apple開發人員檔案](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* 對於混合、託管和Managed Services部署，除了下列轉換程式外，請聯絡Adobe以更新即時(RT)執行伺服器。 中間來源伺服器不受影響。

* 身為Campaign Classic v7內部部署使用者，您必須升級行銷和即時執行伺服器。 中間來源伺服器不受影響。

#### 轉換程式 {#ios-transition-steps}

若要將iOS行動應用程式移至權杖型驗證模式，請遵循下列步驟：

1. 瀏覽至您的清單 **服務與訂閱**.
1. 列出所有行動應用程式 **憑證式驗證** 模式。
1. 編輯每個行動應用程式，並瀏覽至 **憑證/私密金鑰** 標籤。
1. 從 **驗證模式** 下拉式清單，選取 **權杖型驗證**.
1. 填寫APNs連線設定 **[!UICONTROL Key Id]**， **[!UICONTROL Team Id]** 和 **[!UICONTROL Bundle Id]** 然後按一下「 」以選取您的p8憑證 **[!UICONTROL Enter the private key...]**.

   ![](assets/token-based-certif.png)

1. 按一下 **[!UICONTROL Test the connection]** 檢查您的設定是否正確，以及伺服器是否擁有APN的存取權。 請注意，對於中間來源部署， **[!UICONTROL Test connection]** 按鈕無法檢查伺服器是否具有APN的存取權。
1. 按一下 **[!UICONTROL Next]** 以開始設定生產應用程式，並依照上述步驟進行。
1. 按一下 **[!UICONTROL Finish]**，之後 **[!UICONTROL Save]**。

您的iOS應用程式現在已移至權杖型驗證模式。
