---
title: 使用Adobe Campaign傳送直接郵件
description: 開始使用Campaign中的直接郵件
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

直接郵件傳遞可讓您產生擷取檔案，其中包含目標群體的資料。 然後，您可以與將傳送訊息給目標母體的提供者共用此檔案。

產生檔案的步驟如下：

1. 建立傳遞

   根據範本建立直接郵件傳遞。 您可以複製並設定 **[!UICONTROL Deliver by direct mail (paper)]** 內建範本。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. 定義對象

   收件者設定檔必須至少包含其名稱和郵寄地址。

   郵寄地址為計算欄位。 依預設，地址最多可包含六行：第一行包含名字和姓氏，下一行包含郵遞區號（道路等），最後一行包含郵遞區號和城鎮或城市。

   如果名稱、郵遞區號欄位和城鎮/城市欄位並非空白，則會視為完整的地址。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. 定義檔案內容

   使用擷取精靈來定義要匯出至輸出檔案的資訊（欄）。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. 驗證傳遞

   檢查分析結果和輸出檔案的內容。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文件 中深入瞭解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

   在行銷活動的內容中，在解壓縮日期，會建立解壓縮檔案。 您可以檢視解壓縮檔案的內容、核准解壓縮檔案，或變更格式，然後視需要重新啟動解壓縮。 一旦檔案獲得核准，您就可以將通知電子郵件傳送給路由器。 在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html)中了解更多

1. 開始傳遞

   驗證解壓縮檔案後，請按一下 **確認傳遞** 確認訊息可讓您啟動傳送。

   確認作業會開始擷取指定檔案中的資料。

   在行銷活動的內容中，當所有核准皆已授與後，擷取檔案會透過特殊工作流程建立，在預設設定中，當直接郵件傳送擱置擷取時，會自動啟動。 進一步瞭解 [本節](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hant)
