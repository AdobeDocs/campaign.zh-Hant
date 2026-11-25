---
title: 中間來源基礎結構中的SMS
description: 瞭解如何在中間來源基礎結構中設定簡訊傳遞
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: b5eb9eaa-0ca8-478c-9ed5-e5006e9b5609
TQID: 'https://experienceleague.adobe.com/JMj3tFG6i-bWXlEGyvFzlNpAj4fZoqZC4mdej5N3Qcw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%
---
# 中間來源基礎結構中的SMS {#sms-mid}

使用中間來源基礎結構傳送SMS傳遞需要：

1. 中間伺服器上的SMS運運算元。 [在這裡瞭解如何建立它](#sms-operator-mid)
1. 行銷伺服器上的SMS外部帳戶，將使用之前建立的運運算元。 [在這裡瞭解如何建立它](#sms-external-account)
1. 中間伺服器上的SMPP外部帳戶，指定頻道和中間來源傳遞模式。 [在這裡瞭解如何建立它](#smpp-external-account-mid)
1. 參照外部帳戶的傳遞範本以簡化傳送流程。 [在這裡瞭解如何建立它](#sms-delivery-template)

## 在中間伺服器上建立SMS運運算元 {#sms-operator-mid}

首先，您必須在中間伺服器上建立SMS運運算元，由Marketing伺服器上的SMS外部帳戶使用。

若要建立簡訊運運算元，請遵循下列步驟：

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Access management]** > **[!UICONTROL Operators]**&#x200B;中，按一下&#x200B;**[!UICONTROL New]**&#x200B;並在開啟的新視窗中填寫表單。

   * **[!UICONTROL Name (login)]**&#x200B;和&#x200B;**[!UICONTROL Label]**&#x200B;為必要專案。
   * 密碼並非強制性，但強烈建議您使用密碼以提高安全性。

   請注意，名稱（登入）稍後將用於命名中間伺服器中的SMPP外部帳戶。

   ![在中間伺服器上新增簡訊操作員表單，其名稱為（登入）、密碼和標籤，以及許可權的[新增]按鈕](assets/smsoperator_mid.png){zoomable="yes"}

1. 在&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;部分中，按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。
在開啟的新視窗上，從&#x200B;**[!UICONTROL Folder]**&#x200B;清單中選擇&#x200B;**[!UICONTROL Named rights]**，然後在右側清單中選擇&#x200B;**[!UICONTROL ADMINISTRATION]**。

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;按鈕。

   ![新增群組或已命名的許可權對話方塊，其中已選取ADMINISTRATION已命名的許可權](assets/smsoperator_rights.png){zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;按鈕，完成簡訊運運算元的建立。

   已新增![簡訊操作員表單，其管理許可權為，且[儲存]按鈕已反白顯示](assets/smsoperator_save.png){zoomable="yes"}

您現在可以在運運算元清單中看到它。

![顯示新中間簡訊運運算元(smsOperator)的運運算元清單](assets/smsoperator_list.png){zoomable="yes"}

## 在行銷伺服器上建立簡訊外部帳戶 {#sms-external-account}

在中間基礎結構中，您需要在行銷伺服器上建立簡訊外部帳戶，如下所示

>[!IMPORTANT]
>
>對多個外部SMS帳戶使用相同的帳戶和密碼可能會導致帳戶之間的衝突和重疊。 深入瞭解[簡訊疑難排解頁面](smpp-connection.md#sms-troubleshooting)。

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**&#x200B;中，按一下&#x200B;**[!UICONTROL New]**&#x200B;圖示

   在[管理] > [平台]中的![外部帳戶清單，並反白顯示[新增]圖示](assets/sms_extaccount.png){zoomable="yes"}

1. 設定外部帳戶的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**。 將帳戶型別定義為&#x200B;**[!UICONTROL Routing]**，核取&#x200B;**[!UICONTROL Enabled]**&#x200B;方塊，為通道選取&#x200B;**[!UICONTROL Mobile (SMS)]**，為傳遞模式選取&#x200B;**[!UICONTROL Mid-sourcing]**。

   ![外部帳戶一般標籤：路由型別、已啟用、行動(SMS)通道和中間來源傳遞模式](assets/mid_smsextaccount.png){zoomable="yes"}

1. 在&#x200B;**[!UICONTROL Mid-sourcing]**&#x200B;索引標籤中，使用中間來源伺服器URL和先前在中間伺服器上建立的SMS運運算元填寫表單。

   按一下&#x200B;**[!UICONTROL Test the connection]**&#x200B;按鈕以確認連線。

   ![包含伺服器URL、SMS操作員帳戶、密碼和測試連線按鈕的中間來源標籤](assets/midtab_smsextaccount.png){zoomable="yes"}

1. 按一下 **[!UICONTROL Save]**。

## 在中間伺服器上建立SMPP外部帳戶 {#smpp-external-account-mid}

>[!IMPORTANT]
>
>對多個外部SMS帳戶使用相同的帳戶和密碼可能會導致帳戶之間的衝突和重疊。 請參閱[簡訊疑難排解頁面](smpp-connection.md#sms-troubleshooting)。

目標現在是在中間伺服器上建立您的SMPP外部帳戶。

要執行此操作，請遵循下列步驟：

1. 在中間伺服器的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**&#x200B;中，按一下&#x200B;**[!UICONTROL New]**&#x200B;圖示

1. 設定外部帳戶的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**。

   >[!WARNING]
   >
   >指派內部名稱時，請務必遵循指定的命名慣例： `SMS Operator Name_Internal Name of the Marketing SMS external account`。
   >

   將帳戶型別定義為&#x200B;**[!UICONTROL Routing]**，核取&#x200B;**[!UICONTROL Enabled]**&#x200B;方塊，為通道選取&#x200B;**[!UICONTROL Mobile (SMS)]**，為傳遞模式選取&#x200B;**[!UICONTROL Bulk delivery]**。
   ![中間伺服器外部帳戶一般標籤：路由型別、已啟用、行動（簡訊）通道和大量傳送模式](assets/mid_extaccount.png){zoomable="yes"}

1. 在&#x200B;**[!UICONTROL Mobile]**&#x200B;索引標籤中，將&#x200B;**[!UICONTROL Extended generic SMPP]**&#x200B;保留在&#x200B;**[!UICONTROL Connector]**&#x200B;下拉式清單中。

   預設會勾選&#x200B;**[!UICONTROL Send messages through a dedicated process]**&#x200B;方塊。

   ![使用擴充通用SMPP聯結器的行動標籤及透過專用的程式傳送訊息已核取](assets/sms_extaccount_connector.png){zoomable="yes"}

   若要設定連線，您必須填寫此表單的索引標籤。 如需詳細資訊，[進一步瞭解SMPP外部帳戶](smpp-external-account.md#smpp-connection-settings)。

## 設定傳遞範本 {#sms-delivery-template}

為了協助建立SMS傳遞，請建立SMS傳遞範本，其中會參考您的所有設定。

在行銷伺服器上的&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;中，以滑鼠右鍵按一下現有的行動傳遞範本，然後選擇&#x200B;**[!UICONTROL Duplicate]**。

![傳遞範本清單，在行動裝置（簡訊）範本的內容功能表中已選取重複](assets/sms_template_duplicate.png){zoomable="yes"}

變更範本的&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**&#x200B;以輕鬆辨識它，然後按一下&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕。

![重複的傳遞範本，包含[標籤]和[內部名稱]欄位，以及[內容]按鈕反白顯示](assets/sms_template_name.png){zoomable="yes"}

在&#x200B;**[!UICONTROL General]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Routing]**&#x200B;中，選取您的SMPP外部帳戶。

![傳遞屬性[一般]索引標籤，[路由]欄位設為SMPP外部帳戶](assets/mid_template.png){zoomable="yes"}

在&#x200B;**[!UICONTROL SMS]**&#x200B;索引標籤中，您可以將選用引數新增至範本。

![傳遞屬性SMS索引標籤，包含一般引數和選用的SMPP引數(TLV)](assets/sms_template_properties.png){zoomable="yes"}

[進一步瞭解此簡訊標籤設定](sms-delivery-settings.md)。
