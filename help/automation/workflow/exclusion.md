---
product: campaign
title: 排除
description: 深入了解「排除」工作流程活動
feature: Workflows, Targeting Activity
exl-id: 8ea831e2-8e6e-4ef0-ac05-f27ebf89ccb9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# 排除{#exclusion}



安 **排除**-type活動會根據主要目標建立目標，從中提取一個或多個其他目標。

若要設定此活動，請輸入其標籤並選取主要收件者集：主集的母體可讓您建構結果。 將排除由主集共用的設定檔以及至少一個登入活動。

![](assets/s_user_segmentation_exclu.png)

>[!NOTE]
>
>如需設定和使用排除活動的詳細資訊，請參閱 [排除母體（排除）](targeting-workflows.md#excluding-a-population--exclusion-).

檢查 **[!UICONTROL Generate complement]** 選項。 補充將包含主要傳入人口減去傳出人口。 接著，會將其他輸出轉變新增至活動，如下所示：

![](assets/s_user_segmentation_exclu_compl.png)

## 排除範例 {#exclusion-examples}

以下範例試圖匯編一份18至30歲的收件者名單，同時排除巴黎居民。

1. 插入並開啟 **[!UICONTROL Exclusion]** -type活動。 第一個查詢會鎖定居住在巴黎的收件者。 第二個查詢目標為18至30歲的人。
1. 輸入主集。 主集為 **18歲–30歲** 查詢。 與第二組相關的元素將從最終結果中排除。
1. 檢查 **[!UICONTROL Generate complement]** 選項。 在這種情況下，補充是由居住在巴黎的18至30歲收件者組成。
1. 核准排除設定，然後插入更新清單活動至結果。 您也可以視需要插入額外清單更新至補充項目。
1. 執行工作流程。 在此範例中，結果是由18至30歲的收件者所組成，但居住在巴黎的收件者則被排除，並傳送至補充項目。

   ![](assets/exclusion_example.png)

## 輸入參數 {#input-parameters}

* tableName
* 綱要

每個入站事件都必須指定由這些參數定義的目標。

## 輸出參數 {#output-parameters}

* tableName
* 綱要
* recCount

這組三個值可識別排除後產生的目標。 **[!UICONTROL tableName]** 是記錄目標標識符的表的名稱， **[!UICONTROL schema]** 是母體的綱要（通常為nms:recipient）和 **[!UICONTROL recCount]** 是表格中的元素數。

與補體相關聯的轉變具有相同的參數。
