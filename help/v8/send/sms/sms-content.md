---
title: 定義及個人化簡訊內容
description: 瞭解如何定義及個人化SMS傳送內容
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: 0ef082b49261d0d2de5a6891a4a7f0cf5aafa221
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 定義簡訊內容 {#sms-content}

若要設定SMS傳送的內容：

1. 在&#x200B;**[!UICONTROL Text content]**&#x200B;索引標籤中輸入訊息的內容。

   ![](assets/sms_content.png){zoomable="yes"}

1. 您可以插入個人化欄位（例如新增名字）或插入預先定義的個人化區塊（例如新增問候語），以個人化您的訊息。 按一下個人化按鈕以新增下列專案：

   ![](assets/sms_perso.png){zoomable="yes"}

   例如，按一下&#x200B;**[!UICONTROL Recipient]** > **[!UICONTROL First name]**&#x200B;後，SMS內容會以個人化欄位更新，如下所示：

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   在[本節](../personalize.md)中進一步瞭解Adobe Campaign中的個人化。

1. 您可以從&#x200B;**[!UICONTROL Preview]**&#x200B;索引標籤預覽傳遞內容。 若要檢查您的個人化設定，請按一下&#x200B;**[!UICONTROL Test personalization]**&#x200B;下拉式清單，然後選取收件者。

   ![](assets/sms_preview.png){zoomable="yes"}

   您可以使用個人化來檢查簡訊預覽：

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* 若使用Latin-1 (ISO-8859-1)字碼頁，SMS訊息的長度上限為160個字元。 如果訊息是以Unicode撰寫，則不可超過70個字元。 某些特殊字元可能會影響訊息長度。 如需訊息長度的詳細資訊，請參閱[簡訊字母音譯](smpp-external-account.md#smpp-channel-settings)區段。
>
>* 當出現個人化欄位或條件內容欄位時，訊息的大小會因收件者而異。 進行個人化時，必須評估訊息的長度。
>
>*當您啟動分析時，會檢查訊息的長度，並在溢位事件中顯示警告。

建立傳遞內容後，您可以[選取對象](sms-audience.md)。
