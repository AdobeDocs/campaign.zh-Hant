---
title: 獨立執行個體中的SMS
description: 瞭解如何在獨立執行個體中設定簡訊傳遞
feature: SMS
role: User
hide: true
hidefromtoc: true
level: Beginner, Intermediate
badge: label="有限可用性" type="Informative"
source-git-commit: 6926d84576df1810b511ef1a9976593cb99585bb
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---


# 獨立執行個體中的SMS {#sms-standalone}

>[!IMPORTANT]
>
>本檔案適用於Adobe Campaign v8.7.2和更新版本。
>
>若為舊版，請閱讀[Campaign Classicv7檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up)。

在獨立執行個體中，傳送SMS傳送需要：

1. 指定聯結器和訊息型別的&#x200B;**外部帳戶**，[在這裡瞭解更多](#external-account)

1. 參考此外部帳戶的&#x200B;**傳遞範本**，[在這裡瞭解更多](#sms-delivery-template)

## 建立外部帳戶 {#external-account}

>[!IMPORTANT]
>
>對多個外部SMS帳戶使用相同的帳戶和密碼可能會導致帳戶之間的衝突和重疊。 深入瞭解[簡訊疑難排解頁面](smpp-connection.md#sms-troubleshooting)。

以下是建立SMPP外部帳戶的步驟：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**&#x200B;中，按一下&#x200B;**[!UICONTROL New]**&#x200B;圖示

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. 設定外部帳戶的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**。 將帳戶型別定義為&#x200B;**[!UICONTROL Routing]**，核取&#x200B;**[!UICONTROL Enabled]**&#x200B;方塊，為通道選取&#x200B;**[!UICONTROL Mobile (SMS)]**，為傳遞模式選取&#x200B;**[!UICONTROL Bulk delivery]**。

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. 在&#x200B;**[!UICONTROL Mobile]**&#x200B;索引標籤中，將&#x200B;**[!UICONTROL Extended generic SMPP]**&#x200B;保留在&#x200B;**[!UICONTROL Connector]**&#x200B;下拉式清單中。
預設會勾選&#x200B;**[!UICONTROL Send messages through a dedicated process]**&#x200B;方塊。

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   若要設定連線，您必須填寫此表單的索引標籤。 如需詳細資訊，[進一步瞭解SMPP外部帳戶](smpp-external-account.md#smpp-connection-settings)。


## 設定傳遞範本 {#sms-delivery-template}

為了協助建立SMS傳遞，請建立SMS傳遞範本，其中會參考您的SMPP外部帳戶。

在&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;中，以滑鼠右鍵按一下現有的行動傳遞範本，然後選擇&#x200B;**[!UICONTROL Duplicate]**。

![](assets/sms_template_duplicate.png){zoomable="yes"}

變更範本的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**&#x200B;以輕鬆辨識它，然後按一下&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕。

![](assets/sms_template_name.png){zoomable="yes"}

在&#x200B;**[!UICONTROL General]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Routing]**&#x200B;中，選取您的SMPP外部帳戶。

![](assets/sms_template_routing.png){zoomable="yes"}

在&#x200B;**[!UICONTROL SMS]**&#x200B;索引標籤中，您可以將選用引數新增至範本。

![](assets/sms_template_properties.png){zoomable="yes"}

[進一步瞭解此簡訊標籤設定](sms-delivery-settings.md)。
