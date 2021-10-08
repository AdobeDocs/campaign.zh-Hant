---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign中的簡訊
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---

# 建立和傳送簡訊

使用Adobe Campaign傳送個人化SMS訊息。

![](../assets/do-not-localize/book.png) 在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}中了解如何開始使用SMS通道

>[!NOTE]
>
>Adobe Campaign也可讓您透過其&#x200B;**Adobe Campaign行動應用程式頻道(NMAC)**&#x200B;選項，在行動裝置上提交推播通知。 進一步了解[本節](push.md)。

## 設定簡訊頻道

若要傳送至行動電話，您需要：

* 指定連接器和訊息類型的外部帳戶。

* 參考此外部帳戶的傳遞範本。

![](../assets/do-not-localize/book.png)  了解如何在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}中設定SMS通道

開始傳送簡訊之前：

* 請確定收件者設定檔中至少包含行動電話。
* 檢閱也適用於Campaign v8的Adobe Campaign Classic [傳送最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

此外，您還需熟悉SMS通訊協定和設定。 逐步了解Adobe Campaign與[本檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}中SMPP提供者之間所設定的連線。

## 建立您的第一個SMS傳送

1. 若要建立新傳送，請瀏覽至&#x200B;**[!UICONTROL Campaigns]**&#x200B;標籤，按一下&#x200B;**[!UICONTROL Deliveries]**，然後按一下現有傳送清單上方的&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) 如需如何建立傳送的全域資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

1. 選取參考相關外部帳戶的傳遞範本以傳送SMS傳遞。

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}中建立SMPP外部帳戶

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}中了解如何建立傳送範本以傳送至行動裝置

1. 使用標籤、程式碼和說明來識別您的傳送。

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以確認並顯示訊息設定視窗。

1. 在精靈的&#x200B;**[!UICONTROL Text content]**&#x200B;區段中輸入訊息內容，包括視需要的個人化欄位。

   ![](assets/sms-content.png)

1. 選取目標母體。

建立和設計SMS的關鍵步驟在Campaign Classicv7檔案中詳細說明：

* 建立簡訊

   ![](../assets/do-not-localize/book.png) [了解如何建立SMS傳送](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* 設計SMS內容

   ![](../assets/do-not-localize/book.png) [了解如何定義SMS內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* 選取電子郵件的對象

   ![](../assets/do-not-localize/book.png) [了解如何定義目標母體](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) 定義對象的步驟在本頁面 [詳細說明](../start/audiences.md)。

## 測試您的SMS

若要檢視呈現包含個人化訊息的訊息，請按一下&#x200B;**[!UICONTROL Preview]**&#x200B;並選取收件者。

![](assets/sms-preview.png)

若要傳送校樣，請參閱Campaign Classicv7檔案的以下章節：

* 驗證傳遞並傳送校樣
   ![](../assets/do-not-localize/book.png) [了解驗證傳送](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}的關鍵步驟
* 新增種子地址
   ![](../assets/do-not-localize/book.png) [了解種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## 傳送及監控SMS傳送

傳送及監控SMS的關鍵步驟在Campaign Classicv7檔案中詳細說明：

* 傳送、監視及追蹤SMS傳遞

   ![](../assets/do-not-localize/book.png) [了解傳送、監視及追蹤SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}的工具

* 疑難排解SMS傳送

   ![](../assets/do-not-localize/book.png) [了解SMS疑難排解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
