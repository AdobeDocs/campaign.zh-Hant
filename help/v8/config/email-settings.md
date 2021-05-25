---
solution: Campaign v8
product: Adobe Campaign
title: Campaign電子郵件通道設定
description: Campaign電子郵件通道設定
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# Campaign電子郵件通道設定

## 電子郵件密件副本

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件副本。

>[!NOTE]
>電子郵件密件副本功能為選用。 請檢查您的授權合約。

Adobe Campaign本身不會管理封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用地址，以便使用外部系統處理和封存訊息。

要執行此操作，與已傳送電子郵件對應的.eml檔案會傳輸至遠端伺服器，例如SMTP電子郵件伺服器。 封存目的地是您必須指定的密件副本電子郵件地址（不會顯示給傳送收件者）。

請注意：

* 您只能使用&#x200B;**一個**&#x200B;密件副本電子郵件地址。

* 系統只會考慮成功傳送的電子郵件，不會考慮退信。

:speech_balloon:以「受管理的Cloud Services」使用者身分，[聯絡Adobe](../start/campaign-faq.md#support)以在促銷活動中啟用電子郵件密件副本。 您選擇的密件副本電子郵件地址必須提供給Adobe團隊，由團隊為您進行配置。

設定電子郵件密件副本後，請確定已在傳送範本或透過&#x200B;**電子郵件密件副本**&#x200B;選項在傳送中啟用功能。

![](assets/email-bcc.png)


**相** 關主題Campaign Classicv7檔案：

* [使用電子郵件傳遞範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* [探索電子郵件參數](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html)
* [瞭解傳遞失敗](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
