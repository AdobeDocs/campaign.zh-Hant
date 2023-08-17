---
product: campaign
title: 傳遞大綱
description: 深入瞭解傳遞大網工作流程活動
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# 傳遞大綱{#delivery-outline}

此 **傳遞大網** 可讓您在行銷活動工作流程中使用大綱。 必須預先在行銷活動中建立大綱。

若要設定活動，您只需要選取您喜歡的大綱以及計畫的聯絡日期。 您可以新增型別或型別規則，以新增篩選規則。

## 範例：透過傳遞大網插入優惠方案 {#example--inserting-an-offer-via-a-delivery-outline}

此 **傳遞大網** 活動可在行銷活動工作流程中使用，可讓您顯示目前進行中行銷活動之傳遞大網所參考的優惠。

>[!NOTE]
>
>此 **互動** 必須安裝套件。

1. 在工作流程中，新增傳遞活動之前，請先新增傳遞大網活動。
1. 在傳遞大網活動中，指定您要使用的大網。
1. 根據您的傳送完成可用的欄位。
1. 有兩種可能的情況：

   * 如果您想要呼叫優惠方案引擎，請檢查 **[!UICONTROL Restrict the number of propositions selected]** 方塊。 指定優惠方案空間以及將在傳遞中顯示的建議數量。

     優惠方案引擎會考慮優惠方案權重和適用性規則。

   * 如果您未勾選此方塊，則傳遞大網中的所有優惠方案都會顯示，而不會呼叫優惠方案引擎。

   預覽會考量傳送中指定的優惠方案數量。 執行工作流程時，會考慮傳遞大網中指定的數字。

   ![](assets/int_compo_offre_wf1.png)
