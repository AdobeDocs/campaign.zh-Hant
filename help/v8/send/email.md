---
title: 使用Adobe Campaign傳送電子郵件
description: 開始使用 Adobe Campaign 中的電子郵件。向目標群體寄送個人化電子郵件。
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: a76d2c30d3e1c723bcd4881f28980d346aade3dc
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 9%

---

# 設計和傳送電子郵件

使用Adobe Campaign建立電子郵件傳遞，以傳送個人化電子郵件給目標群體。 [了解更多](../send/send.md)

>[!NOTE]
>
>若要建立吸引人且個人訂做的電子郵件，請瀏覽至[網頁使用者介面](../start/campaign-ui.md#campaign-web-user-interface-ac-web-ui)。 Adobe Campaign隨附電子郵件Designer，這是一個直覺式的拖放介面，可讓您為每封電子郵件設計和調整所有內容。


瞭解在[此頁面](../start/create-message.md)中建立和設定傳遞的關鍵步驟。

## 建立電子郵件傳遞

建立與客戶其他體驗相一致的個人化和內容相關的電子郵件。

![](assets/new-email-content.png)


在以下範例中，您將瞭解在Adobe Campaign中設計電子郵件傳送的步驟，其中包含個人化資料、外部URL的連結和映象頁面的連結。

1. **建立傳遞**

   若要建立新傳遞，請瀏覽至&#x200B;**行銷活動**&#x200B;標籤，按一下&#x200B;**傳遞**，然後按一下現有傳遞清單上方的&#x200B;**建立**&#x200B;按鈕。

   ![](assets/delivery_step_1.png)

1. **選取範本**

   選取傳遞範本，然後為您的傳遞命名。 此名稱將僅對Adobe Campaign主控台的使用者可見，不會由您的收件者可見，不過此標題將顯示在您的傳遞清單中。 按一下&#x200B;**[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **匯入您的內容**

   按一下&#x200B;**Source**&#x200B;索引標籤，貼上您的HTML內容。

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >為避免效能問題，電子郵件中包含的影像不能超過100 KB。

1. **個人化您的訊息**

   * 新增收件者的名字和姓氏

     若要在訊息內容中插入目標設定檔的名字和姓氏，請將游標置於您要插入的位置，然後按一下工具列中的最後一個圖示，然後按一下&#x200B;**[!UICONTROL Include]**&#x200B;並選取&#x200B;**[!UICONTROL Greetings]**。

     ![](assets/include-greetings.png)

     瀏覽到預覽索引標籤，透過選取收件者來檢查個人化。

     ![](assets/perso-check.png)

     在[本節](personalize.md)中進一步瞭解個人化選項。

   * 插入追蹤連結

     若要透過影像或文字將傳遞收件者帶往外部地址，請選取該地址，然後按一下工具列中的&#x200B;**[!UICONTROL Add a link]**&#x200B;圖示。

     在&#x200B;**URL**&#x200B;欄位中，使用以下格式&#x200B;**https://www.myURL.com**&#x200B;輸入連結的URL，然後確認。

     ![](assets/add-a-link.png)

   * 新增映象頁面

     若要允許收件者在網頁瀏覽器中檢視您的傳遞內容，請新增郵件之[映象頁面](mirror-page.md)的連結。

     將游標放在您要插入此連結的位置，然後按一下工具列中的最後一個圖示，然後按一下&#x200B;**[!UICONTROL Include]**&#x200B;並選取&#x200B;**[!UICONTROL link to mirror page]**。

     在[本節](mirror-page.md#link-to-mirror-page)中進一步瞭解管理映象頁面。

1. 您可以為電子郵件定義其他引數，例如傳送訊息副本至BBC地址、變更訊息格式、設定特定編碼等。 若要了解詳細資訊，請參閱[本章節](email-parameters.md)。

1. 內容準備就緒後，請按一下&#x200B;**儲存**：內容現在會顯示在&#x200B;**[!UICONTROL Campaigns > Deliveries]**&#x200B;索引標籤的傳遞清單中。

您的第一封電子郵件已準備就緒。 您現在需要定義對象、驗證傳遞並傳送。

瞭解如何在此[使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}中建立工作流程以匯入電子郵件內容。

>[!MORELIKETHIS]
>
>* [建立傳遞](../start/create-message.md)
>* [建立並使用電子郵件範本](create-templates.md)
>* [選取您電子郵件的對象](../audiences/gs-audiences.md)
>* [驗證傳遞並傳送證明](preview-and-proof.md)
>* [設定並傳送傳遞](configure-and-send.md)
>* [傳遞最佳實務](../start/delivery-best-practices.md)

## 測試及驗證您的電子郵件

Campaign提供數種方式，可在將電子郵件傳送給受眾之前測試和驗證電子郵件。 在[本節](../send/preview-and-proof.md)中瞭解如何預覽和測試您的電子郵件內容。

您可以：

* [傳送校樣](preview-and-proof.md)
* [新增種子地址](../audiences/test-profiles.md)
* [檢查傳遞分析記錄](delivery-analysis.md)

