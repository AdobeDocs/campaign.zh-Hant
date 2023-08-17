---
title: Campaign電子郵件通道設定
description: Campaign電子郵件通道設定
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 5%

---

# Campaign電子郵件通道設定

## 電子郵件密件副本 {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件副本。

Adobe Campaign本身不會管理封存的檔案。 它可讓您選擇將訊息傳送至專用的密件副本（密件副本）電子郵件地址，您可在其中使用外部系統處理和封存。 與已傳送電子郵件相對應的.eml檔案可接著傳輸至遠端伺服器，例如SMTP電子郵件伺服器。

>[!CAUTION]
>
>基於隱私權理由，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。

封存目的地是您選擇的密件副本電子郵件地址，傳遞收件者將看不到該地址。

![](../assets/do-not-localize/speech.png)  作為「受管理的Cloud Service」使用者， [連絡人Adobe](../start/campaign-faq.md#support){target="_blank"} 以傳達要用於封存的密件副本電子郵件地址。

定義密件副本電子郵件地址後，您必須在傳送層級啟用專用選項。

>[!CAUTION]
>
>建立新的傳遞或傳遞範本時， **[!UICONTROL Email BCC]** 預設為未啟用。 您必須在電子郵件傳遞或傳遞範本中手動啟用。


要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**，或 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 選取您選擇的傳遞或複製現成可用的傳遞內容 **[!UICONTROL Email delivery]** 範本，然後選取複製的範本。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 選取 **[!UICONTROL Delivery]** 索引標籤。
1. 核取 **[!UICONTROL Email BCC]** 選項。

   ![](assets/email-bcc.png)

1. 選取 **[!UICONTROL Ok]**。

系統會根據此範本，將每次傳遞的所有已傳送訊息復本傳送至已設定的電子郵件密件副本地址。

請注意下列特殊性和建議：

* 您只能使用一個密件副本電子郵件地址。

* 請確定密件副本位址有足夠的接收容量來封存所有傳送的電子郵件。

* 電子郵件密件副本 <!--with Enhanced MTA--> 會在傳遞給收件者之前傳遞給密件副本電子郵件地址，這會導致即使原始傳遞可能已跳出，仍會傳送密件副本訊息。 如需退信的詳細資訊，請參閱 [瞭解傳遞失敗](../send/delivery-failures.md).

* 如果傳送至密件副本地址的電子郵件被開啟並按過，這將在中列入考慮 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 傳送分析，這可能會造成一些計算錯誤。

<!--Only successfully sent emails are taken in account, bounces are not.-->

**了解更多**

在以下小節中：

* [使用電子郵件傳遞範本](../send/create-templates.md)

* [瞭解傳遞失敗](../send/delivery-failures.md)


在Campaign Classic v7檔案中：

* [選取電子郵件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [選取字元編碼](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [設定退信電子郵件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

