---
product: campaign
title: 使用Adobe Campaign在日文的行動裝置上傳送電子郵件
description: 瞭解如何設定、設計和傳送將在日文行動裝置上閱讀的電子郵件
feature: Email, Email Design
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 02cca21f-b1ac-4ac2-9761-015f6c7f5567
source-git-commit: 3d562aab2f19b84aad8b484768bf19648145feb3
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# 在日文的行動裝置上傳送電子郵件 {#sending-emails-on-japanese-mobiles}

## 日文行動裝置的電子郵件格式 {#email-formats-for-japanese-mobiles}

Adobe Campaign針對行動裝置上的電子郵件管理三種特定的日文格式： **裝飾郵件** （DoCoMo行動裝置）、**裝飾郵件** （Softbank行動裝置）和&#x200B;**裝飾郵件** （KDDI AU行動裝置）。 這些格式會施加特定的編碼、結構和大小限制。 在[本節](#limitations-and-recommendations)中進一步瞭解限制和建議。

為了讓收件者正確接收這些格式之一的郵件，建議在對應設定檔中選取&#x200B;**[!UICONTROL Deco-mail (DoCoMo)]**、**[!UICONTROL Decore Mail (Softbank)]**&#x200B;或&#x200B;**[!UICONTROL Decoration Mail (KDDI AU)]**：

![](assets/deco-mail_03.png)

不過，如果您保留&#x200B;**[!UICONTROL Email format]**&#x200B;選項為&#x200B;**[!UICONTROL Unknown]**、**[!UICONTROL HTML]**&#x200B;或&#x200B;**[!UICONTROL Text]**，Adobe Campaign會自動偵測（傳送電子郵件時）要使用的日文格式，以便正確顯示訊息。

此自動偵測系統以&#x200B;**[!UICONTROL Management of Email Formats]**&#x200B;郵件規則集中定義的預先定義網域清單為基礎。 如需管理電子郵件格式的詳細資訊，請參閱[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/email-deliverability.html?lang=zh-Hant#managing-email-formats)。

## 限制和建議 {#limitations-and-recommendations}

傳送電子郵件時，若需在日本提供者(Softbank、DoCoMo、KDDI AU)營運的行動裝置上讀取電子郵件，需適用一定數量的限制。

因此，您必須：

* 僅使用JPEG或GIF格式的影像
* 建立包含嚴格低於10,000位元組之文字和HTML區段的傳遞（針對KDDI AU和DoCoMo）
* 使用總大小（編碼前）小於100 KB的影像
* 每則訊息請勿使用超過20個影像
* 使用精簡大小的HTML格式（每個運運算元可用的標籤數量有限）

>[!NOTE]
>
>建立訊息時，必須考慮每個運運算元的特定限制。 請參閱他們的產品檔案。


## 測試電子郵件內容 {#testing-the-email-content}

### 預覽訊息 {#previewing-the-message}

Adobe Campaign可讓您檢查您的訊息格式是否適合傳送至日本行動裝置。

定義內容並輸入電子郵件主旨後，您便可以在建立訊息時檢查顯示和格式設定。

在內容編輯視窗的「**[!UICONTROL Preview]**」標籤中，按一下「**[!UICONTROL More... > Deco-mail diagnostic]**」可讓您：

* 檢查HTML內容標籤是否符合日文格式限制
* 檢查訊息中的影像數量是否未超過格式的限制（20個影像）
* 檢查郵件大小總計（小於100kB）

  ![](assets/deco-mail_06.png)

### 執行型別規則 {#running-typology-rule}

除了預覽診斷之外，在傳送證明或傳遞時會執行第二次檢查：分析期間會啟動特定型別規則&#x200B;**[!UICONTROL Deco-mail check]**。

>[!IMPORTANT]
>
>只有當至少有一個收件者設定為接收&#x200B;**[!UICONTROL Deco-mail (DoCoMo)]**、**[!UICONTROL Decore Mail (Softbank)]**&#x200B;或&#x200B;**[!UICONTROL Decoration Mail (KDDI AU)]**&#x200B;格式的電子郵件時，才會執行此型別規則。

此型別規則可讓您確保傳遞符合日文運運算元定義的[格式限制](#limitations-and-recommendations)，尤其是關於電子郵件的總大小、HTML和文字區段的大小、訊息中的影像數目，以及HTML內容中的標籤。

### 傳送校樣 {#sending-proofs}

您可以傳送校樣以測試您的傳遞。 當您傳送證明時，如果您使用替代地址，請輸入與所使用設定檔的電子郵件格式對應的地址。

例如，若已在&#x200B;**[!UICONTROL Decore Mail (Softbank)]**&#x200B;預先定義此設定檔的電子郵件格式，您可以用test@softbank.ne.jp取代設定檔的位址。

![](assets/deco-mail_05.png)

## 傳送訊息 {#sending-messages}

若要使用Campaign以日文電子郵件格式傳送電子郵件給收件者，有兩個可能的選項：

* 建立兩個傳遞：一個僅用於日文收件者，另一個用於其他收件者 — 請參閱[本節](#designing-a-specific-delivery-for-japanese-formats)。
* 建立單一傳遞，Adobe Campaign會自動偵測要使用的格式 — 請參閱[本節](#designing-a-delivery-for-all-formats)。

### 設計日文格式的特定傳遞 {#designing-a-specific-delivery-for-japanese-formats}

您可以建立包含兩個傳遞的工作流程：一個要在日文行動裝置上讀取，另一個適用於具有標準電子郵件格式的收件者。

若要這麼做，請在工作流程中使用&#x200B;**[!UICONTROL Split]**&#x200B;活動，並將日文電子郵件格式（裝飾郵件、裝飾郵件和裝飾郵件）定義為篩選條件。

![](assets/deco-mail_08.png)

![](assets/deco-mail_07.png)

### 為所有格式設計傳遞 {#designing-a-delivery-for-all-formats}

當Adobe Campaign根據網域（具有定義為&#x200B;**[!UICONTROL Unknown]**、**[!UICONTROL HTML]**&#x200B;或&#x200B;**[!UICONTROL Text]**&#x200B;之電子郵件格式的設定檔）動態管理格式時，您可以將相同的傳遞傳送給所有收件者。

訊息連絡人將會在日文的行動裝置上正確顯示給使用者，就像標準收件者一樣。

>[!IMPORTANT]
>
>請務必遵守與每種日文電子郵件格式（裝飾郵件、裝飾郵件和裝飾郵件）相關的特殊功能。 如需限制的詳細資訊，請參閱[本節](#limitations-and-recommendations)。
