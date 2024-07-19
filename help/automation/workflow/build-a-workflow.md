---
product: campaign
title: 建置工作流程
description: 瞭解如何建立工作流程
feature: Workflows
role: User
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 166fe487aa169f47f9da86c2990acb1f6dff430e
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 1%

---

# 建置工作流程 {#build-a-workflow}

## 建立新的工作流程 {#create-a-new-workflow}

工作流程建立流程取決於工作流程的型別。 您可以：

* 從Explorer的&#x200B;**[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]**&#x200B;節點或首頁的&#x200B;**[!UICONTROL Profiles and Targets]**&#x200B;索引標籤，透過&#x200B;**[!UICONTROL Targeting workflows]**&#x200B;子索引標籤建立[目標工作流程](#targeting-workflows)。

  ![](assets/create-targeting-wf.png)

* 從行銷活動的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;索引標籤建立[行銷活動工作流程](#campaign-workflows)

* 從總管的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**&#x200B;節點建立[技術工作流程](#technical-workflows)。 最佳實務是建立特定的工作流程資料夾，以儲存您的技術工作流程。

按一下位於工作流程清單上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。

![](assets/create_a_wf_icon.png)

輸入標籤並按一下&#x200B;**[!UICONTROL Save]**。

## 新增和連結活動 {#add-and-link-activities}

您現在必須定義各種活動，並將它們在圖表中連結在一起。 在設定的這個階段，我們可以看到圖表標籤和工作流程狀態（正在編輯）。 視窗的下半部僅用於編輯圖表。 它包含工具列、活動浮動面板（位於左側）和圖表本身（位於右側）。

![](assets/new-workflow-2.png)

>[!NOTE]
>
>如果浮動視窗未顯示，請按一下工作流程工具列中的第一個按鈕以顯示它。

活動會依浮動視窗的不同標籤中的類別分組。 可用的標籤和活動會依工作流程型別（技術、目標定位或行銷活動工作流程）而有所不同。

* 第一個標籤包含定位和資料操作活動。 [目標定位活動](targeting-activities.md)中會詳細說明這些活動。
* 第二個索引標籤包含排程活動，主要用於協調其他活動。 在[流量控制活動](flow-control-activities.md)中會詳細說明這些活動。
* 第三個標籤包含可用於工作流程的工具和動作。 在[動作活動](action-activities.md)中會詳細說明這些活動。
* 第四個索引標籤包含取決於指定事件的活動，例如收到電子郵件或檔案抵達伺服器。 [事件活動](event-activities.md)中會詳細說明這些活動。

建立圖表

1. 在浮動視窗中選取活動，並使用拖放操作將其移至圖表，以新增活動。

   在圖表上新增&#x200B;**開始**&#x200B;活動，然後新增&#x200B;**傳遞**&#x200B;活動。

   ![](assets/new-workflow-3.png)

1. 將&#x200B;**開始**&#x200B;活動轉變拖曳至&#x200B;**傳遞**&#x200B;活動，將活動連結在一起。

   ![](assets/new-workflow-4.png)

   您可以將新活動放在轉變的結尾處，自動將活動連結至上一個活動。

1. 新增您需要的活動，並將它們連結在一起，如下圖所示。

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>您可以在相同的工作流程中複製和貼上活動。 不過，我們不建議跨不同的工作流程複製貼上活動。 某些附加至傳送和排程器等活動的設定，在執行目標工作流程時可能會導致衝突和錯誤。 我們建議您&#x200B;**複製**&#x200B;工作流程。 如需詳細資訊，請參閱[重複的工作流程](#duplicate-workflows)。

您可以使用下列元素來變更圖表的顯示和版面配置：

* **使用工具列**

  圖表編輯工具列可讓您存取工作流程的佈局和執行功能。

  ![](assets/wf-toolbar.png)

  這可讓您調整編輯工具的版面：顯示浮動視窗以及圖形物件的概觀、大小和對齊。

  ![](assets/s_user_segmentation_toolbar.png)

  以下各節詳細介紹了與進度和日誌顯示相關的圖示：

   * [顯示進度](monitor-workflow-execution.md#displaying-progress)
   * [顯示記錄](monitor-workflow-execution.md#displaying-logs)

* **物件對齊方式**

  若要對齊圖示，請選取圖示並按一下&#x200B;**[!UICONTROL Align vertically]**&#x200B;或&#x200B;**[!UICONTROL Align horizontally]**&#x200B;圖示。

  使用&#x200B;**CTRL**&#x200B;鍵選取數個分散的活動，或取消選取一或多個活動。 按一下圖表背景以取消選取所有專案。

* **影像管理**

  您可以自訂圖表的背景影像以及與各種活動相關的影像。 請參閱[變更活動影像](change-activity-images.md)。

## 設定活動 {#configure-activities}

連按兩下活動以進行設定，或按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Open...]**。

>[!NOTE]
>
>行銷活動工作流程活動在[本節](activities.md)中有詳細說明。

第一個索引標籤包含基本設定。 **[!UICONTROL Advanced]**&#x200B;索引標籤包含其他引數，這些引數特別用於定義發生錯誤時的行為、指定活動的執行持續時間以及輸入初始化指令碼。

為了更清楚瞭解活動及改善工作流程易讀性，您可以在活動中輸入註解。

![](assets/example1-comment.png)

當操作者捲動到活動上時，這些註解會自動顯示。

![](assets/example2-comment.png)


## 工作流程範本 {#workflow-templates}

工作流程範本包含屬性的整體設定，且可能包含串連在圖表中的一系列活動。 此設定可重複用於建立包含特定數量之預先設定元素的新工作流程

您可以根據現有範本建立新的工作流程範本，或直接將工作流程變更為範本。

工作流程範本儲存在總管的&#x200B;**[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;節點中。

除了一般的工作流程屬性外，範本屬性可讓您為根據此範本建立的工作流程指定執行檔案。

![](assets/wf-template-properties.png)

## 複製工作流程 {#duplicate-workflows}

您可以複製不同型別的工作流程。 複製之後，不會將工作流程的修改轉存到工作流程的副本中。

Adobe建議複製工作流程，而非執行活動的複製/貼上。 複製活動時，會保留其所有設定。 若是管道活動，也會複製與活動相關聯的傳送物件，這可能會造成重大問題。

1. 在工作流程上按一下右鍵。
1. 按一下&#x200B;**複製**。

   ![](assets/duplicate-workflows.png)

1. 在工作流程視窗中，變更工作流程標籤。
1. 按一下「**儲存**」。

