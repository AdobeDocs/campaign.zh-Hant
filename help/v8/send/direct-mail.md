---
title: 與Adobe Campaign直接發送郵件
description: 在市場活動中開始使用直郵
feature: Direct Mail
role: Data Engineer
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 12%

---

# 建立直接郵件傳遞

通過直接郵寄，您可以生成包含目標人口資料的提取檔案。 然後，您可以與提供程式共用此檔案，該提供程式將向目標群體傳遞消息。

生成檔案的步驟如下：

1. 建立交貨

   根據模板建立直郵遞送。 您可以複製和配置 **[!UICONTROL Deliver by direct mail (paper)]** 內置模板。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. 定義對象

   收件人配置檔案必須至少包含其姓名和郵政地址。

   郵政地址是計算欄位。 預設情況下，地址最多可包含六行：第一行包含名字和姓氏，下一行包含郵政地址（道路等），最後一行包含郵遞區號和城鎮。

   如果名稱、郵遞區號欄位和城鎮/城市欄位不為空，則地址被視為完整地址。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. 定義檔案內容

   使用抽取嚮導可定義要導出到輸出檔案的資訊（列）。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. 驗證傳遞

   檢查分析結果和輸出檔案的內容。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

   在市場營銷活動的上下文中，在提取日期建立提取檔案。 您可以查看提取的檔案的內容、批准它或更改格式，並在需要時重新啟動提取。 檔案獲得批准後，您可以向路由器發送通知電子郵件。 在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html)中了解更多

1. 開始交貨

   驗證抽取檔案後，按一下 **確認交貨** 通過確認消息可以啟動傳遞。

   確認將啟動指定檔案中的資料提取。

   在市場營銷活動的上下文中，當所有批准都被授予時，提取檔案通過特殊工作流建立，在預設配置中，當直郵遞送處於待提取狀態時，該工作流將自動啟動。 瞭解詳情 [此部分](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hant)
