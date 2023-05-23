---
product: campaign
title: 建置工作流程
description: 瞭解如何構建工作流
feature: Workflows
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 4%

---

# 建置工作流程 {#build-a-workflow}

## 建立新工作流 {#create-a-new-workflow}

工作流建立流取決於工作流類型。 您可以：

* 建立 [目標工作流](#targeting-workflows) 從 **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** 或 **[!UICONTROL Profiles and Targets]** 頁籤 **[!UICONTROL Targeting workflows]** 的子菜單。

   ![](assets/create-targeting-wf.png)

* 建立 [市場活動工作流](#campaign-workflows) 從 **[!UICONTROL Targeting and workflows]** 頁籤

* 建立 [技術工作流](#technical-workflows) 從 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** 的子菜單。 最佳做法是建立特定的工作流資料夾以保存技術工作流。

按一下 **[!UICONTROL New]** 按鈕。

![](assets/create_a_wf_icon.png)

輸入標籤，然後按一下 **[!UICONTROL Save]**。

## 添加和連結活動 {#add-and-link-activities}

您現在必須定義各種活動，並將它們在圖表中連結在一起。在此配置階段，我們可以看到表徵圖和工作流狀態（正在編輯）。 窗口的下部僅用於編輯圖。 它包含工具欄、活動元件面板（在左側）和圖本身（在右側）。

![](assets/new-workflow-2.png)

>[!NOTE]
>
>如果未顯示調色板，請按一下工作流工具欄上的第一個按鈕以顯示調色板。

活動按元件面板不同頁籤中的類別分組。 可用的標籤和活動可能因工作流類型（技術、目標或市場活動工作流）而異。

* 第一個頁籤包含目標和資料操作活動。 這些活動在 [目標活動](targeting-activities.md)。
* 第二個頁籤包含計畫活動，這些活動主要用於協調其他活動。 這些活動在 [流控制活動](flow-control-activities.md)。
* 第三個頁籤包含可在工作流中使用的工具和操作。 這些活動在 [行動活動](action-activities.md)。
* 第四個頁籤包含依賴於給定事件的活動，如接收電子郵件或檔案到達伺服器。 這些活動在 [活動](event-activities.md)。

建立圖

1. 通過在調色板中選擇活動並使用拖放操作將其移動到圖來添加活動。

   添加 **開始** 活動，然後 **交貨** 表徵圖

   ![](assets/new-workflow-3.png)

1. 通過拖動 **開始** 活動轉換並將其放到 **交貨** 的子菜單。

   ![](assets/new-workflow-4.png)

   通過將新活動置於轉換結束，可以自動將活動連結到上一個活動。

1. 添加所需活動並將它們連結在一起，如下圖所示。

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>您可以在同一工作流中複製和貼上活動。 但是，我們不建議跨不同的工作流複製貼上活動。 附加到「交貨」和「計畫程式」等活動的某些設定在執行目標工作流時可能會導致衝突和錯誤。 相反，我們建議你  **重複** 工作流。 有關詳細資訊，請參見 [複製工作流](#duplicate-workflows)。

可以使用以下元素更改圖表的顯示和佈局：

* **使用工具欄**

   圖編輯工具欄允許您訪問工作流的佈局和執行功能。

   ![](assets/wf-toolbar.png)

   這允許您調整編輯工具的佈局：調色板的顯示以及圖形對象的概述、大小和對齊方式。

   ![](assets/s_user_segmentation_toolbar.png)

   與進度和日誌顯示相關的表徵圖將在以下各節中詳細介紹：

   * [顯示進度](monitor-workflow-execution.md#displaying-progress)
   * [顯示日誌](monitor-workflow-execution.md#displaying-logs)

* **對象對齊**

   要對齊表徵圖，請選中表徵圖，然後按一下 **[!UICONTROL Align vertically]** 或 **[!UICONTROL Align horizontally]** 表徵圖

   使用 **CTRL鍵** 鍵，以選擇多個分散的活動或取消選擇一個或多個活動。 按一下圖背景以取消選擇所有內容。

* **映像管理**

   可以定製圖的背景影像以及與各種活動相關的背景影像。 請參閱 [更改活動映像](change-activity-images.md)。

## 配置活動 {#configure-activities}

按兩下某個活動進行配置，或按一下右鍵並選擇 **[!UICONTROL Open...]**。

>[!NOTE]
>
>市場活動工作流活動的詳細資訊請參閱 [此部分](activities.md)。

第一個頁籤包含基本配置。 的 **[!UICONTROL Advanced]** 頁籤包含附加參數，這些參數在遇到錯誤時用於定義行為、指定活動的執行持續時間以及輸入初始化指令碼。

為了更好地瞭解活動並提高工作流的可讀性，您可以在活動中輸入注釋。

![](assets/example1-comment.png)

當運算子滾動到活動上時，這些注釋會自動顯示。

![](assets/example2-comment.png)


## 工作流程範本 {#workflow-templates}

工作流模板包含屬性的總體配置以及可能連接在圖中的一系列活動。 此配置可重複使用，用於建立包含特定數量的預配置元素的新工作流

您可以基於現有模板建立新的工作流模板，或直接將工作流更改為模板。

工作流模板儲存在 **[!UICONTROL Resources > Templates > Workflow templates]** 的子菜單。

除了通常的工作流屬性外，模板屬性還允許您為基於此模板建立的工作流指定執行檔案。

![](assets/wf-template-properties.png)

## 複製工作流 {#duplicate-workflows}

您可以複製不同類型的工作流。 複製之後，不會將工作流程的修改轉存到工作流程的副本中。

>[!CAUTION]
>
>複製貼上在工作流中可用，但我們建議您使用 **重複**。 複製活動後，將保留其整個配置。 對於傳遞活動（電子郵件、SMS、推送通知……），還會複製附加到該活動的傳遞對象，這可能導致崩潰。

1. 按一下右鍵工作流。
1. 按一下 **重複**。

   ![](assets/duplicate-workflows.png)

1. 在工作流窗口中，更改工作流標籤。
1. 按一下「**儲存**」。

市場活動視圖中不直接提供重複功能。

但是，您可以建立一個視圖來顯示實例上的所有工作流。 在此視圖中，您可以使用 **複製到**。

**建立視圖**

1. 在 **瀏覽器**，轉到在中建立視圖所需的資料夾。
1. 按一下右鍵並轉到 **添加新資料夾** > **進程**&#x200B;選中 **工作流**。

   ![](assets/add-new-folder-workflows.png)

新資料夾 **工作流** 的子菜單。

1. 按一下右鍵並選擇 **屬性**。
1. 在 **限制** 頁籤 **此資料夾是視圖** 選項 **保存**。

   ![](assets/folder-is-a-view.png)

現在，資料夾將填充實例的所有工作流。

**複製市場活動工作流**

1. 在工作流視圖中選擇市場活動工作流。
1. 按一下右鍵 **複製到**。
1. 更改其標籤。
1. 按一下「**儲存**」。

您可以在工作流視圖中查看重複的工作流。
