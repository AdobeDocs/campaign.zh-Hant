---
audience: end-user
title: 設計豐富推送通知傳送
description: 瞭解如何使用Adobe Campaign Web設計Android豐富推送通知傳送
feature: Push
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 771473620ea9b6d71be72871255d22b816c51b91
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 5%

---

# 設計Android豐富推送傳送 {#rich-push}

使用Firebase Cloud Messaging時，您可以選擇兩種型別的訊息：

* 此 **[!UICONTROL Data message]** 由使用者端應用程式處理。 這些訊息會直接傳送至行動應用程式，在裝置上產生和顯示Android通知。 資料訊息僅包含您的自訂應用程式變數。

* 此 **[!UICONTROL Notification message]**，會由FCM SDK自動處理。 FCM會自動代表使用者端應用程式在使用者裝置上顯示訊息。 通知訊息包含預先定義的一組引數和選項，但仍可使用自訂應用程式變數進一步個人化。

## 定義通知的內容 {#push-message}

建立推播傳送後，您就可以定義其內容。 有三個範本可供使用：

* **預設範本** 可讓您傳送包含簡單圖示和隨附影像的通知。

* **基本範本** 可在您的通知中包含文字、影像和按鈕。

* **傳送範本** 可讓您傳送包含文字和多個影像的通知，以供使用者瀏覽。

瀏覽下列標籤，瞭解如何為每個範本撰寫訊息。

>[!BEGINTABS]

>[!TAB 預設範本]

1. 從 **[!UICONTROL Notification type]** 下拉式清單，選取 **[!UICONTROL Default]**.

   ![](assets/rich_push_default.png)

1. 若要撰寫訊息，請在 **[!UICONTROL Title]** 和 **[!UICONTROL Message]** 欄位。

   ![](assets/rich_push_default_2.png)

1. 使用動態個人化欄位來定義內容、個人化資料並新增動態內容。 [了解更多](../send/personalize.md)

1. 若要進一步個人化您的推播通知，請設定 **[!UICONTROL Notification options]** 和 **[!UICONTROL HTTPv1 additional options]** 的預設值。 [了解更多](#push-advanced)

   ![](assets/rich_push_default_3.png)

定義訊息內容後，您可以使用測試訂閱者來預覽及測試訊息。

>[!TAB 基本範本]

1. 從 **[!UICONTROL Notification Type]** 下拉式清單，選取 **[!UICONTROL Basic]**.

   ![](assets/rich_push_basic.png)

1. 若要撰寫訊息，請在 **[!UICONTROL Title]**， **[!UICONTROL Message]** 和 **[!UICONTROL Expanded message]** 欄位。

   此 **[!UICONTROL Message]** 文字會顯示在收合的檢視中，而 **[!UICONTROL Expanded message]** 在展開通知時顯示。

   ![](assets/rich_push_basic_2.png)

1. 使用動態個人化欄位來定義內容、個人化資料並新增動態內容。 [了解更多](../send/personalize.md)

1. 在 **[!UICONTROL Color options]** 選單中，輸入您的十六進位色彩代碼 **[!UICONTROL Title]**， **[!UICONTROL Message]** 和 **[!UICONTROL Background]**.

1. 新增 **[!UICONTROL Remind later button]** 如有需要。 輸入您的 **[!UICONTROL Reminder Text]** 和 **日期** 於對應欄位中。

   此 **[!UICONTROL Reminder Date]** 欄位需要代表紀元的值（以秒為單位）。

1. 按一下 **[!UICONTROL Add button]** 並填入下列欄位：

   * **[!UICONTROL Label]**：按鈕上顯示的文字。
   * **[!UICONTROL Link URI]**：指定按一下按鈕時所要執行的URI。

   您可以選擇在推播通知中包含最多三個按鈕。 如果您選擇使用 **[!UICONTROL Remind later button]**，您最多只能包含兩個按鈕。

1. 選取 **[!UICONTROL Link type]** 的已連結URL的：

   * **[!UICONTROL Web URL]**：網頁URL會將使用者導向至線上內容。 按一下後，它們會提示裝置的預設網頁瀏覽器開啟並導覽至指定的URL。

   * **[!UICONTROL Deeplink]**：深層連結是引導使用者前往應用程式內特定區段的URL，即使應用程式已關閉。 按一下即可顯示對話方塊，讓使用者從能夠處理連結的各種應用程式中進行選擇。

   * **[!UICONTROL Open App]**：開啟應用程式URL可讓您直接連線至應用程式內的內容。 它可讓您的應用程式繞過消除歧義對話方塊，將其自身建立為特定連結型別的預設處理常式。

   如需如何處理Android應用程式連結的詳細資訊，請參閱 [Android開發人員檔案](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. 若要進一步個人化您的推播通知，請設定 **[!UICONTROL Notification options]** 和 **[!UICONTROL HTTPv1 additional options]** 的預設值。 [了解更多](#push-advanced)

   ![](assets/rich_push_basic_4.png)

定義訊息內容後，您可以使用測試訂閱者來預覽及測試訊息。

>[!TAB 傳送範本]

1. 從 **[!UICONTROL Notification Type]** 下拉式清單，選取 **[!UICONTROL Carousel]**.

   ![](assets/rich_push_carousel.png)

1. 若要撰寫訊息，請在 **[!UICONTROL Title]**， **[!UICONTROL Message]** 和 **[!UICONTROL Expanded message]** 欄位。

   此 **[!UICONTROL Message]** 文字會顯示在收合的檢視中，而 **[!UICONTROL Expanded message]** 在展開通知時顯示。

   ![](assets/rich_push_carousel_1.png)

1. 使用運算式編輯器來定義內容、個人化資料及新增動態內容。 [了解更多](../send/personalize.md)

1. 在 **[!UICONTROL Color options]** 選單中，輸入您的十六進位色彩代碼 **[!UICONTROL Title]**， **[!UICONTROL Message]** 和 **[!UICONTROL Background]**.

1. 選擇如何 **[!UICONTROL Carousel]** 已操作：

   * **[!UICONTROL Auto]**：以投影片形式自動循環顯示影像，並以預先定義的時間間隔轉換。
   * **[!UICONTROL Manual]**：可讓使用者在幻燈片之間手動撥動，以導覽影像。

1. 從 **[!UICONTROL Layout]** 下拉式清單，選取 **[!UICONTROL Filmstrip]** 在主投影片旁加入上一個和下一個影像的預覽。

1. 按一下 **[!UICONTROL Add image]** 並輸入影像URL、文字和動作URL。

   請確定您至少包含三個影像，最多包含五個影像。

   ![](assets/rich_push_carousel_2.png)

1. 若要進一步個人化您的推播通知，請設定 **[!UICONTROL Notification options]** 和 **[!UICONTROL HTTPv1 additional options]** 的預設值。 [了解更多](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

定義訊息內容後，您可以使用測試訂閱者來預覽及測試訊息。

>[!ENDTABS]

## 推播通知進階設定 {#push-advanced}

### 通知選項 {#notification-options}

| 參數 | 說明 |
|---------|---------|
| **[!UICONTROL Channel ID]** | 設定通知的頻道ID。 在收到具有此管道ID的任何通知之前，應用程式必須建立具有此管道ID的管道。 |
| **[!UICONTROL Icon]** | 設定要在設定檔裝置上顯示的通知圖示。 |
| **[!UICONTROL Sound]** | 設定裝置收到通知時播放的音效。 |
| **[!UICONTROL Tag]** | 設定用來取代通知抽屜中現有通知的識別碼。 這有助於防止累積多個通知，並確保只顯示最新的相關通知。 |
| **[!UICONTROL Color]** | 以十六進位色彩代碼設定通知的圖示色彩。 |
| **[!UICONTROL Click action]** | 設定與使用者點按您的通知相關聯的動作。 |
| **[!UICONTROL Notification background color]** | 使用十六進位色彩代碼設定通知背景的色彩。 |
| **[!UICONTROL Link type]** | <ul><li>網頁URL：網頁URL會將使用者導向至線上內容。 按一下後，它們會提示裝置的預設網頁瀏覽器開啟並導覽至指定的URL。</li><li>深層連結：深層連結是指即使應用程式已關閉，仍可指引使用者前往應用程式內的特定區段的URL。 按一下即可顯示對話方塊，讓使用者從能夠處理連結的各種應用程式中進行選擇。</li><li> 開啟應用程式：開啟應用程式URL可讓您直接連線至應用程式內的內容。 它可讓您的應用程式繞過消除歧義對話方塊，將其自身建立為特定連結型別的預設處理常式。</li></ul> |

### HTTPv1其他選項 {#additional-options}

| 參數 | 說明 |
|---------|---------|
| **[!UICONTROL Ticker]** | 設定通知的提示文字。 僅適用於設為Android 5.0 Lollipop的裝置。 |
| **[!UICONTROL Sticky]** | 啟動後，通知仍可見，即使使用者按一下它。 <br>如果停用，則當使用者與通知互動時，會自動解除通知。 粘性行為可讓重要通知在熒幕上持續較長時間。 |
| **[!UICONTROL Image]** | 設定要在通知中顯示的影像URL。 |
| **[!UICONTROL Notification Priority]** | 設定通知的優先順序層級，可以是預設、最低、低或高。 優先順序層級會決定通知的重要性和急迫性，影響其顯示方式以及是否可以略過某些系統設定。 有關詳細資訊，請參閱 [FCM檔案](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Notification Count]** | 設定直接在應用程式圖示上顯示的新未讀取資訊數目。 此讓使用者迅速查看待處理的通知數量。 |
| **[!UICONTROL Visibility]** | 設定通知的可見度等級，可為公開、私人或秘密。 可見度等級會決定通知內容在鎖定畫面和其他敏感區域上顯示的程度。 如需詳細資訊，請參閱 [FCM檔案](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Application variables]** | 允許您定義通知行為。 這些變數完全可自訂，且可納入傳送到行動裝置的部分訊息承載。 |
