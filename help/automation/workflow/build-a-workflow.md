---
product: campaign
title: 建置工作流程
description: 了解如何建立工作流程
feature: Workflows
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 4%

---

# 建置工作流程 {#build-a-workflow}

## 建立新工作流程 {#create-a-new-workflow}

工作流程建立流程取決於工作流程類型。 您可以：

* 建立 [目標工作流程](#targeting-workflows) 從 **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** 或 **[!UICONTROL Profiles and Targets]** 頁簽，通過 **[!UICONTROL Targeting workflows]** 頁簽。

   ![](assets/create-targeting-wf.png)

* 建立 [行銷活動工作流程](#campaign-workflows) 從 **[!UICONTROL Targeting and workflows]** 行銷活動的標籤

* 建立 [技術工作流程](#technical-workflows) 從 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** 的子節點。 最佳實務是建立特定的工作流程資料夾，以儲存您的技術工作流程。

按一下 **[!UICONTROL New]** 按鈕。

![](assets/create_a_wf_icon.png)

輸入標籤，然後按一下 **[!UICONTROL Save]**.

## 新增及連結活動 {#add-and-link-activities}

您現在必須定義各種活動，並將它們在圖表中連結在一起。在設定的這個階段，我們會看到圖表標籤和工作流程狀態（正在編輯）。 窗口的下部僅用於編輯圖。 它包含工具列、活動浮動視窗（位於左側），以及圖表本身（位於右側）。

![](assets/new-workflow-2.png)

>[!NOTE]
>
>如果浮動視窗未顯示，請按一下工作流程工具列上的第一個按鈕以顯示它。

活動會依浮動視窗不同標籤中的類別分組。 可用的標籤和活動可能會依工作流程類型（技術、鎖定目標或行銷活動工作流程）而有所不同。

* 第一個標籤包含定位和資料操控活動。 這些活動在 [目標定位活動](targeting-activities.md).
* 第二個索引標籤包含排程活動，主要用於協調其他活動。 這些活動在 [流量控制活動](flow-control-activities.md).
* 第三個索引標籤包含可在工作流程中使用的工具和動作。 這些活動在 [動作活動](action-activities.md).
* 第四個索引標籤包含依賴指定事件的活動，例如收到電子郵件或檔案到達伺服器。 這些活動在 [事件活動](event-activities.md).

建立圖表的方式

1. 在浮動視窗中選取活動，並使用拖放操作將其移至圖表，以新增活動。

   新增 **開始** 活動，然後 **傳送** 圖表上的活動。

   ![](assets/new-workflow-3.png)

1. 拖曳 **開始** 活動轉變並將其拖放到 **傳送** 活動。

   ![](assets/new-workflow-4.png)

   您可以將新活動放置在轉變結束時，自動將活動連結至上一個活動。

1. 新增您需要的活動，並將它們連結在一起，如下圖所示。

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>您可以在相同的工作流程中複製和貼上活動。 不過，我們不建議跨不同的工作流程複製貼上活動。 某些附加至活動（例如傳送和排程器）的設定在執行目標工作流程時可能會導致衝突和錯誤。 反之，我們建議您  **複製** 工作流程。 如需詳細資訊，請參閱 [複製工作流程](#duplicate-workflows).

您可以使用下列元素來變更圖表的顯示和配置：

* **使用工具列**

   圖表編輯工具列可讓您存取工作流程的版面和執行功能。

   ![](assets/wf-toolbar.png)

   這可讓您調整編輯工具的版面：顯示浮動視窗，以及圖形對象的概述、大小和對齊方式。

   ![](assets/s_user_segmentation_toolbar.png)

   與進度和記錄顯示相關的圖示在以下章節中詳細說明：

   * [顯示進度](monitor-workflow-execution.md#displaying-progress)
   * [顯示日誌](monitor-workflow-execution.md#displaying-logs)

* **對象對齊**

   若要對齊圖示，請選取圖示並按一下 **[!UICONTROL Align vertically]** 或 **[!UICONTROL Align horizontally]** 表徵圖。

   使用 **CTRL** 鍵，以選取數個分散的活動或取消選取一或多個活動。 按一下圖表背景，取消選取所有項目。

* **影像管理**

   您可以自訂圖表的背景影像，以及與各種活動相關的背景影像。 請參閱 [變更活動影像](change-activity-images.md).

## 設定活動 {#configure-activities}

連按兩下要設定的活動，或以滑鼠右鍵按一下並選取 **[!UICONTROL Open...]**.

>[!NOTE]
>
>行銷活動工作流程活動在 [本節](activities.md).

第一個索引標籤包含基本設定。 此 **[!UICONTROL Advanced]** 索引標籤包含其他參數，這些參數尤其用於在遇到錯誤時定義行為、指定活動的執行持續時間以及輸入初始化指令碼。

為了更好地了解活動，並提高工作流的可讀性，您可以在活動中輸入注釋。

![](assets/example1-comment.png)

當運算子捲動到活動上時，會自動顯示這些註解。

![](assets/example2-comment.png)


## 工作流程範本 {#workflow-templates}

工作流程範本包含屬性的整體設定，以及圖表中串連的可能範圍活動。 此設定可重複用於建立包含特定數量之預先設定元素的新工作流程

您可以根據現有範本建立新的工作流程範本，或直接將工作流程變更為範本。

工作流程範本會儲存在 **[!UICONTROL Resources > Templates > Workflow templates]** 的子節點。

除了通常的工作流屬性外，模板屬性還允許您為基於此模板建立的工作流指定執行檔案。

![](assets/wf-template-properties.png)

## 複製工作流程 {#duplicate-workflows}

您可以複製不同類型的工作流程。 複製之後，不會將工作流程的修改轉存到工作流程的副本中。

>[!CAUTION]
>
>複製貼上功能可在工作流程中使用，但建議您使用 **複製**. 複製活動後，會保留其整個設定。 對於傳送活動（電子郵件、簡訊、推播通知……），附加至活動的傳送物件也會複製，而這可能導致當機。

1. 以滑鼠右鍵按一下工作流程。
1. 按一下 **複製**.

   ![](assets/duplicate-workflows.png)

1. 在工作流程視窗中，變更工作流程標籤。
1. 按一下 **儲存**.

促銷活動檢視不直接提供重複功能。

不過，您可以建立檢視來顯示執行個體上的所有工作流程。 在此檢視中，您可以使用 **複製到**.

**建立檢視**

1. 在 **瀏覽器**，移至在中建立檢視所需的資料夾。
1. 按一下滑鼠右鍵，然後前往 **新增資料夾** > **程式**，選取 **工作流程**.

   ![](assets/add-new-folder-workflows.png)

新資料夾 **工作流程** 中所有規則的URL區段。

1. 按一下滑鼠右鍵並選取 **屬性**.
1. 在 **限制** 頁簽，啟用 **此資料夾為檢視** 選項，然後按一下 **儲存**.

   ![](assets/folder-is-a-view.png)

資料夾現在會填入您執行個體的所有工作流程。

**複製促銷活動工作流程**

1. 在工作流程檢視中選取促銷活動工作流程。
1. 按一下右鍵 **複製到**.
1. 更改其標籤。
1. 按一下 **儲存**.

您可以在工作流程檢視中查看重複的工作流程。
