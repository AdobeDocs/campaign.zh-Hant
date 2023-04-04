---
product: campaign
title: 變更工作流程中的維度
description: 了解如何使用變更維度活動
feature: Workflows, Targeting Activity
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 變更維度{#change-dimension}

使用 **[!UICONTROL Change dimension]** 活動，在您建立對象時變更目標維度。 此活動會根據資料範本和輸入維度來移動軸。 例如，您從「合約」維度切換為「用戶端」維度。

您也可以使用此活動來定義新目標的其他欄，並定義重複資料刪除條件。

若要設定 **[!UICONTROL Change dimension]** 活動，請套用下列步驟：

1. 透過 **[!UICONTROL Change dimension]** 欄位。

   ![](assets/s_user_change_dimension_param1.png)

1. 在尺寸更改期間，您可以保留所有元素或選擇要保留在輸出中的元素。 在下列範例中，最大值為。 重複項目數設為2。

   ![](assets/s_user_change_dimension_limit.png)

   當您選擇僅保留一條記錄時，工作架構中會顯示一個集合：此集合表示在最終結果中不會定位的所有記錄（因為只保留一個記錄）。 與所有其他集合一樣，此集合可讓您計算欄中的匯總或復原資訊。

   例如，如果您變更 **[!UICONTROL Customers]** 維度 **[!UICONTROL Recipients]** 維度中，則可以在新增購買次數時，鎖定特定商店的客戶。

1. 如果您選擇不保留所有這些資訊，則可以配置重複管理模式。

   ![](assets/s_user_change_dimension_param2.png)

   藍色箭頭可讓您定義重複的處理優先順序。

   在上述範例中，收件者的電子郵件地址會先刪除重複項目，然後視需要刪除其帳號。

1. 此 **[!UICONTROL Result]** 標籤可讓您新增其他資訊。

   例如，您可以使用 **子字串** 類型函式。 操作步驟：

   * 按一下 **[!UICONTROL Add data...]** 連結和選取 **[!UICONTROL Data linked to the filtering dimension]**.

      ![](assets/wf_change-dimension_sample_01.png)

      >[!NOTE]
      >
      >有關建立和管理其他列的資訊，請參閱 [新增資料](query.md#add-data).

   * 選取上一個目標維度（軸切換前），然後選取 **[!UICONTROL Zip Code]** 收件者 **[!UICONTROL Location]** 子樹，然後按一下 **[!UICONTROL Edit expression]**.

      ![](assets/wf_change-dimension_sample_02.png)

   * 按一下 **[!UICONTROL Advanced selection]** 選擇 **[!UICONTROL Edit the formula using an expression]**.

      ![](assets/wf_change-dimension_sample_03.png)

   * 使用清單中提供的函式並指定要執行的計算。

      ![](assets/wf_change-dimension_sample_04.png)

   * 最後，輸入剛建立的列的標籤。

      ![](assets/wf_change-dimension_sample_05.png)

1. 執行工作流以查看此配置的結果。 比較變更維度活動前後表格中的資料，並比較工作流程表格的結構，如下列範例所示：

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
