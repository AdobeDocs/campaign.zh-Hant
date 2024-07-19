---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# 建立和傳送簡訊

使用Adobe Campaign傳送個人化SMS訊息。

在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}中瞭解如何開始使用簡訊頻道

>[!NOTE]
>
>Adobe Campaign也可讓您透過其&#x200B;**Adobe Campaign行動應用程式頻道(NMAC)**&#x200B;選項，在行動裝置上提交推播通知。 若要了解詳細資訊，請參閱[本章節](push.md)。

## 設定簡訊頻道

若要傳送至行動電話，您需要：

* 指定聯結器和訊息型別的外部帳戶。

* 引用此外部帳戶的傳遞範本。

在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}中瞭解如何設定簡訊頻道

開始傳送SMS之前：

* 請確定收件者設定檔在其設定檔中至少包含一部行動電話。
* 檢閱也適用於Campaign v8的Adobe Campaign Classic [傳遞最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=zh-Hant#sending-messages){target="_blank"}。

此外，您需要熟悉SMS通訊協定和設定。 在[此檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}中逐步進行Adobe Campaign與SMPP提供者之間的連線設定。

## 建立您的第一個SMS傳遞

1. 若要建立新傳遞，請瀏覽至&#x200B;**[!UICONTROL Campaigns]**&#x200B;標籤，按一下&#x200B;**[!UICONTROL Deliveries]**&#x200B;並按一下現有傳遞清單上方的&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

   ![](assets/delivery_step_1.png)

   如需有關如何建立傳遞的全域資訊，請參閱[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}。

1. 選取參考相關外部帳戶的傳遞範本，以傳送SMS傳遞。

   ![](assets/sms-template-list.png)

   在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}中瞭解如何建立SMPP外部帳戶

   在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}中瞭解如何建立傳遞範本以傳遞至行動裝置

1. 使用標籤、程式碼和說明來識別您的傳遞。

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以確認並顯示訊息設定視窗。

1. 在精靈的&#x200B;**[!UICONTROL Text content]**&#x200B;區段中輸入訊息的內容，包括需要的個人化欄位。

   ![](assets/sms-content.png)

1. 選取目標母體。

建立和設計簡訊的關鍵步驟，在Campaign Classic v7檔案中詳細說明：

* 建立簡訊

  [瞭解如何建立SMS傳遞](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* 設計簡訊內容

  [瞭解如何定義SMS內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* 選取電子郵件的對象

  [瞭解如何定義目標母體](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

定義對象的步驟已詳載於[此頁面](../start/audiences.md)。

## 測試您的簡訊

若要檢視訊息的呈現及其個人化，請按一下&#x200B;**[!UICONTROL Preview]**&#x200B;並選取收件者。

![](assets/sms-preview.png)

若要傳送校樣，請參閱Campaign Classicv7檔案的下列章節：

* 驗證傳遞並傳送校樣
  [瞭解驗證傳遞的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target="_blank"}
* 新增種子地址
  [瞭解種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## 傳送及監控簡訊傳遞

傳送和監控SMS的關鍵步驟在Campaign Classic v7檔案中詳細說明：

* 傳送、監控和追蹤簡訊傳遞

  [瞭解傳送、監控和追蹤SMS的工具](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* 疑難排解簡訊傳遞

  [瞭解簡訊疑難排解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
