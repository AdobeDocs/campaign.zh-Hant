---
product: Adobe Campaign
title: 使用Adobe Campaign傳送電子郵件
description: 開始使用Campaign中的電子郵件
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 9%

---

# 設計和傳送電子郵件

電子郵件傳送可讓您傳送個人化電子郵件給目標人口。

↗️了解更多[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html)。

## 建立您的第一個電子郵件傳送

建立與客戶體驗其餘部分一致的個人化和情境相關電子郵件。

![](assets/new-email-content.png)


在下列範例中，您將學習在Adobe Campaign中設計電子郵件傳送的步驟，其中包含個人化資料、外部URL的連結，以及鏡像頁面的連結。

1. **建立傳送**

   若要建立新傳送，請瀏覽至&#x200B;**Campaigns**&#x200B;標籤，按一下&#x200B;**Delives**，然後按一下現有傳送清單上方的&#x200B;**Create**&#x200B;按鈕。

   ![](assets/delivery_step_1.png)

1. **選取範本**

   選取傳送範本，然後為您的傳送命名。 此名稱只會顯示給Adobe Campaign Console的使用者，而不會顯示給收件者，不過傳送清單中會顯示此標題。 按一下&#x200B;**[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **匯入您的內容**

   按一下&#x200B;**Source**&#x200B;標籤以貼上您的HTML內容。

   ![](assets/paste-content.png)


1. **個人化您的訊息**


   * 新增收件者的名字和姓氏

      要在消息內容中插入目標配置檔案的名字和姓氏，請將游標放在要插入它們的位置，然後按一下工具欄中的最後一個表徵圖，然後按一下&#x200B;**[!UICONTROL Include]**&#x200B;並選擇&#x200B;**[!UICONTROL Greetings]**。

      ![](assets/include-greetings.png)

      瀏覽至「預覽」標籤，透過選取收件者來檢查個人化。

      ![](assets/perso-check.png)

   * 插入追蹤連結

      若要透過影像或文字將傳送收件者帶至外部地址，請選取該收件者，然後按一下工具列中的&#x200B;**[!UICONTROL Add a link]**&#x200B;圖示。

      在&#x200B;**URL**&#x200B;欄位中輸入連結的URL，使用下列格式&#x200B;**https://www.myURL.com**，然後確認。

      ![](assets/add-a-link.png)

   * 添加鏡像頁

      若要允許收件者在網頁瀏覽器中檢視您的傳遞內容，請新增連結至訊息的鏡像頁面。

      將游標置於要插入此連結的位置，然後按一下工具欄中的最後一個表徵圖，然後按一下&#x200B;**[!UICONTROL Include]**&#x200B;並選擇&#x200B;**[!UICONTROL link to mirror page]**。
   內容準備就緒後，按一下「**儲存**」：它現在會顯示在您的傳送清單中，位於&#x200B;**[!UICONTROL Campaigns > Deliveries]**&#x200B;標籤中。 您的第一封電子郵件已就緒。 您現在需要定義對象、驗證傳送並傳送。


如需詳細資訊，請參閱Campaign Classicv7檔案的以下章節：

* 在Campaign中設計電子郵件
↗️ [了解如何設計電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* 匯入電子郵件內容
↗️ [使用案例：建立工作流程以載入傳送內容](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* 建立和使用電子郵件範本
↗️ [進一步了解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* 選取電子郵件的對象
↗️ [了解如何定義目標母體](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* 驗證傳遞並傳送校樣
↗️ [了解驗證傳送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* 添加[種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## 測試及驗證您的電子郵件

Campaign提供數種方式，可在將您的電子郵件傳送給您的對象之前，先測試及驗證您的電子郵件。

↗️ [套用Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)中列出的最佳實務

您可以：

* 檢查傳遞分析記錄
* 傳送校樣
* 新增種子地址
* 使用控制組
* 檢查電子郵件呈現

↗️ [在 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html) 中深入瞭解

## 監視您的電子郵件

傳送後，在「傳送控制面板」中檢查您的傳送狀態，並存取傳送記錄檔和報表，以確認訊息已正確傳送。

↗️ [在 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html) 中深入瞭解

