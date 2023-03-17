---
title: Campaign電子郵件通道設定
description: Campaign電子郵件通道設定
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 8%

---

# Campaign電子郵件通道設定

## 電子郵件密件副本 {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件副本。

Adobe Campaign本身不會管理封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用的BCC（盲文副本）電子郵件地址，以便使用外部系統處理和封存訊息。 然後，與已傳送電子郵件對應的.eml檔案可以傳輸至遠端伺服器，例如SMTP電子郵件伺服器。

>[!CAUTION]
>
>基於隱私理由，BCC電子郵件必須由能夠安全地儲存個人識別資訊(PII)的封存系統處理。

封存目的地是您選擇的密件副本電子郵件地址，傳送收件者將看不到該地址。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support){target="_blank"} 傳送要用於封存的密件副本電子郵件地址。

定義BCC電子郵件地址後，您必須在傳送層級啟用專用選項。

>[!CAUTION]
>
>建立新的傳遞或傳遞範本時， **[!UICONTROL Email BCC]** 預設不啟用。 您必須在電子郵件傳遞或傳遞範本中手動啟用。


要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**，或 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 選取您選擇的傳送或複製現成可用的 **[!UICONTROL Email delivery]** 範本，然後選取複製的範本。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 選取 **[!UICONTROL Delivery]** 索引標籤。
1. 核取 **[!UICONTROL Email BCC]** 選項。

   ![](assets/email-bcc.png)

1. 選取 **[!UICONTROL Ok]**。

根據此範本，每次傳送的所有已傳送訊息副本都會傳送至已設定的電子郵件密件副本地址。

請注意下列特點和建議：

* 您只能使用一個密件副本電子郵件地址。

* 請確定密件副本地址有足夠的接收容量，以封存所有已傳送的電子郵件。

* 電子郵件密件副本 <!--with Enhanced MTA--> 在傳送給收件者之前會先傳送至密件副本電子郵件地址，即使原始傳送可能已退信，這可能會導致傳送密件副本訊息。 如需跳出的詳細資訊，請參閱 [了解傳送故障](../send/delivery-failures.md).

* 如果開啟並點進傳送至密件副本地址的電子郵件， **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 來自傳送分析，可能會造成某些錯誤計算。

<!--Only successfully sent emails are taken in account, bounces are not.-->

**在 Campaign Classic v7 文件** 中深入瞭解

* [選擇電子郵件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [選擇字元編碼](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [設定退信電子郵件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

* [使用電子郵件傳遞範本](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hant){target="_blank"}

* [瞭解傳遞失敗](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}
