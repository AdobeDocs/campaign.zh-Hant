---
product: campaign
title: 傳遞大綱
description: 進一步了解傳送大綱工作流程活動
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# 傳遞大綱{#delivery-outline}

此 **傳遞大網** 可讓您在促銷活動工作流程中使用大綱。 大綱必須預先在促銷活動中建立。

要配置活動，您只需選擇所需的大綱以及計畫的聯繫日期。 您可以新增類型或類型規則，以新增篩選規則。

## 範例：透過傳遞大綱插入優惠方案 {#example--inserting-an-offer-via-a-delivery-outline}

此 **傳遞大網** 活動，可在促銷活動工作流程中使用，可讓您呈現在傳遞大綱中從目前進行中的促銷活動參考的選件。

>[!NOTE]
>
>此 **互動** 必須安裝軟體包。

1. 在工作流程中，新增傳送大綱活動之前，請先新增傳送活動。
1. 在傳送大綱活動中，指定要使用的大綱。
1. 根據您的傳送完成可用欄位。
1. 可能有兩種情況：

   * 如果您想要呼叫優惠方案引擎，請檢查 **[!UICONTROL Restrict the number of propositions selected]** 框。 指定要在傳遞中呈現的優惠方案空間和主張數量。

      優惠方案引擎會考量優惠方案的權重和適用性規則。

   * 如果您未核取方塊，傳遞大綱中的所有選件都會呈現，而不需要呼叫選件引擎。

   預覽會考量傳送中指定的選件數量。 執行工作流程時，會考慮傳送大綱中指定的編號。

   ![](assets/int_compo_offre_wf1.png)
