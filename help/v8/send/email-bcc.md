---
title: 將郵件副本傳送至密件副本地址
description: 瞭解如何在Adobe Campaign中啟用電子郵件密件副本
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
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

>[!CAUTION]
>
>基於隱私權理由，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。

Adobe Campaign本身不會管理封存的檔案。 與已傳送電子郵件相對應的.eml檔案可接著傳輸至遠端伺服器，例如SMTP電子郵件伺服器。

封存目的地是您選擇的密件副本電子郵件地址，傳遞收件者將看不到該地址。 定義密件副本電子郵件地址後，您必須在[傳遞範本](create-templates.md)層級啟用專用選項。

>[!NOTE]
>
>作為Managed Cloud Services使用者，[聯絡Adobe](../start/campaign-faq.md#support){target="_blank"}以傳達要用於封存的密件副本電子郵件地址。

## 啟用電子郵件密件副本 {#enable-bcc}

若要啟用特定[傳遞範本](create-templates.md)的密件副本，請遵循下列步驟：

1. 從Campaign檔案總管瀏覽至傳遞範本資料夾。 依預設，傳遞範本會儲存在&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;資料夾中。
1. 編輯傳遞範本以使用密件副本進行更新。
1. 按一下 **[!UICONTROL Properties]** 按鈕。
1. 從&#x200B;**[!UICONTROL Delivery]**&#x200B;索引標籤，核取&#x200B;**[!UICONTROL Email BCC with enhanced Momentum]**&#x200B;選項。

   ![](assets/email-bcc.png)

1. 按一下 **[!UICONTROL Ok]** 確認。

系統會根據此範本，將每次傳遞的所有已傳送訊息復本傳送至已針對您的平台設定的電子郵件密件副本地址。

## 護欄和建議 {#recommendations-bcc}

搭配Adobe Campaign使用電子郵件密件副本時，以下護欄和建議適用：

* 您只能使用一個密件副本電子郵件地址。

* 請確定密件副本位址有足夠的接收容量來封存所有傳送的電子郵件。

* 電子郵件BCC <!--with Enhanced MTA-->在傳遞給收件者之前會傳遞到BCC電子郵件地址，這可能會導致即使原始傳遞可能已退回，仍會傳送BCC訊息。 如需退信的詳細資訊，請參閱[瞭解傳遞失敗](delivery-failures.md)。

* 傳送至密件副本位址的電子郵件不可開啟或點進，因為傳送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;會考慮這些活動，所以可能會導致計算錯誤。

<!--Only successfully sent emails are taken in account, bounces are not.-->
