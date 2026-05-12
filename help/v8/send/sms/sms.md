---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 12%

---

# 開始使用簡訊 {#gs-sms-channel}

使用Adobe Campaign傳送簡訊給行動裝置上的客戶。 您可以從SMS編輯器以文字格式建立、個人化和預覽訊息。

若要透過Adobe Campaign傳送簡訊至行動裝置，您需要：

* 在&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;管道上設定的外部帳戶。 瞭解如何在您的[中間來源基礎結構](sms-mid-sourcing.md)上設定簡訊頻道。 針對此設定，您需要瞭解[SMPP外部帳戶引數](smpp-external-account.md)和[SMS通道特性](sms-channel.md)。
完成此設定後，請檢查您的SMPP連線，並瞭解必要時如何疑難排解。 [了解更多資訊](smpp-connection.md)。

* 已正確連結至此外部帳戶的SMS傳送範本。

Adobe Campaign支援兩個SMS聯結器，用於傳送簡訊給您的客戶。 [了解更多資訊](sms-connectors.md)。

>[!NOTE]
>
>您也可以使用Adobe Campaign將[推播通知](../push.md)和[LINE](../line/line.md)訊息傳送至行動裝置。

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
