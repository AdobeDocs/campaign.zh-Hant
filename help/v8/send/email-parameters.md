---
title: Adobe Campaign中的電子郵件引數
description: 瞭解Adobe Campaign中專用於電子郵件傳送的選項和設定。
feature: Email
role: User
level: Beginner
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 87c971ac6cf4abb6b04d52ce60ac2036055e1e02
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 10%

---

# 電子郵件參數 {#email-parameters}

本節介紹專屬於電子郵件傳送的傳送屬性中可用的選項和引數。

## 使用電子郵件密件副本 {#email-bcc}

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件副本。 此選項的詳細資訊，請參閱 [此頁面](email-bcc.md).

## 選取訊息格式 {#selecting-message-formats}

您可以變更已傳送電子郵件訊息的格式。 若要這麼做，請編輯傳送屬性，然後按一下 **[!UICONTROL Delivery]** 標籤。

![](assets/email-message-format.png)

在視窗的下半部分選取電子郵件的格式：

* **[!UICONTROL Use recipient preferences]** （預設模式）

  訊息格式會根據儲存在收件者設定檔中的資料定義，並預設會儲存在 **[!UICONTROL email format]** 欄位(@emailFormat)。 如果收件者希望以特定格式接收郵件，則此格式為傳送的格式。如果未填入欄位，則會傳送替代的多重部分訊息（請參閱下文）。

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  訊息包含兩種格式：文字和HTML。 接收時顯示的格式取決於收件者郵件軟體的設定（替代的多重部分）。

  >[!IMPORTANT]
  >
  >此選項包含檔案的兩個版本。 因此，這會減少傳送輸送量，因為郵件大小較大。

* **[!UICONTROL Send all messages in text format]**

  訊息會以文字格式傳送。 不會傳送HTML格式，但只有當收件者按一下郵件時，才會用於映象頁面。

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## 設定字元編碼 {#character-encoding}

在 **[!UICONTROL SMTP]** 的標籤中， **[!UICONTROL Character encoding]** 區段可讓您設定特定編碼。

預設編碼為UTF-8。 如果部分收件者的電子郵件提供者不支援UTF-8標準編碼，您可能想要設定特定編碼，以正確向電子郵件的收件者顯示特殊字元。

例如，您想要傳送包含日文字元的電子郵件。 為確保所有字元都能正確顯示給在日本的收件者，您可能想要使用可支援日文字元的編碼，而非標準UTF-8。

若要這麼做，請選取 **[!UICONTROL Force the encoding used for messages]** 中的選項 **[!UICONTROL Character encoding]** 區段，並從顯示的下拉式清單中選擇編碼。

![](assets/email-smtp-encoding.png)

## 管理退信電子郵件 {#managing-bounce-emails}

此 **[!UICONTROL SMTP]** 傳遞屬性的索引標籤也可讓您設定退回郵件的管理。

* **[!UICONTROL Errors-to-address]**：依預設，會在平台的預設錯誤方塊中接收跳出的電子郵件，但您可以定義傳送的特定錯誤地址。

* **[!UICONTROL Bounce address]**：您也可以定義另一個地址，未處理的退回電子郵件會轉寄至該地址。 此位址可讓您在應用程式無法自動限定電子郵件時，調查退回的原因。

每個欄位都可以使用專用圖示進行個人化。 進一步瞭解中的個人化欄位 [本節](personalization-fields.md).

![](assets/email-smtp-bounce.png)

有關退回郵件管理的詳細資訊，請參閱 [本節](delivery-failures.md#bounce-mail-management).

## 新增SMTP標頭 {#adding-smtp-headers}

您可以新增SMTP標頭至您的傳遞。 若要這麼做，請使用 **[!UICONTROL SMTP]** 索引標籤進行標籤。

在此視窗中輸入的指令碼必須參考下清單單中每行的一個標題： **name：value**.

如有必要，會自動對值編碼。

>[!IMPORTANT]
>
>系統會為進階使用者保留新增指令碼，以便插入其他SMTP標題。
>
>此指令碼的語法必須符合以下內容類型的要求：沒有未使用的空間，沒有空行等。

![](assets/email-smtp-headers.png)


## 產生映象頁面 {#generating-mirror-page}

鏡像頁面是可透過網頁瀏覽器線上存取的 HTML 頁面。其內容與電子郵件相同。如果您的收件者嘗試在收件匣中檢視您的電子郵件時遇到轉譯問題或影像損毀，此功能會很有用。

瞭解如何在中插入映象頁面的連結 [本節](mirror-page.md)
