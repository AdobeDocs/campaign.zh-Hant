---
product: Adobe Campaign
title: 使用Adobe Campaign傳送直接郵件
description: 開始使用Campaign中的直接郵件
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 12%

---

# 建立直接郵件傳遞

直接郵件傳送可讓您產生包含目標母體資料的擷取檔案。 然後，您可以與提供者共用此檔案，該提供者將傳送訊息給目標人口。

產生檔案的步驟如下：

1. 建立傳送

   根據範本建立直接郵件傳送。 您可以複製並配置&#x200B;**[!UICONTROL Deliver by direct mail (paper)]**&#x200B;內建範本。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html) 中深入瞭解

1. 定義對象

   收件者設定檔至少必須包含其名稱和郵遞區號。

   郵遞區號是計算欄位。 預設情況下，地址最多可包含6行：第一行包含名字和姓氏，下一行包含郵遞區號（道路等），最後一行則包含郵遞區號和城鎮。

   如果名稱、郵遞區號欄位和城鎮/城市欄位不為空，則地址視為完整。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html) 中深入瞭解

1. 定義檔案的內容

   使用提取精靈來定義要匯出至輸出檔案的資訊（欄）。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html) 中深入瞭解

1. 驗證傳遞

   檢查分析結果和輸出檔案的內容。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html) 中深入瞭解

   在行銷活動的內容中，提取日期即會建立提取檔案。 您可以檢視擷取的檔案內容、核准，或變更格式，並視需要重新啟動擷取。 檔案獲得批准後，您就可以向路由器發送通知電子郵件。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file) 中深入瞭解

1. 開始傳送

   驗證解壓縮檔案後，按一下&#x200B;**確認傳送**&#x200B;確認訊息可讓您啟動傳送。

   確認會開始指定檔案中的資料擷取。

   在行銷活動的內容中，當所有核准均已授與時，擷取檔案會透過特殊工作流程建立，而在預設設定中，當直接郵件傳送擱置擷取時，此工作流程會自動啟動。

   ↗️ 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery) 中深入瞭解