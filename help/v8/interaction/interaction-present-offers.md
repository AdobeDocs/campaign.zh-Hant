---
product: campaign
title: 提供優惠（入站交互）
description: 瞭解如何使用「活動交互」模組演示最佳優惠
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 9%

---

# 提供最佳優惠{#interaction-present-offers}

可以使用 [入站或出站通道](interaction-architecture.md#interaction-types)。 本章詳細介紹了入站通道的某些特定功能。

![](assets/inbound-interactions.png)

要讓優惠引擎選擇優惠，必須批准該優惠並在即時環境中提供。

![](../assets/do-not-localize/book.png) 如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content)

在入站聯繫人的上下文中，瀏覽該頁面的用戶可由網站識別或不識別。 「提供」引擎為已識別的配置檔案和匿名配置檔案提供不同的提供。

在能夠在入站渠道上演示優惠之前，必須配置優惠引擎呼叫，以便在其中顯示優惠。 在大多數入站交互的情況下，這是Web頁。

>[!NOTE]
>
>對於入站交互，您必須特別配置「優惠」引擎以呈現和更新一個或多個優惠。
>
>您還必須在優惠空間上啟用統一模式。 如需詳細資訊，請參閱[此頁面](interaction-offer-spaces.md)。
