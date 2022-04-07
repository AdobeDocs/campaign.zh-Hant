---
title: 市場活動電子郵件通道設定
description: 市場活動電子郵件通道設定
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# 市場活動電子郵件通道設定

## 電子郵件密件抄送

您可以配置Adobe Campaign以保留從您的平台發送的電子郵件副本。

>[!NOTE]
>電子郵件密件抄送功能是可選的。 請檢查您的授權合約。

Adobe Campaign本身不管理存檔檔案。 它確實使您能夠將您選擇的消息發送到專用地址，在該地址可以使用外部系統進行處理和存檔。

為此，將與已發送電子郵件相對應的.eml檔案傳輸到遠程伺服器，如SMTP電子郵件伺服器。 存檔目標是您必須指定的密件抄送電子郵件地址（對傳遞收件人不可見）。

請注意：

* 您只能使用 **一個** 密件抄送電子郵件地址。

* 只考慮成功發送的電子郵件，不考慮回報。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 在市場活動中激活電子郵件密件抄送。 必須將您選擇的BCC電子郵件地址提供給將為您配置該地址的Adobe團隊。

配置電子郵件密件抄送後，確保在傳遞模板或通過 **電子郵件密件抄送** 的雙曲餘切值。

![](assets/email-bcc.png)


Campaign Classic v7 文件中的&#x200B;**相關主題**：


* [生成鏡像頁](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;

* [選擇電子郵件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;

* [選擇字元編碼](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;

* [設定退回電子郵件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;

* [使用電子郵件傳遞模板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hant){target=&quot;_blank&quot;

* [瞭解交付失敗](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;
