---
title: Adobe Campaign中的電子郵件引數
description: 瞭解Adobe Campaign中專用於電子郵件傳送的選項和設定。
feature: Email
role: User
level: Beginner, Intermediate, Experienced
source-git-commit: 44f30f753e3ed75b7e56caf7bd8cdfa7cbee5c35
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 8%

---

# 電子郵件參數 {#email-parameters}

本節介紹專屬於電子郵件傳送的傳送屬性中可用的選項和引數。

## 使用電子郵件密件副本 {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件復本。

Adobe Campaign本身不會管理封存的檔案。 它可讓您將您選擇的訊息傳送至專用的密件副本（密件副本）電子郵件地址，您可使用外部系統從此處處理和封存。 與已傳送電子郵件相對應的.eml檔案可以傳送到遠端伺服器，例如SMTP電子郵件伺服器。

>[!CAUTION]
>
>基於隱私權考量，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。

封存目的地是您選擇的密件副本電子郵件地址，傳遞收件者將看不到該地址。

![](../assets/do-not-localize/speech.png)  身為Managed Cloud Services使用者， [連絡人Adobe](../start/campaign-faq.md#support){target="_blank"} 傳達要用於封存的密件副本電子郵件地址。

定義密件副本電子郵件地址後，您必須在傳送層級啟用專用選項。

>[!CAUTION]
>
>**[!UICONTROL Email BCC]** 預設為未啟用。 您必須在電子郵件傳遞或傳遞範本中手動啟用。

要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**，或 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 選取您選擇的傳遞專案或複製現成可用的傳遞專案 **[!UICONTROL Email delivery]** 範本，然後選取複製的範本。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 選取 **[!UICONTROL Delivery]** 索引標籤。
1. 核取 **[!UICONTROL Email BCC]** 選項。

   ![](assets/email-bcc.png)

1. 選取 **[!UICONTROL Ok]**。

系統會根據此範本，將每次傳遞的所有已傳送訊息副本傳送至已設定的電子郵件密件副本地址。

請注意下列具體細節和建議：

* 您只能使用一個密件副本電子郵件地址。

* 請確定密件副本位址有足夠的接收容量，可封存所有已傳送的電子郵件。

* 電子郵件密件副本 <!--with Enhanced MTA--> 會在傳遞給收件者之前傳遞給密件副本電子郵件地址，這可能會導致即使原始傳遞可能已跳出，仍會傳送密件副本訊息。 如需退信的詳細資訊，請參閱 [瞭解傳遞失敗](delivery-failures.md).

* 如果傳送至密件副本地址的電子郵件被開啟並按過，這將會在 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 傳送分析，這可能會導致某些計算錯誤。

<!--Only successfully sent emails are taken in account, bounces are not.-->

## 選取訊息格式 {#selecting-message-formats}

您可以變更已傳送電子郵件訊息的格式。 若要這麼做，請編輯傳送屬性，然後按一下 **[!UICONTROL Delivery]** 標籤。

![](assets/email-message-format.png)

在視窗的下半部分選取電子郵件的格式：

* **[!UICONTROL Use recipient preferences]** （預設模式）

  訊息格式會根據儲存在收件者設定檔中的資料定義，並預設會儲存在 **[!UICONTROL email format]** 欄位(@emailFormat)。 如果收件者希望以特定格式接收郵件，則此格式為傳送的格式。如果未填入欄位，則會傳送替代的多重部分訊息（請參閱下文）。

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  訊息包含兩種格式：文字和HTML。 接收時顯示的格式取決於收件者的郵件軟體設定（替代的多重部分）。

  >[!IMPORTANT]
  >
  >此選項包含檔案的兩個版本。 因此，它會減少傳遞輸送量，因為訊息大小較大。

* **[!UICONTROL Send all messages in text format]**

  訊息會以文字格式傳送。 不會傳送HTML格式，但只有當收件者按一下郵件時，才會用於映象頁面。

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## 設定字元編碼 {#character-encoding}

在 **[!UICONTROL SMTP]** 標籤中， **[!UICONTROL Character encoding]** 區段可讓您設定特定編碼。

預設編碼為UTF-8。 如果部分收件者的電子郵件提供者不支援UTF-8標準編碼，您可能想要設定特定編碼，以正確向電子郵件的收件者顯示特殊字元。

例如，您想要傳送包含日文字元的電子郵件。 為確保所有字元都能正確顯示給在日本的收件者，您可能想要使用可支援日文字元的編碼，而不是標準UTF-8。

若要這麼做，請選取 **[!UICONTROL Force the encoding used for messages]** 中的選項 **[!UICONTROL Character encoding]** 區段，然後從顯示的下拉式清單中選擇編碼。

![](assets/email-smtp-encoding.png)

## 管理退信電子郵件 {#managing-bounce-emails}

此 **[!UICONTROL SMTP]** 傳遞屬性的索引標籤也可讓您設定退回郵件的管理。

* **[!UICONTROL Errors-to-address]**：依預設，會在平台的預設錯誤方塊中接收跳出的電子郵件，但您可以定義傳送的特定錯誤地址。

* **[!UICONTROL Bounce address]**：您也可以定義另一個地址，未處理的退回電子郵件將轉寄至該地址。 此位址可讓您在應用程式無法自動限定電子郵件時調查退回的原因。

每個欄位都可以使用專用圖示進行個人化。 進一步瞭解中的個人化欄位 [本節](personalization-fields.md).

![](assets/email-smtp-bounce.png)

有關退回郵件管理的詳細資訊，請參閱 [本節](delivery-failures.md#bounce-mail-management).

## 新增SMTP標頭 {#adding-smtp-headers}

您可以將SMTP標頭新增至您的傳遞。 若要這麼做，請使用 **[!UICONTROL SMTP]** 索引標籤進行標籤。

在此視窗中輸入的指令碼必須參考下清單單中每行的一個標題： **name：value**.

如有必要，會自動對值編碼。

>[!IMPORTANT]
>
>會為進階使用者保留新增指令碼，以便插入其他 SMTP 標題。
>
>此指令碼的語法必須符合以下內容類型的要求：沒有未使用的空間，沒有空行等。

![](assets/email-smtp-headers.png)

<!--
## Generate mirror page {#generating-mirror-page}

The mirror page is an HTML page accessible online via a web browser. Its content is identical to the email. It can be useful if your recipients are experiencing rendering issues or broken images when trying to view your email in their inbox.

Learn how to insert a link to the mirror page in [this section](mirror-page.md).-->