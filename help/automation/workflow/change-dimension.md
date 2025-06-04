---
product: campaign
title: 變更工作流程中的維度
description: 瞭解如何使用變更維度活動
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# 變更維度{#change-dimension}

在建立對象時，請使用&#x200B;**[!UICONTROL Change dimension]**&#x200B;活動來變更目標維度。 此活動會根據資料範本和輸入維度移動軸。 例如，從「合約」維度切換至「客戶」維度。

您也可以使用此活動來定義新目標的其他欄，並定義重複資料刪除的條件。

>[!IMPORTANT]
>
>請注意，不應將&#x200B;**[!UICONTROL Change Dimension]**&#x200B;和&#x200B;**[!UICONTROL Change Data source]**&#x200B;活動新增到一列。 如果您需要連續使用兩個活動，請務必在它們之間包含&#x200B;**[!UICONTROL Enrichement]**&#x200B;活動。 這可確保正確執行並防止潛在的衝突或錯誤。

若要設定&#x200B;**[!UICONTROL Change dimension]**&#x200B;活動，請套用下列步驟：

1. 透過&#x200B;**[!UICONTROL Change dimension]**&#x200B;欄位選取新的目標維度。

   ![](assets/s_user_change_dimension_param1.png)

1. 在尺寸變更期間，您可以保留所有元素或選取要保留在輸出中的元素。 在下列範例中，最大值為 重複專案數設為2。

   ![](assets/s_user_change_dimension_limit.png)

   當您選擇只保留一個記錄時，會在工作結構描述中顯示集合：此集合代表最終結果中未鎖定目標的所有記錄（因為只保留一個記錄）。 如同其他所有集合，這個集合可讓您計算彙總或復原欄中的資訊。

   例如，如果您將&#x200B;**[!UICONTROL Customers]**&#x200B;維度變更為&#x200B;**[!UICONTROL Recipients]**&#x200B;維度，則可將目標鎖定在特定商店的客戶，同時新增購買的次數。

1. 如果您選擇不保留所有這些資訊，您可以設定重複管理模式。

   ![](assets/s_user_change_dimension_param2.png)

   藍色箭頭可讓您定義重複的處理優先順序。

   在上述範例中，收件者會先在其電子郵件地址上刪除重複專案，然後視需要在其帳號上刪除重複專案。

1. **[!UICONTROL Result]**&#x200B;索引標籤可讓您新增其他資訊。

   例如，您可以使用&#x200B;**Substring**&#x200B;型別函式，根據郵遞區號復原縣。 操作步驟：

   * 按一下&#x200B;**[!UICONTROL Add data...]**&#x200B;連結並選取&#x200B;**[!UICONTROL Data linked to the filtering dimension]**。

     ![](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >如需建立和管理其他資料行的詳細資訊，請參閱[新增資料](query.md#add-data)。

   * 選取前一個目標維度（在軸切換前），並在收件者的&#x200B;**[!UICONTROL Location]**&#x200B;子樹狀結構中選取&#x200B;**[!UICONTROL Zip Code]**，然後按一下&#x200B;**[!UICONTROL Edit expression]**。

     ![](assets/wf_change-dimension_sample_02.png)

   * 按一下&#x200B;**[!UICONTROL Advanced selection]**&#x200B;並選擇&#x200B;**[!UICONTROL Edit the formula using an expression]**。

     ![](assets/wf_change-dimension_sample_03.png)

   * 使用清單中提供的函式並指定要執行的計算。

     ![](assets/wf_change-dimension_sample_04.png)

   * 最後，輸入您剛建立之欄的標籤。

     ![](assets/wf_change-dimension_sample_05.png)

1. 執行工作流程以檢視此設定的結果。 比較變更維度活動前後表格中的資料，並比較工作流程表格的結構，如下列範例所示：

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
