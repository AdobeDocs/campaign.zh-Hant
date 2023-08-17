---
product: campaign
title: 持續傳遞
description: 持續傳遞
feature: Workflows, Channels Activity
exl-id: e3ad6d92-8d53-4098-90fd-cfed29f2e56e
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 9%

---

# 持續傳遞{#continuous-delivery}



A **持續傳遞** 型別動作可讓您將新收件者新增至現有傳遞。 此傳送型別可避免您每次都必須建立新傳送：此模式通常更有效率，尤其是當需要時會傳送少量警報或通知。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#continuous-delivery-video)

在傳遞範本層級，您可以指定指令碼以計算相關傳遞的標籤（和行銷活動資料夾）。 如果指令碼計算尚未存在的傳遞，則會即時建立傳遞。

![](assets/edit_diffusion_fil.png)

此 **[!UICONTROL Process errors]** 選項會顯示特定轉變，如果產生錯誤，則會啟用此轉變。 在此情況下，工作流程不會進入錯誤模式並繼續執行。

考慮的錯誤是檔案系統錯誤（無法移動檔案、無法存取目錄等）。

此選項不會處理與活動設定相關的錯誤，即無效值。

## 輸入引數 {#input-parameters}

* tableName
* 綱要

每個傳入事件都必須指定由這些引數定義的目標。

僅當 **[!UICONTROL Specified by the inbound event]** 已選取選項。

## 輸出引數 {#output-parameters}

* tableName
* 綱要
* recCount

這組三個值會識別即時傳送中產生的目標。 **[!UICONTROL tableName]** 是記憶目標識別碼的表格名稱， **[!UICONTROL schema]** 是母體的綱要（通常是nms：recipient）和 **[!UICONTROL recCount]** 是表格中的元素數。

與補充關聯的轉變有相同的引數。

## 如何設定連續傳送

本節說明如何設定持續傳遞。

此 **持續傳遞** 可讓您將新收件者新增至現有傳遞，並避免每次新增收件者時都必須建立新傳遞。 您可以直接在行銷活動工作流程中更新創意素材，其將會更新傳遞範本「資源」資料夾中的範本。

持續傳遞會建立「單一」傳遞和傳遞記錄(broadLog)以及追蹤記錄，每次執行傳遞時都會參照新增。

![持續傳遞](assets/delivery_continuous.jpg)

## 教學課程影片 {#continuous-delivery-video}

此影片說明如何使用增量查詢來設定持續傳送。

>[!VIDEO](https://video.tv.adobe.com/v/25039?quality=12)

提供其他Campaign操作說明影片 [此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
