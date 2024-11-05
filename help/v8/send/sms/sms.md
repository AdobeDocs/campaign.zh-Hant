---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 4%

---

# 開始使用簡訊 {#gs-sms-channel}

使用Adobe Campaign傳送個人化SMS訊息。

>[!NOTE]
>
>Adobe Campaign也可讓您透過其&#x200B;**Adobe Campaign行動應用程式頻道(NMAC)**&#x200B;選項，在行動裝置上提交推播通知。 若要了解詳細資訊，請參閱[本章節](../push.md)。

SMS的簡易性和易用性使其成為非常寶貴的通訊通道，此外還有其穩健性和在數十億台終端機上無與倫比的相容性。

傳送SMS的主要方式有2種：

* 從電話手動傳送。 這是您用來直接在人與人之間通訊的常見方式。
* 從網際網路傳送。 這是Adobe Campaign用來傳送訊息的方式。 為此，您需要一個SMS服務提供者，從網際網路建立橋接至行動網路。

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
