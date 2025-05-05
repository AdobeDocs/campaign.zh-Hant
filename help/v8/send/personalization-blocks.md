---
title: 使用個人化區塊
description: 瞭解如何在訊息內容中使用內建的個人化區塊
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%

---

# 使用個人化區塊{#personalization-blocks}

個人化區塊是動態內容，包含您可以插入傳送中的特定轉譯。 例如，您可以新增標誌、問候語訊息或映象頁面的連結。

若要存取個人化內容區塊，請瀏覽至總管的&#x200B;**[!UICONTROL Resources > Campaign Management > Personalization blocks]**&#x200B;節點。 [此區段](#ootb-personalization-blocks)中列出內建的個人化區塊。

您也可以定義新區塊，以最佳化您的傳送個人化。 [了解更多](#create-custom-personalization-blocks)。

## 插入個人化區塊 {#insert-personalization-blocks}

若要在訊息中插入個人化區塊，請遵循下列步驟：

1. 在傳遞精靈的內容編輯器中，按一下個人化圖示並選取&#x200B;**[!UICONTROL Include]**&#x200B;功能表。
1. 從清單中選取個人化區塊，或按一下&#x200B;**[!UICONTROL Other...]**&#x200B;功能表以存取完整清單。

   ![](assets/perso-content-block.png)

1. 然後，個人化區塊會插入為指令碼。 產生個人化時，會自動調整成適合收件者設定檔。
1. 瀏覽至&#x200B;**[!UICONTROL Preview]**&#x200B;索引標籤並選取收件者，以檢視特定收件者的此區塊內容。

您可以在傳遞內容中包含個人化區塊的原始碼。 若要這麼做，請在選取&#x200B;**[!UICONTROL Include the HTML source code of the block]**&#x200B;時選取它。

## 內建個人化區塊 {#ootb-personalization-blocks}

內建的個人化區塊包括：

* **[!UICONTROL Enabled by Adobe Campaign]**：插入「由Adobe Campaign啟用」標誌。
* **[!UICONTROL Formatting function for proper nouns]**：產生&#x200B;**[!UICONTROL toSmartCase]** Javascript函式，這會將每個字的第一個字母變更為大寫。
* **[!UICONTROL Greetings]**：插入問候語，其中包含收件者的全名，後面接著逗號。 範例：「你好 John Doe，」。
* **[!UICONTROL Insert logo]**：插入已在執行個體設定中定義的標誌。
* **[!UICONTROL Link to mirror page]**：插入連結至[映象頁面](mirror-page.md)。 預設格式：「如果您無法正確檢視此訊息，請按一下此處」。
* **[!UICONTROL Mirror page URL]**：插入映象頁面URL，讓傳送設計工具檢查連結。
* **[!UICONTROL Offer acceptance URL in unitary mode]**：插入URL以設定選件為&#x200B;**[!UICONTROL Accepted]**。 (如果啟用互動模組，則此區塊可用)
* **[!UICONTROL Registration confirmation]**：插入連結以確認訂閱。
* **[!UICONTROL Registration link]**：插入訂閱連結。 此連結在執行個體設定中定義。預設內容：「若要註冊，請按一下這裡。」
* **[!UICONTROL Registration link (with referrer)]**：插入訂閱連結，以識別訪客和傳遞。 此連結在執行個體設定中定義。
* **[!UICONTROL Registration page URL]**：插入訂閱網址
* **[!UICONTROL Style of content emails]**&#x200B;和&#x200B;**[!UICONTROL Notification style]**：產生程式碼，使用預先定義的HTML樣式來格式化電子郵件。
* **[!UICONTROL Unsubscription link]**：插入連結，以取消訂閱所有傳遞（封鎖清單）。 預設關聯內容：「您收到此訊息因為您曾聯絡&#x200B;***您的組織名稱***&#x200B;或附屬機構。若不要再收到來自&#x200B;***您的組織名稱***&#x200B;的訊息，請按一下這裡。」

## 建立自訂個人化區塊 {#create-custom-personalization-blocks}

您可以定義要從個人化圖示插入的新個人化內容區塊。

若要建立個人化區塊，請遵循下列步驟：

1. 瀏覽至Campaign檔案總管的&#x200B;**[!UICONTROL Resources > Campaign Management > Personalization blocks]**&#x200B;資料夾。
1. 在內建區塊清單上方，按一下&#x200B;**[!UICONTROL New]**。

   ![](assets/perso-new-block.png)

1. 填寫個人化區塊的設定：

   ![](assets/perso-custom-block.png)

   * 輸入區塊的標籤。 此標籤會顯示在個人化欄位插入視窗中。
   * 選取&#x200B;**傳遞**&#x200B;內容型別。
   * 啟用&#x200B;**[!UICONTROL Visible in the customization menus]**&#x200B;選項，讓此區塊可從個人化欄位插入圖示存取。
   * 必要時，請啟用&#x200B;**[!UICONTROL The content of the personalization block depends upon the format]**&#x200B;選項，為HTML和文字電子郵件定義兩個不同的區塊。
   * 輸入內容(HTML、文字、JavaScript等) 個人化區塊的，然後按一下&#x200B;**[!UICONTROL Save]**。

儲存後，新的個人化區塊便可在傳遞編輯器中使用。

## 教學課程影片 {#personalization-blocks-video}

在以下影片中瞭解如何建立動態內容區塊，以及如何使用這些區塊來個人化您的電子郵件傳送內容。

>[!VIDEO](https://video.tv.adobe.com/v/3449017?quality=12&captions=chi_hant)
