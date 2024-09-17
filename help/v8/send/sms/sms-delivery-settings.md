---
title: 簡訊傳送設定
description: 瞭解如何設定簡訊傳遞
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="有限可用性" type="Informative"
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: 8dffc24ff859ded70ea9c5b9ede39512c1543e74
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 1%

---

# 簡訊傳送設定 {#sms-settings}

>[!IMPORTANT]
>
>本檔案適用於Adobe Campaign v8.7.2和更新版本。
>
>若為舊版，請閱讀[Campaign Classicv7檔案](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up)。

簡訊傳送所需的技術設定如下：

* 路由： [SMPP外部帳戶](smpp-external-account.md#smpp-connection-settings)

* [此 ](#sms-tab)

您可以在傳送範本中設定所有這些專案，以避免針對每個SMS傳送建立進行設定。

## 設定&#x200B;**[!UICONTROL SMS]**&#x200B;索引標籤 {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

以下是填寫此表單所需的資訊。 每個欄位的說明如下：

* **[!UICONTROL Sender address]**

  此欄位為選用。 它允許覆寫寄件者地址(oADC)。 此欄位的內容置於SUBMIT_SM PDU的&#x200B;*source_addr*&#x200B;欄位中。

  根據SMPP規格，欄位限製為21個字元，但某些提供者可能允許較長的值。 另請注意，某些國家/地區可能會套用非常嚴格的限制（長度、內容、允許的字元……），因此您可能需要再次檢查您在此處放置的內容是否合法。 使用個人化欄位時請格外小心。

  如果此欄位留空，將改用外部帳戶中定義的Source編號欄位的值。 如果兩個值都為空，*source_addr*&#x200B;欄位將會留空。

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >不建議使用此功能。 選用的SMPP引數可提供更具彈性的實作。
  >
  >這兩項功能無法同時使用。

  結合相符的外部帳戶設定，允許隨每個MT傳送一個可選引數。 此欄位會定義TLV的值部分。

* **[!UICONTROL Transmission mode]**

  此欄位會指出您要傳輸的SMS型別：一般或快閃訊息，儲存在行動裝置或SIM卡上。 此設定會在SUBMIT_SM PDU的dest_addr_subunit選擇性欄位中傳輸。

   * **Flash**&#x200B;將值設為1。 它會傳送快閃訊息，該訊息會在行動裝置上彈出，且不會儲存在記憶體中。
   * **Normal**&#x200B;將值設為0。 它會傳送一般訊息。
   * **在行動裝置上儲存**&#x200B;將值設為2。 它會告訴手機將簡訊儲存在內部記憶體中。
   * **儲存於終端機**&#x200B;會將值設為3。 它會告訴手機將簡訊儲存在SIM卡中。

* **[!UICONTROL Priority, Communication type]**

  擴展SMPP聯結器會忽略這些欄位。

* **[!UICONTROL Maximum number of SMS per message]**

  此設定僅在訊息裝載設定停用時才有效（如需詳細資訊，請參閱外部帳戶設定中的）。 如果訊息需要的SMS數量超過此值，則會觸發錯誤。

  SMS通訊協定將SMS限製為255個部分，但有些行動電話無法拼合長度超過10個部分左右的訊息（此限制取決於確切型號）。 如果您希望安全，請勿逾越每則訊息5個部分。

  由於個人化訊息在Adobe Campaign中的運作方式，訊息的大小可能有所不同，因此傳送大量超長訊息可能會大幅增加傳送成本：將此設定為合理的值有助於控制這些成本。

  指定0會停用限制。

* **[!UICONTROL Optional SMPP parameters (TLV)]**
您可以指定額外的欄位，以作為選用的SMPP引數(TLV)傳送。 這些額外的欄位會與每個MT一併傳送，而個人化欄位可讓每個MT有不同的值。
此表格列出要隨每則訊息傳送的選用引數。 欄包含下列資訊：
   * **標籤**：這是選用的自由格式標籤。 不會傳輸給提供者。 您可以提供引數的文字說明。
   * **標籤**：標籤值，以十進位格式(例如12345)或具有0x首碼的十六進位（例如0x12ab）。 標籤可介於0到65535之間。 向SMPP服務提供者詢問他們支援的標籤。
   * **值**：要傳入選用引數的值。 此為個人化欄位。
   * **格式**：用於引數的編碼。 您可以選取任何支援的文字編碼或最常見的二進位格式。 向SMPP服務提供者詢問所需的格式。
   * **最大長度**：此引數的最大位元組數。 由於二進位欄位的大小固定，因此二進位欄位會忽略此項。

* **[!UICONTROL Using binary formats for TLV]**

  Campaign支援以二進位格式傳送TLV。 二進位檔僅限於傳送數字。

  由於個人化欄位一律會輸出文字，因此個人化欄位必須包含數字的十進位表示法（任何字串只要只包含數字就沒問題）。 值可以同時為已簽署和未簽署，個人化引擎只會將其轉換為正確的二進位表示法。

  使用二進位格式時，特殊值「 」（空字串）、「null」和「undefined」會完全停用欄位，而不會擲回錯誤。 在這三種特殊情況下，完全不會傳遞標籤。 這允許在個人化欄位中使用精心編制的Javascript時，僅針對某些訊息傳遞特定的TLV。

  >[!NOTE]
  >
  >二進位格式一律會編碼為big-endian格式。

## 建立簡訊傳遞 {#sms-delivery}

若要建立新的SMS傳送，請遵循下列步驟：

1. 例如，從&#x200B;**[!UICONTROL Explorer]**&#x200B;的傳遞儀表板或傳遞資料夾中建立新的傳遞。  預設會標示為「電子郵件傳送」。

1. 選取您為SMS傳送建立的傳送範本。 [如需更多詳情，請參閱此處](sms-mid-sourcing.md#sms-delivery-template)。

   ![](assets/sms_create.png){zoomable="yes"}

<!-- * For standalone instance,  [learn more here](sms-standalone-instance.md#sms-delivery-template).
* For mid-sourcing infrastructure, -->

1. 在&#x200B;**[!UICONTROL Label]**&#x200B;欄位中重新命名您的傳遞，並視需要在&#x200B;**[!UICONTROL Delivery code]**&#x200B;欄位和&#x200B;**[!UICONTROL Nature]**&#x200B;清單中新增資訊，以進行追蹤。 您也可以新增&#x200B;**[!UICONTROL Description]**&#x200B;至您的傳遞。

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;按鈕。 現在，您的傳送中已有範本的所有設定。

1. 您可以簽入&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕，確認所有專案都已視需要設定。 [進一步瞭解SMS索引標籤](#sms-tab)

![](assets/sms_settings.png){zoomable="yes"}

您現在可以設定您的[簡訊內容](sms-content.md)。
