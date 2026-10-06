---
title: 簡訊傳送校樣
description: 瞭解如何傳送簡訊傳遞的校樣
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: 'https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 1%
---
# 傳送簡訊傳遞的證明 {#sms-proof}

Adobe強烈建議您設定傳遞驗證週期。 將內容傳送給對象之前，請確定內容已核准。

您可以傳送簡訊傳遞的證明以進行驗證：

1. 按一下&#x200B;**[!UICONTROL Send a proof]**&#x200B;按鈕，將會開啟一個視窗

   ![](assets/proof_targeting.png){zoomable="yes"}

   您有多個模式可傳送證明：

   * **[!UICONTROL Definition of a specific proof target]**：可讓您以篩選條件查詢資料庫中作為證明目標的地址
   * **[!UICONTROL Substitution of the address]**：可讓您輸入測試地址，並使用目標收件者資料來驗證內容。 您可以手動輸入替代地址，或從下拉式清單中選取替代地址。 關聯的[分項清單](../../config/enumerations.md)是&#x200B;**[!UICONTROL Substitution address (rcpAddress)]**。
     預設會隨機執行替代，但您可以透過**[!UICONTROL Detail]**&#x200B;圖示從主要目標中選取特定收件者。
   * **[!UICONTROL Seed addresses]**：可讓您存取種子地址以作為證明目標。 這些位址可從檔案匯入或手動輸入。
   * **[!UICONTROL Specific target and Seed addresses]**：可讓您合併來自收件者的種子地址和地址。

1. 選擇您的&#x200B;**[!UICONTROL Targeting mode]**&#x200B;後，根據它新增您的證明地址

   在下列範例中，我們選擇&#x200B;**[!UICONTROL Definition of a specific proof target]**，並新增收件者：

   ![](assets/proof_recipient.png){zoomable="yes"}

1. 按一下 **[!UICONTROL Analyze]** 按鈕。
Adobe Campaign會在驗證證明傳送之前執行所有控制。 分析結束時，**[!UICONTROL Confirm delivery]**&#x200B;按鈕將可供點按。

   ![](assets/proof_analyze.png){zoomable="yes"}

1. 若要傳送簡訊傳遞的證明，請按一下&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;按鈕。

如果這個階段一切正常，您可以繼續並[傳送您的SMS傳送給對象](sms-audience.md)。
