---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: bb77b915f50b31d8d91e25da6fa86aa15b03bba4
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# 開始使用簡訊 {#gs-sms-channel}

Adobe Campaign可讓您在行動裝置上傳送個人化簡訊。

對於 SMS 訊息，您只能以文字格式建立、修改和個人化訊息。 您也可以在傳送簡訊之前先預覽簡訊。

>[!NOTE]
>
>您也可以使用Adobe Campaign來傳送[LINE](../../send/line.md)訊息，其中包含文字和/或影像與連結。

若要透過Adobe Campaign傳送簡訊至行動電話，您需要：

* 在&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;管道或在&#x200B;**[!UICONTROL LINE]**&#x200B;管道設定外部帳戶。
* 已正確連結至此外部帳戶的SMS傳送範本。

您可以在本檔案中檢視設定、傳送和監控SMS傳送的步驟：

* **設定簡訊頻道**

首先，您需要在[中間來源基礎結構](sms-mid-sourcing.md)上設定SMS頻道。

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

針對此設定，您需要瞭解[SMPP外部帳戶引數](smpp-external-account.md)和[SMS通道特性](sms-channel.md)。

完成此設定後，請檢查您的[SMPP連線，並瞭解如何在需要時進行疑難排解](smpp-connection.md)。

* **建立您的第一個SMS傳遞**

若要開始設定SMS傳遞：

1. 建立您的傳遞，並填入[SMS傳遞設定](sms-delivery-settings.md)，

1. [定義傳遞的內容](sms-content.md)，

1. [選取對象](sms-audience.md)。

定義對象的步驟已詳載於[此頁面](../../audiences/create-audiences.md)。

* **驗證並傳送簡訊**

建立傳遞後：

1. [傳送校樣](sms-proofs.md)以驗證轉譯與內容，

1. 然後，[傳送給最終對象](sms-send.md)。

* **監視及追蹤SMS**

傳送後，[瞭解如何監視及追蹤您的SMS](sms-monitor.md)。
