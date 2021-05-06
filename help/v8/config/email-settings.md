---
solution: Campaign Classic
product: campaign
title: 促銷活動電子郵件頻道設定
description: 促銷活動電子郵件頻道設定
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# 促銷活動電子郵件頻道設定

## 電子郵件密件副本

您可以設定Adobe Campaign，保留從您的平台傳送的電子郵件副本。

不過，Adobe Campaign本身並不管理已封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用位址，以便使用外部系統處理及封存。

為此，將與已發送電子郵件對應的。eml檔案傳輸到遠程伺服器，如SMTP電子郵件伺服器。 封存目標是您必須指定的密件副本電子郵件地址（對傳送收件者不可見）。

請注意：

* 您只能使用一個密件副本電子郵件地址。

* 只有成功傳送的電子郵件才會納入考量，但彈回數則不會納入考量。

在設定電子郵件密件副本後，請務必在傳送範本或透過&#x200B;**電子郵件密件副本**&#x200B;選項的傳送中啟用該功能。

:arrow_upper_right:有關詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**注意**:電子郵件密件副本功能是可選的。請檢查您的授權合約。

:speech_balloon:身為受管理的Cloud Services使用者，[請聯絡Adobe](../start/support.md#support)，以啟用促銷活動中的電子郵件密件副本。 您選擇的密件副本電子郵件地址必須提供給將為您配置的Adobe團隊。