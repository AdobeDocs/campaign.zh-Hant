---
product: campaign
title: 傳遞大綱
description: 深入瞭解傳遞大網工作流程活動
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# 傳遞大綱{#delivery-outline}

**傳遞大綱**&#x200B;可讓您在行銷活動工作流程中使用大綱。 必須預先在行銷活動中建立大綱。

若要設定活動，您只需要選取您喜歡的大綱以及計畫的聯絡日期。 您可以新增型別或型別規則，以新增篩選規則。

## 範例：透過傳遞大網插入優惠方案 {#example--inserting-an-offer-via-a-delivery-outline}

行銷活動工作流程中可用的&#x200B;**傳遞大網**&#x200B;活動可讓您呈現傳遞大網中參考之目前進行中行銷活動的選件。

>[!NOTE]
>
>必須安裝&#x200B;**互動**&#x200B;套件。

1. 在工作流程中，新增傳遞活動之前，請先新增傳遞大網活動。
1. 在傳遞大網活動中，指定您要使用的大網。
1. 根據您的傳送完成可用的欄位。
1. 有兩種可能的情況：

   * 如果要呼叫優惠方案引擎，請核取&#x200B;**[!UICONTROL Restrict the number of propositions selected]**&#x200B;方塊。 指定優惠方案空間以及將在傳遞中顯示的建議數量。

     優惠方案引擎會考慮優惠方案權重和適用性規則。

   * 如果您未勾選此方塊，則傳遞大網中的所有優惠方案都會顯示，而不會呼叫優惠方案引擎。

   預覽會考量傳送中指定的優惠方案數量。 執行工作流程時，會考慮傳遞大網中指定的數字。

   ![](assets/int_compo_offre_wf1.png)
