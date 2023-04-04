---
product: campaign
title: 呈現選件（入站互動）
description: 了解如何使用Campaign互動模組呈現最佳優惠方案
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 9%

---

# 提供最佳優惠方案{#interaction-present-offers}

優惠方案可在各種優惠方案空間中顯示，使用 [傳入或傳出頻道](interaction-architecture.md#interaction-types). 本章詳細說明傳入頻道的某些特定功能。

![](assets/inbound-interactions.png)

為了讓優惠方案引擎選取優惠方案，必須經過核准，並可在即時環境中使用。

![](../assets/do-not-localize/book.png) 如需詳細資訊，請參閱 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

在傳入連絡人的內容中，瀏覽頁面的使用者可由網站識別，或不可由網站識別。 選件引擎會針對已識別的設定檔和匿名設定檔顯示不同的選件。

您必須先設定優惠方案引擎呼叫，以便在其中顯示優惠方案，才能在入站管道上顯示優惠方案。 在傳入互動的大多數情況下，此為網頁。

>[!NOTE]
>
>對於入站互動，您必須明確設定選件引擎以呈現和更新一或多個選件。
>
>您也必須在優惠方案空間上啟用統一模式。 如需詳細資訊，請參閱[此頁面](interaction-offer-spaces.md)。
