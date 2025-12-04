---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 10%

---

# 開始使用簡訊 {#gs-sms-channel}

使用Adobe Campaign傳送簡訊給行動裝置上的客戶。 您可以從SMS編輯器以文字格式建立、個人化和預覽訊息。

若要透過Adobe Campaign傳送簡訊至行動裝置，您需要：

* 在&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;管道上設定的外部帳戶。 瞭解如何在您的[中間來源基礎結構](sms-mid-sourcing.md)上設定簡訊頻道。 針對此設定，您需要瞭解[SMPP外部帳戶引數](smpp-external-account.md)和[SMS通道特性](sms-channel.md)。
完成此設定後，請檢查您的SMPP連線，並瞭解必要時如何疑難排解。 [了解更多](smpp-connection.md)。

* 已正確連結至此外部帳戶的SMS傳送範本。


>[!NOTE]
>
>您也可以使用Adobe Campaign將[推播通知](../push.md)和[LINE](../line/line.md)訊息傳送至行動裝置。
>
> 對於使用舊版SMS聯結器的客戶，現有實作仍受支援。 不過，我們建議移至新的聯結器。 如果您想要轉換，請聯絡Adobe。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="建立簡訊" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>建立簡訊傳遞</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="簡訊內容" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>定義您的SMS內容</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="簡訊對象" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>選取客群</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="簡訊設定" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>設定簡訊頻道</strong></a>
</div>
<p>
</td>
</tr></table>
