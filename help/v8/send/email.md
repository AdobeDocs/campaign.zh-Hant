---
title: 使用Adobe Campaign傳送電子郵件
description: 開始使用 Adobe Campaign 中的電子郵件。向目標族群寄送個人化電子郵件。
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 500de76853772313b1aac655da2f1b3562de2c55
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 9%

---

# 設計和傳送電子郵件

電子郵件傳遞可讓您傳送個人化電子郵件給目標群體。 [了解更多](../send/send.md)

## 建立您的第一個電子郵件傳遞

建立與客戶其他體驗相一致的個人化和內容相關的電子郵件。

![](assets/new-email-content.png)


在下列範例中，您將瞭解在Adobe Campaign中設計電子郵件傳送的步驟，該傳送包含個人化資料、外部URL的連結和映象頁面的連結。

1. **建立傳遞**

   若要建立新傳送，請瀏覽至 **行銷活動** 標籤，按一下 **傳遞** 並按一下 **建立** 按鈕來標籤現有傳遞清單。

   ![](assets/delivery_step_1.png)

1. **選取範本**

   選取傳遞範本，然後為您的傳遞命名。 此名稱僅對Adobe Campaign主控台的使用者可見，不會對您的收件者可見，不過此標題將顯示在傳送清單中。 按一下&#x200B;**[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **匯入您的內容**

   按一下 **來源** 標籤貼上您的HTML內容。

   ![](assets/paste-content.png)


1. **個人化您的訊息**

   * 新增收件者的名字和姓氏

     若要在訊息內容中插入目標設定檔的名字和姓氏，請將游標置於您要插入的位置，然後按一下工具列中的最後一個圖示，然後按一下 **[!UICONTROL Include]** 並選取 **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     瀏覽到預覽索引標籤，透過選取收件者來檢查個人化。

     ![](assets/perso-check.png)

     進一步瞭解中的個人化選項 [本節](personalize.md).

   * 插入追蹤連結

     若要透過影像或文字將傳遞收件者帶往外部地址，請選取該地址，然後按一下 **[!UICONTROL Add a link]** 圖示加以檢視。

     在中輸入連結的URL **URL** 欄位，格式如下 **https://www.myURL.com**，然後確認。

     ![](assets/add-a-link.png)

   * 新增映象頁面

     若要允許收件者在網頁瀏覽器中檢視您的傳遞內容，請新增連結至 [映象頁面](mirror-page.md) 訊息的。

     將游標放在您要插入此連結的位置，然後按一下工具列中的最後一個圖示，然後按一下 **[!UICONTROL Include]** 並選取 **[!UICONTROL link to mirror page]**.

     在中進一步瞭解管理映象頁面 [本節](mirror-page.md#link-to-mirror-page).

1. 您可以為電子郵件定義其他引數，例如傳送訊息副本至BBC地址、變更訊息格式、設定特定編碼等。 若要了解詳細資訊，請參閱[本章節](email-parameters.md)。

1. 內容準備就緒後，按一下 **儲存**：此資訊現在會顯示在您的傳送清單中，位於 **[!UICONTROL Campaigns > Deliveries]** 標籤。

您的第一封電子郵件已準備就緒。 您現在需要定義對象、驗證傳遞並傳送。

在此瞭解如何匯入電子郵件內容 [使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

請在下列章節中進一步瞭解：

<!--[Design an email in Campaign]-->
* [建立和使用電子郵件範本](../send/create-templates.md)
* [選取電子郵件的對象](../audiences/gs-audiences.md)
* [驗證傳遞並傳送證明](preview-and-proof.md)
* [設定並傳送傳遞](configure-and-send.md)

## 測試及驗證您的電子郵件

Campaign提供數種方式，可在將電子郵件傳送給對象之前測試和驗證電子郵件。 瞭解如何在中預覽和測試您的電子郵件內容 [本節](../send/preview-and-proof.md).

您可以：

* [傳送校樣](preview-and-proof.md)
* [新增種子地址](../audiences/test-profiles.md)
* [檢查傳遞分析記錄](delivery-analysis.md)

