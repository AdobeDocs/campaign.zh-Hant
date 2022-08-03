---
title: 與Adobe Campaign發送電子郵件
description: 開始使用 Campaign 中的電子郵件
feature: Email
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 設計和傳送電子郵件

電子郵件遞送使您能夠向目標群體發送個性化電子郵件。

![](../assets/do-not-localize/book.png)深入瞭解 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target=&quot;_blank&quot;} 

## 建立您的第一封電子郵件

建立與客戶其他體驗相一致的個人化和內容相關的電子郵件。

![](assets/new-email-content.png)


在以下示例中，您將學習設計Adobe Campaign電子郵件傳遞的步驟，該電子郵件傳遞包含個性化資料、到外部URL的連結以及到鏡像頁面的連結。

1. **建立交貨**

   要建立新交貨，請瀏覽至 **市場活動** 按鈕 **交貨** 並按一下 **建立** 按鈕。

   ![](assets/delivery_step_1.png)

1. **選擇模板**

   選擇交貨模板，然後將交貨名稱命名。 此名稱僅對Adobe Campaign控制台的用戶可見，而不對收件人可見，但此標題將顯示在您的交貨清單中。 按一下&#x200B;**[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **導入內容**

   按一下 **源** 頁籤以貼上HTML內容。

   ![](assets/paste-content.png)


1. **個性化您的郵件**


   * 添加收件人的姓和名

      要在消息內容中插入目標配置檔案的名字和姓氏，請將游標置於要插入它們的位置，然後按一下工具欄中的最後一個表徵圖，然後按一下 **[!UICONTROL Include]** 選擇 **[!UICONTROL Greetings]**。

      ![](assets/include-greetings.png)

      瀏覽至「預覽」頁籤，通過選擇收件人來檢查個性化設定。

      ![](assets/perso-check.png)

   * 插入跟蹤的連結

      要通過影像或文本將遞送收件人帶到外部地址，請選擇它，然後按一下 **[!UICONTROL Add a link]** 的子菜單。

      在中輸入連結的URL **URL** 欄位 **https://www.myURL.com**，然後確認。

      ![](assets/add-a-link.png)

   * 添加鏡像頁

      要允許收件人在Web瀏覽器中查看您的傳遞內容，請向郵件的鏡像頁面添加連結。

      將游標置於要插入此連結的位置，然後按一下工具欄中的最後一個表徵圖，然後按一下 **[!UICONTROL Include]** 選擇 **[!UICONTROL link to mirror page]**。
   內容準備好後，按一下 **保存**:它現在將顯示在您的交貨清單中 **[!UICONTROL Campaigns > Deliveries]** 頁籤。 您的第一封電子郵件已準備就緒。 您現在需要定義受眾、驗證交付併發送。


瞭解如何在此導入電子郵件內容 [用例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)。

在以下章節中瞭解更多資訊 **Campaign Classicv7文檔**:

* 在活動中設計電子郵件
   ![](../assets/do-not-localize/book.png) [瞭解如何設計電子郵件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html){target=&quot;_blank&quot;
* 建立和使用電子郵件模板
   ![](../assets/do-not-localize/book.png) [進一步瞭解電子郵件範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target=&quot;_blank&quot;}
* 選擇電子郵件的受眾
   ![](../assets/do-not-localize/book.png) [瞭解如何定義目標人口](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;
* 驗證交貨併發送校樣
   ![](../assets/do-not-localize/book.png) [瞭解驗證交付的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;
* 添加 [種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;

## Test和驗證電子郵件

「活動」提供了多種方法來test和驗證您的電子郵件，然後再將它們發送給您的受眾。

![](../assets/do-not-localize/book.png) [應用Campaign Classicv7文檔中列出的最佳做法](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html){target=&quot;_blank&quot;

您可以：

* 檢查交貨分析日誌
* 傳送校樣
* 新增種子地址
* 使用控制組
* 檢查電子郵件呈現

![](../assets/do-not-localize/book.png)[深入瞭解 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;} 
