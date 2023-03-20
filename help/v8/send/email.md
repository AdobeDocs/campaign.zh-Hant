---
title: 使用Adobe Campaign傳送電子郵件
description: 開始使用 Adobe Campaign 中的電子郵件。向目標族群寄送個人化電子郵件。
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 16%

---

# 設計和傳送電子郵件

電子郵件傳送可讓您傳送個人化電子郵件給目標人口。

![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target="_blank"}

## 建立您的第一個電子郵件傳送

建立與客戶其他體驗相一致的個人化和內容相關的電子郵件。

![](assets/new-email-content.png)


在下列範例中，您將學習在Adobe Campaign中設計電子郵件傳送的步驟，其中包含個人化資料、外部URL的連結，以及鏡像頁面的連結。

1. **建立傳送**

   若要建立新傳送，請瀏覽至 **行銷活動** 按一下 **傳遞** 並按一下 **建立** 按鈕。

   ![](assets/delivery_step_1.png)

1. **選取範本**

   選取傳送範本，然後為您的傳送命名。 此名稱只會顯示給Adobe Campaign Console的使用者，而不會顯示給收件者，不過傳送清單中會顯示此標題。 按一下&#x200B;**[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **匯入您的內容**

   按一下 **來源** 標籤來貼上HTML內容。

   ![](assets/paste-content.png)


1. **個人化您的訊息**

   * 新增收件者的名字和姓氏

      若要在訊息內容中插入目標設定檔的名字和姓氏，請將游標置於您要插入設定檔的位置，然後按一下工具列中的最後一個圖示，然後按一下 **[!UICONTROL Include]** 選取 **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      瀏覽至「預覽」標籤，透過選取收件者來檢查個人化。

      ![](assets/perso-check.png)

      進一步了解中的個人化選項 [本節](personalize.md).

   * 插入追蹤連結

      若要透過影像或文字將傳送收件者帶至外部地址，請選取該收件者，然後按一下 **[!UICONTROL Add a link]** 圖示。

      在 **URL** 欄位，使用下列格式 **https://www.myURL.com**，然後確認。

      ![](assets/add-a-link.png)

   * 添加鏡像頁

      若要允許收件者在網頁瀏覽器中檢視您的傳遞內容，請新增連結至 [鏡像頁面](../send/mirror-page.md) 你的留言。

      將游標置於要插入此連結的位置，然後按一下工具欄中的最後一個表徵圖，然後按一下 **[!UICONTROL Include]** 選取 **[!UICONTROL link to mirror page]**.
   內容準備就緒後，按一下 **儲存**:它現在會顯示在您的傳送清單中， **[!UICONTROL Campaigns > Deliveries]** 標籤。 您的第一封電子郵件已就緒。 您現在需要定義對象、驗證傳送並傳送。


了解如何在此匯入電子郵件內容 [使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

深入了解 **Campaign Classicv7檔案**:

* 在Campaign中設計電子郵件
   ![](../assets/do-not-localize/book.png) [了解如何設計電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=zh-Hant){target="_blank"}
* 建立和使用電子郵件範本
   ![](../assets/do-not-localize/book.png) [深入瞭解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hant){target="_blank"}
* 選取電子郵件的對象
   ![](../assets/do-not-localize/book.png) [了解如何定義目標母體](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}
* 驗證傳遞並傳送校樣
   ![](../assets/do-not-localize/book.png) [了解驗證傳送的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target="_blank"}
* 新增 [種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## 測試及驗證您的電子郵件

Campaign提供數種方式，可在將您的電子郵件傳送給您的對象之前，先測試及驗證您的電子郵件。

![](../assets/do-not-localize/book.png) [套用Campaign Classicv7檔案中列出的最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html){target="_blank"}

您可以：

* 檢查傳遞分析記錄
* 傳送校樣
* 新增種子地址
* 使用控制組
* 檢查電子郵件呈現

![](../assets/do-not-localize/book.png) [在 Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target="_blank"}
