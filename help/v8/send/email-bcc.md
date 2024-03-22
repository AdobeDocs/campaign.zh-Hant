---
title: 將郵件副本傳送至密件副本地址
description: 瞭解如何在Adobe Campaign中啟用電子郵件密件副本
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# 將郵件副本傳送至密件副本地址 {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## 關於電子郵件密件副本 {#gs-bcc}

您可以設定Adobe Campaign以保留從您的平台傳送的電子郵件副本。 此選項可讓您以密件副本（密件副本）專用的電子郵件地址傳送訊息，以便使用外部系統處理和封存訊息。
Adobe Campaign本身不會管理封存的檔案。 與已傳送電子郵件相對應的.eml檔案可接著傳輸至遠端伺服器，例如SMTP電子郵件伺服器。

封存目的地是您選擇的密件副本電子郵件地址，傳遞收件者將看不到該地址。 定義密件副本電子郵件地址後，您必須在 [傳遞範本](create-templates.md) 層級。

>[!NOTE]
>
>作為「受管理的Cloud Service」使用者， [連絡人Adobe](../start/campaign-faq.md#support){target="_blank"} 以傳達要用於封存的密件副本電子郵件地址。

>[!CAUTION]
>
>基於隱私權理由，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。


## 啟用電子郵件密件副本 {#enable-bcc}

啟用特定密件副本的方式 [傳遞範本](create-templates.md)，請遵循下列步驟：

1. 從Campaign檔案總管瀏覽至傳遞範本資料夾。 依預設，傳遞範本會儲存在 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 資料夾。
1. 編輯傳遞範本以使用密件副本進行更新。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 從 **[!UICONTROL Delivery]** 索引標籤，核取 **[!UICONTROL Email BCC]** 選項。

   ![](assets/email-bcc.png)

1. 按一下 **[!UICONTROL Ok]** 確認。

系統會根據此範本，將每次傳遞的所有已傳送訊息復本傳送至已針對您的平台設定的電子郵件密件副本地址。

## 護欄和建議 {#recommendations-bcc}

搭配Adobe Campaign使用電子郵件密件副本時，以下護欄和建議適用：

* 您只能使用一個密件副本電子郵件地址。

* 請確定密件副本位址有足夠的接收容量來封存所有傳送的電子郵件。

* 電子郵件密件副本 <!--with Enhanced MTA--> 會在傳遞給收件者之前傳遞給密件副本電子郵件地址，這會導致即使原始傳遞可能已跳出，仍會傳送密件副本訊息。 如需退信的詳細資訊，請參閱 [瞭解傳遞失敗](delivery-failures.md).

* 傳送至密件副本位址的電子郵件不可開啟或點進，因為這些活動會在中列入考量 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 傳送分析可能會造成計算錯誤。

<!--Only successfully sent emails are taken in account, bounces are not.-->
