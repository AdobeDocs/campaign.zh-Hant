---
title: 市場活動電子郵件通道設定
description: 市場活動電子郵件通道設定
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 5%

---

# 市場活動電子郵件通道設定

## 電子郵件密件副本 {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

您可以配置Adobe Campaign以保留從您的平台發送的電子郵件副本。

Adobe Campaign本身不管理存檔檔案。 它確實使您能夠將您選擇的郵件發送到專用的BCC（盲碳拷貝）電子郵件地址，在該地址，您可以使用外部系統處理和存檔這些郵件。 然後，與所發送的電子郵件相對應的.eml檔案可以傳輸到遠程伺服器，如SMTP電子郵件伺服器。

>[!CAUTION]
>
>出於隱私原因，BCC電子郵件必須由能夠安全儲存個人身份資訊(PII)的存檔系統處理。

存檔目標是您選擇的BCC電子郵件地址，它對遞送收件人來說仍是不可見的。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support){target="_blank"} 來傳遞要用於存檔的密件抄送電子郵件地址。

定義密件抄送電子郵件地址後，必須在傳遞級別啟用專用選項。

>[!CAUTION]
>
>建立新交貨或交貨模板時， **[!UICONTROL Email BCC]** 預設情況下未啟用。 您需要在電子郵件傳遞或傳遞模板中手動啟用它。


要執行此操作，請遵循下列步驟：

1. 轉到 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**&#x200B;或 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 選擇您選擇的交貨或複製現成的 **[!UICONTROL Email delivery]** ，然後選擇複製的模板。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 選取 **[!UICONTROL Delivery]** 索引標籤。
1. 核取 **[!UICONTROL Email BCC]** 選項。

   ![](assets/email-bcc.png)

1. 選取 **[!UICONTROL Ok]**。

基於此模板的每個傳遞的所有已發送郵件的副本將發送到已配置的電子郵件密件抄送地址。

注意以下具體情況和建議：

* 您只能使用一個密件抄送電子郵件地址。

* 確保BCC地址具有足夠的接收容量來存檔所有已發送的電子郵件。

* 電子郵件密件抄送 <!--with Enhanced MTA--> 在傳送給收件人之前，將其傳送至BCC電子郵件地址，這可能導致BCC郵件被發送，即使原始遞送可能已經轉發。 有關退貨的詳細資訊，請參閱 [瞭解交付失敗](../send/delivery-failures.md)。

* 如果開啟並按一下發送到密件抄送地址的電子郵件，則在 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 從發送分析中得出，這可能會導致一些錯誤計算。

<!--Only successfully sent emails are taken in account, bounces are not.-->

**了解更多**

在以下各節中：

* [使用電子郵件傳遞模板](../send/create-templates.md)

* [瞭解傳遞失敗](../send/delivery-failures.md)


在Campaign Classicv7文檔中：

* [選擇電子郵件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [選擇字元編碼](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [設定退回電子郵件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

