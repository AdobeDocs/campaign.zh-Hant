---
product: campaign
title: 聯合
description: 進一步瞭解聯合工作流程活動
feature: Workflows, Targeting Activity
exl-id: 4109e198-bf9d-4dd2-92a1-16bbadbe30e8
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# 聯合{#union}

**[!UICONTROL Union]**&#x200B;會將數個入站活動的結果群組在單一目標中。 建立目標時會收到所有結果：因此，必須完成所有先前的活動才能執行聯合。

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>有關設定和使用&#x200B;**[!UICONTROL Union]**&#x200B;活動的詳細資訊，請參閱[此頁面](targeting-workflows.md#combining-several-targets--union-)。

## 聯合範例 {#union-example}

在下列範例中，兩個查詢的結果已合併，以更新清單。 這兩個查詢會鎖定收件者。 因此，結果會以相同的表格為基礎。

1. 在兩個查詢之後且在清單的更新型別活動之前直接插入&#x200B;**[!UICONTROL Union]** -type活動，然後開啟它。
1. 您可以輸入標籤。
1. 選取&#x200B;**[!UICONTROL Keys only]**&#x200B;調解方法，因為在此範例中，由查詢產生的母體包含一致的資料。
1. 如果您已為查詢新增其他資料，您可以決定只保留共用的資料。
1. 如果要限制最終母體的大小，請核取&#x200B;**[!UICONTROL Limit size of generated population]**&#x200B;選項。

   輸入最大收件者人數，並選取母體優先的查詢，以指定此最終數字。

1. 核准&#x200B;**[!UICONTROL Union]**&#x200B;活動，然後設定[清單更新](list-update.md)活動。
1. 啟動工作流程。 會顯示結果數量，並建立或更新清單更新活動中定義的清單。 此清單包含兩個查詢的收件者集，或如適用，包含上一步驟中定義的號碼。

   ![](assets/union_example.png)

## 輸入引數 {#input-parameters}

* tableName
* 結構描述

每個傳入事件都必須指定由這些引數定義的目標。

## 輸出引數 {#output-parameters}

* tableName
* 結構描述
* recCount

這組三個值會識別聯合產生的目標。 **[!UICONTROL tableName]**&#x200B;是記錄目標識別碼的資料表的名稱，**[!UICONTROL schema]**&#x200B;是母體的結構描述（通常是nms：recipient），而&#x200B;**[!UICONTROL recCount]**&#x200B;是資料表中的元素數目。
