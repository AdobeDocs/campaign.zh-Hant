---
title: 使用Adobe Campaign傳送直接郵件
description: 開始使用Campaign中的直接郵件
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 11%

---

# 建立直接郵件傳遞

直接郵件傳遞可讓您產生擷取檔案，其中包含目標群體的資料。 然後，您可以與將傳送訊息給目標母體的提供者共用此檔案。

產生檔案的步驟如下：

1. 建立傳遞

   根據範本建立直接郵件傳遞。 您可以複製並設定 **[!UICONTROL Deliver by direct mail (paper)]** 內建範本。

   在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html) 中深入瞭解{target="_blank"}

1. 定義對象

   收件者設定檔必須至少包含其名稱和郵寄地址。

   郵寄地址為計算欄位。 依預設，地址最多可包含6行：第一行包含名字和姓氏，下一行包含郵遞區號（道路等），而最後一行包含郵遞區號和城鎮。 您可以在nms：recipient綱要中檢閱預設計算postalAddress欄位的定義。

   如果名稱、郵遞區號欄位和城鎮/城市欄位並非空白，則會將地址視為完整。 所有位址不完整的收件者都會從直接郵件傳遞中排除。

   在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html) 中深入瞭解{target="_blank"}

1. 定義檔案的內容

   使用擷取精靈來定義要匯出至輸出檔案的資訊（欄）。

   在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html) 中深入瞭解{target="_blank"}

1. 驗證傳遞

   檢查分析結果和輸出檔案的內容。

   在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html) 中深入瞭解{target="_blank"}

   在行銷活動的內容中，於解壓縮日期建立解壓縮檔案。 您可以檢視擷取的檔案內容、核准該檔案，或視需要變更格式並重新啟動擷取。 一旦檔案獲得核准，您就可以將通知電子郵件傳送給路由器。 在[本頁](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hant)中了解更多

1. 開始傳遞

   驗證解壓縮檔案後，請按一下 **確認傳遞** 確認訊息可讓您啟動傳送。

   確認會在指定的檔案中開始資料擷取。

   在行銷活動的內容中，當所有核准都獲得授權時，擷取檔案會透過特殊工作流程建立，在預設設定中，當直接郵件傳送擱置擷取時，會自動開始。 進一步瞭解 [本節](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hant)
