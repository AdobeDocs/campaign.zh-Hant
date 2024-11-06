---
title: 使用Adobe Campaign傳送簡訊
description: 開始使用Campaign的簡訊
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 19c5a15a0f42285fc3b1a448f3cbf474d741e6e2
workflow-type: tm+mt
source-wordcount: '155'
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
>您也可以使用Adobe Campaign來傳送[LINE](../../send/line.md)訊息，其中包含文字和/或影像與連結。


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
<img alt="簡訊內容" src="../../assets/do-not-localize/sms.jpg">
</a>
<div>
<a href="sms-content.md"><strong>定義及個人化內容</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="客群" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>選擇退出管理</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="設定" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>設定簡訊頻道</strong></a>
</div>
<p>
</td>
</tr></table>
