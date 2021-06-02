---
product: Adobe Campaign
title: 使用Adobe Campaign傳送電子郵件
description: 開始使用Campaign中的電子郵件
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: d1e96b1311d9de24ceb918230186cd3cad609ab2
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 4%

---

# 設計和傳送電子郵件

電子郵件傳送可讓您傳送個人化電子郵件給目標人口。

[!DNL :arrow_upper_right:] 進一步了 [解Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html)。

## 建立您的第一個電子郵件傳送

建立與客戶體驗其餘部分一致的個人化和情境相關電子郵件。

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [了解如何在Analytics v7檔案中建立電子郵件傳送Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


在下列範例中，您將學習在Adobe Campaign中設計電子郵件傳送的步驟，其中包含個人化資料、外部URL的連結、鏡像頁面的連結以及Web表單的連結。

1. 建立傳送

   若要建立新傳送，請瀏覽至&#x200B;**Campaigns**&#x200B;標籤，按一下&#x200B;**Delives**，然後按一下現有傳送清單上方的&#x200B;**Create**&#x200B;按鈕。

   ![](assets/delivery_step_1.png)

1. 選取範本

   選取傳送範本，然後為您的傳送命名。 此名稱只會顯示給Adobe Campaign Console的使用者，而不會顯示給收件者，不過傳送清單中會顯示此標題。 按一下 **[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. 匯入您的內容

   按一下&#x200B;**Source**&#x200B;標籤以貼上您的HTML內容。

   ![](assets/paste-content.png)


1. 個人化您的訊息


   * 顯示收件者的名字和名字

      若要將收件者的第一和第二名稱插入傳遞中的文字欄位，請按一下您選取的文字欄位，然後將游標置於您要顯示這些名稱的位置。 按一下彈出工具欄中的第一個表徵圖，然後按一下&#x200B;**[!UICONTROL Personalization block]**。 選擇&#x200B;**[!UICONTROL Greetings]**，然後按一下&#x200B;**[!UICONTROL OK]**。

   * 將連結插入影像中

      若要透過影像將傳送收件者帶至外部地址，請按一下相關影像以顯示快顯工具列，將游標置於第一個圖示上，然後按一下&#x200B;**[!UICONTROL Link to an external URL]**。

      在&#x200B;**URL**&#x200B;欄位中輸入連結的URL，使用下列格式&#x200B;**https://www.myURL.com**，然後確認。

      您可以隨時使用視窗右側的區段來變更連結。

   * 將連結插入文字

      若要將外部連結整合到您傳送的文字中，請選取一些文字或一組文字，然後按一下快顯工具列中的第一個圖示。 按一下&#x200B;**[!UICONTROL Link to an external URL]**，在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中輸入連結地址。

      您可以隨時使用視窗右側的區段來變更連結。

   * 添加鏡像頁

      若要讓收件者在網頁瀏覽器中檢視您的傳遞內容，您可以將鏡像頁面的連結整合到您的傳遞中。

      按一下您要查看所張貼連結的文字欄位。 按一下彈出工具欄中的第一個表徵圖，選擇&#x200B;**[!UICONTROL Personalization block]**，然後選擇&#x200B;**[!UICONTROL Link to Mirror Page (MirrorPage)]**。 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以確認。

   * 整合Web應用程式的連結

      數位內容編輯器可讓您整合從Adobe Campaign主控台（例如登錄頁面或表單頁面）指向Web應用程式的連結。 有關詳細資訊，請參閱[連結到Web應用程式](../../web/using/editing-content.md#link-to-a-web-application)。

      為連結至Web應用程式的文字欄位，然後按一下第一個圖示。 選擇&#x200B;**[!UICONTROL Link to a Web application]**，然後按一下&#x200B;**Web應用程式**&#x200B;欄位結尾的表徵圖，選擇所需的應用程式。

1. 傳送訊息

   整合內容後，按一下&#x200B;**Save**&#x200B;儲存傳送。 它現在會顯示在您的傳送清單中，位於&#x200B;**[!UICONTROL Campaigns > Deliveries]**&#x200B;標籤中。


## 建立內容並選取對象

您可以直接建立至Campaign或匯入對象以及您的電子郵件內容。 使用下列連結了解如何：

* 在Campaign中設計電子郵件
   [!DNL :arrow_upper_right:] [了解如何設計電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* 匯入電子郵件內容
   [!DNL :arrow_upper_right:] [使用案例：建立工作流程以載入傳遞內容](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* 建立和使用電子郵件範本
   [!DNL :arrow_upper_right:] [深入了解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* 選取電子郵件的對象
   [!DNL :arrow_upper_right:] [了解如何定義目標母體](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* 驗證傳遞並傳送校樣
   [!DNL :arrow_upper_right:] [了解驗證傳送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* 添加[種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## 測試及驗證您的電子郵件

Campaign提供數種方式，可在將您的電子郵件傳送給您的對象之前，先測試及驗證您的電子郵件。

[!DNL :arrow_upper_right:] [套用Campaign Classicv7檔案中列出的最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

您可以：

* 檢查傳遞分析記錄
* 傳送校樣
* 新增種子地址
* 使用控制組
* 檢查電子郵件呈現

[!DNL :arrow_upper_right:] [進一步了解Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## 監視您的電子郵件

傳送後，在「傳送控制面板」中檢查您的傳送狀態，並存取傳送記錄檔和報表，確認訊息已正確傳送。

[!DNL :arrow_upper_right:] [進一步了解Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

