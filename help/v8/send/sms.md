---
title: 向Adobe Campaign發送簡訊
description: 在活動中開始使用SMS
feature: SMS
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 4%

---

# 建立和發送SMS

使用Adobe Campaign發送個性化的SMS消息。

![](../assets/do-not-localize/book.png) 瞭解如何開始使用中的SMS通道 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;

>[!NOTE]
>
>Adobe Campaign還允許你通過其 **Adobe Campaign移動應用頻道(NMAC)** 的雙曲餘切值。 瞭解詳情 [此部分](push.md)。

## 設定簡訊頻道

要發送到行動電話，您需要：

* 指定連接器和消息類型的外部帳戶。

* 引用此外部帳戶的交貨模板。

![](../assets/do-not-localize/book.png)  瞭解如何在中配置SMS通道 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;

開始發送SMS之前：

* 確保收件人的個人資料中至少包含一部手機。
* 回顧Adobe Campaign Classic [提供最佳做法](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;}，它也適用於市場活動v8。

此外，您需要熟悉SMS協定和設定。 瀏覽Adobe Campaign與SMPP提供商之間在 [此文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

## 建立您的第一個SMS傳遞

1. 要建立新交貨，請瀏覽至 **[!UICONTROL Campaigns]** 按鈕 **[!UICONTROL Deliveries]** 並按一下 **[!UICONTROL Create]** 按鈕。

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) 有關如何建立交貨的全局資訊，請參閱 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

1. 選擇引用相關外部帳戶的傳遞模板以發送SMS傳遞。

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) 瞭解如何在中建立SMPP外部帳戶 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;

   ![](../assets/do-not-localize/book.png) 瞭解如何建立交付模板以交付給 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;

1. 使用標籤、代碼和說明標識您的交貨。

1. 按一下 **[!UICONTROL Continue]** 確認並顯示消息配置窗口。

1. 在 **[!UICONTROL Text content]** 的子菜單。

   ![](assets/sms-content.png)

1. 選擇目標人口。

建立和設計SMS的關鍵步驟詳見Campaign Classicv7文檔：

* 建立簡訊

   ![](../assets/do-not-localize/book.png) [瞭解如何建立SMS傳遞](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;

* 設計SMS內容

   ![](../assets/do-not-localize/book.png) [瞭解如何定義SMS內容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;

* 選擇電子郵件的受眾

   ![](../assets/do-not-localize/book.png) [瞭解如何定義目標人口](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;

![](../assets/do-not-localize/glass.png) 定義受眾的步驟詳述於 [此頁](../start/audiences.md)。

## Test您的SMS

要查看消息的個性化呈現，請按一下 **[!UICONTROL Preview]** 選擇收件人。

![](assets/sms-preview.png)

要發送證據，請參閱第v7Campaign Classic文檔的以下部分：

* 驗證交貨併發送校樣
   ![](../assets/do-not-localize/book.png) [瞭解驗證交付的關鍵步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;
* 新增種子地址
   ![](../assets/do-not-localize/book.png) [瞭解種子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;

## 發送和監視SMS遞送

Campaign Classicv7文檔中詳細介紹了發送和監視SMS的關鍵步驟：

* 發送、監視和跟蹤SMS遞送

   ![](../assets/do-not-localize/book.png) [瞭解發送、監控和跟蹤SMS的工具。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;

* 排除簡訊遞送故障

   ![](../assets/do-not-localize/book.png) [瞭解SMS故障排除](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;
