---
title: 使用個人化區塊
description: 了解如何在訊息內容中使用內建的個人化區塊
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---

# 使用個人化區塊{#personalization-blocks}

個人化區塊是動態內容，包含您可插入至傳送的特定轉譯。 例如，您可以新增標誌、問候訊息或鏡像頁面的連結。

若要存取個人化內容區塊，請瀏覽至 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** 瀏覽器的節點。 內建個人化區塊列於 [本節](#ootb-personalization-blocks).

您也可以定義新區塊，以最佳化傳遞個人化。 [了解更多資訊](#create-custom-personalization-blocks)。

## 插入個人化區塊 {#insert-personalization-blocks}

若要在訊息中插入個人化區塊，請遵循下列步驟：

1. 在傳遞精靈的內容編輯器中，按一下個人化圖示並選取 **[!UICONTROL Include]** 功能表。
1. 從清單中選取個人化區塊，或按一下 **[!UICONTROL Other...]** 功能表來存取完整清單。

   ![](assets/perso-content-block.png)

1. 接著，個人化區塊會以指令碼的形式插入。 系統會在產生個人化時自動調整至收件者設定檔。
1. 瀏覽至 **[!UICONTROL Preview]** 頁簽，並選取收件者以檢視特定收件者的此區塊內容。

您可以在傳遞內容中加入個人化區塊的原始碼。 要執行此操作，請選取 **[!UICONTROL Include the HTML source code of the block]** 的子句。

## 內建個人化區塊 {#ootb-personalization-blocks}

內建的個人化區塊包括：

* **[!UICONTROL Enabled by Adobe Campaign]**:插入「Enabled by Adobe Campaign」標誌。
* **[!UICONTROL Formatting function for proper nouns]**:會產生 **[!UICONTROL toSmartCase]** Javascript函式，可將每個字詞的首字母變更為大寫。
* **[!UICONTROL Greetings]**:插入帶有收件人全名的問候語，後面跟逗號。 範例：「你好，無名氏，」
* **[!UICONTROL Insert logo]**:插入在實例設定中定義的徽標。
* **[!UICONTROL Link to mirror page]**:插入連結至 [鏡像頁面](mirror-page.md). 預設格式為：「如果您無法正確檢視此訊息，請按一下這裡」。
* **[!UICONTROL Mirror page URL]**:插入鏡像頁面URL，使「傳遞設計人員」能夠檢查連結。
* **[!UICONTROL Offer acceptance URL in unitary mode]**:插入URL，以便將選件設定為 **[!UICONTROL Accepted]**. （如果已啟用互動模組，便可使用此區塊）
* **[!UICONTROL Registration confirmation]**:插入啟用以確認訂閱的連結。
* **[!UICONTROL Registration link]**:插入訂閱連結。 此連結會在執行個體設定中定義。 預設內容為：&quot;要註冊，請按一下這裡。&quot;
* **[!UICONTROL Registration link (with referrer)]**:插入訂閱連結，以識別訪客和傳送。 此連結會在執行個體設定中定義。
* **[!UICONTROL Registration page URL]**:插入訂閱URL
* **[!UICONTROL Style of content emails]** 和 **[!UICONTROL Notification style]**:產生程式碼，使用預先定義的HTML樣式來格式化電子郵件。
* **[!UICONTROL Unsubscription link]**:插入可從所有傳送（封鎖清單）中取消訂閱的連結。 預設關聯內容為：「你收到這條資訊是因為你與 ***您的組織名稱*** 或附屬機構。 不再接收來自 ***您的組織名稱*** 按一下這裡。」

## 建立自訂個人化區塊 {#create-custom-personalization-blocks}

您可以定義要從個人化圖示插入的新個人化內容區塊。

若要建立個人化區塊，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** Campaign檔案總管的資料夾。
1. 在內建區塊清單上方，按一下 **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. 填入個人化區塊的設定：

   ![](assets/perso-custom-block.png)

   * 輸入區塊的標籤。 此標籤會顯示在個人化欄位插入視窗中。
   * 選取 **傳送** 內容類型。
   * 啟用 **[!UICONTROL Visible in the customization menus]** 選項，從個人化欄位插入圖示存取此區塊。
   * 如有必要，請啟用 **[!UICONTROL The content of the personalization block depends upon the format]** 選項，為HTML和文字電子郵件定義兩個不同的區塊。
   * 輸入內容(在HTML、文字、JavaScript等中) ，然後按一下 **[!UICONTROL Save]**.

儲存後，傳遞編輯器中即可使用新的個人化區塊。

## 教學課程影片 {#personalization-blocks-video}

透過下列影片了解如何建立動態內容區塊，以及如何使用區塊將電子郵件傳送的內容個人化。

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
