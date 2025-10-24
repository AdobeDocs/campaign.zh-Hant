---
product: campaign
title: 行銷活動目標對象
description: 瞭解如何定義行銷活動的對象
feature: Campaigns, Audiences
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 70a63632-f66d-40f2-806d-bde89303936a
source-git-commit: 26829656f8e06434ca3207c0c7b62ba907765972
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# 選取行銷活動的客群 {#marketing-campaign-deliveries}

在行銷活動中，您可以針對每次傳送定義：

* 目標對象。 您可以傳送訊息給收件者[的](#send-to-a-group)清單，或在工作流程[中建立](#build-the-main-target-in-a-workflow)對象
* 控制組。 您可以[新增控制群組](#add-a-control-group)，以監視郵件傳遞後的收件者行為
* 種子地址 — 在[本節](../../v8/audiences/test-profiles.md)中瞭解更多。

此資訊的部分繼承自[行銷活動範本](marketing-campaign-templates.md#campaign-templates)。

<!--
To build the delivery target, you can define filtering criteria for the recipients in the database. This recipient selection mode is presented in [this section](../../delivery/using/steps-defining-the-target-population.md).
-->

## 傳送至群組{#send-to-a-group}

您可以將母體匯入清單，然後在傳遞中鎖定此清單。 要執行此操作，請遵循下列步驟：

1. 編輯傳遞並按一下&#x200B;**[!UICONTROL To]**&#x200B;連結以變更目標母體。
1. 在&#x200B;**[!UICONTROL Main target]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Defined via the database]**&#x200B;選項並按一下&#x200B;**[!UICONTROL Add]**&#x200B;以選取收件者。

   ![](assets/select-main-target.png)

1. 選擇&#x200B;**[!UICONTROL A list of recipients]**。

   ![](assets/target-a-list.png)


1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以選取清單。

   ![](assets/select-the-list.png)

   您可以新增篩選條件來縮小目標範圍。

1. 定義所有條件後，按一下&#x200B;**[!UICONTROL Finish]**，然後儲存主要目標。

## 在行銷活動工作流程中建立對象 {#build-the-main-target-in-a-workflow}

傳遞的主要目標也可以在行銷活動工作流程中定義：此圖形環境可讓您使用查詢、測試和運運算元來建立目標：聯合、重複資料刪除、共用等。

>[!IMPORTANT]
>
>在行銷活動中新增的工作流程不可超過28個。 超過此限制後，介面中不會顯示其他工作流程，而且可能會產生錯誤。

### 建立工作流程 {#create-a-targeting-workflow}

您可以透過工作流程中圖形順序的篩選條件組合來建立目標定位。 您可以建立母體和子母體，並根據您的需求將其設為目標。 若要顯示工作流程編輯器，請按一下行銷活動控制面板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;標籤。

![](assets/targeting-and-wf-tab.png)

透過置於工作流程中的一或多個查詢，會從Adobe Campaign資料庫擷取目標母體。 瞭解如何在[本節](../workflow/query.md)中建置查詢。

您可以透過「聯合」、「交集」、「共用」、「排除」等方塊啟動查詢及共用母體。

從工作區左側的清單中選取物件，並連結它們以建構目標。

![](assets/campaign-wf.png)

在圖表中，連結圖表中目標建構所需的目標定位和排程查詢。 您可以在建構期間執行目標定位，以檢查從資料庫擷取的母體。

>[!NOTE]
>
>定義查詢的範例和程式在[本節](../workflow/query.md)中有詳細說明。

編輯器的左側區段包含代表活動的圖形物件庫。 第一個標籤包含目標定位活動，第二個標籤則包含流量控制活動，這些活動偶爾會用來協調目標定位活動。

目標工作流程執行和格式化功能可透過圖表編輯器工具列存取。

![](assets/wf-diagram.png)

>[!NOTE]
>
>可用來建置圖表的活動以及所有顯示和配置功能都在[本節](../workflow/about-workflows.md)中詳細說明。

您可以為單一行銷活動建立數個目標工作流程。 若要新增工作流程：

1. 移至工作流程建立區域的左上角區段，按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL Add]**。 您也可以使用位於此區域上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。

   ![](assets/add-a-wf.png)

1. 選取&#x200B;**[!UICONTROL New workflow]**&#x200B;範本並命名此工作流程。
1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以確認建立工作流程，然後建立此工作流程的圖表。

### 執行工作流程 {#execute-a-workflow}

目標工作流程可以透過工具列中的&#x200B;**[!UICONTROL Start]**&#x200B;按鈕手動啟動，但前提是您擁有適當的許可權。

可以按照排程（排程器）或事件（外部訊號、檔案匯入等）將目標設定為自動執行。

與執行目標工作流程相關的動作（啟動、停止、暫停等）為&#x200B;**非同步**&#x200B;程式：命令已儲存，一旦伺服器可供套用命令就會生效。

工具列圖示可讓您執行定位工作流程的相關動作。

* 啟動或重新啟動

   * **[!UICONTROL Start]**&#x200B;圖示可讓您啟動目標定位工作流程。 當您按一下此圖示時，所有沒有輸入轉變的活動都會啟動（端點跳轉除外）。

     ![](assets/start.png)

     伺服器會將要求列入考量，如其狀態所顯示： **[!UICONTROL Start as soon as possible]**。

   * 您可以透過適當的工具列圖示重新啟動目標定位工作流程。 如果&#x200B;**[!UICONTROL Start]**&#x200B;圖示無法使用（例如正在停止定位工作流程），此命令可能會很有用。 在此情況下，請按一下&#x200B;**[!UICONTROL Restart]**&#x200B;圖示以預期重新啟動。 伺服器會將要求列入考量，因為其狀態顯示為： **[!UICONTROL Restart requested]**。

* 停止或暫停

   * 工具列圖示可讓您停止或暫停進行中的目標定位工作流程。

     當您按一下&#x200B;**[!UICONTROL Pause]**&#x200B;時，進行中的作業&#x200B;**[!UICONTROL are not]**&#x200B;已暫停，但在下次重新啟動之前，不會啟動其他活動。

     ![](assets/pause.png)

     伺服器會考慮該命令，因為其狀態顯示為： **[!UICONTROL Pause requested]**。

     您也可以在執行目標工作流程達到特定活動時自動暫停該工作流程。 若要這麼做，請以滑鼠右鍵按一下要暫停目標定位工作流程的活動，然後選取&#x200B;**[!UICONTROL Enable but do not execute]**。

     ![](assets/donotexecute.png)

     此設定會以特殊圖示顯示。

     ![](assets/pause_activity.png)

     >[!NOTE]
     >
     >在進階目標定位行銷活動設計和測試階段，此選項非常有用。

     按一下&#x200B;**[!UICONTROL Start]**&#x200B;以繼續執行。

   * 按一下&#x200B;**[!UICONTROL Stop]**&#x200B;圖示可停止進行中的執行。

     ![](assets/stop.png)

     伺服器會考慮該命令，因為其狀態顯示為： **[!UICONTROL Stop requested]**。

  您也可以在執行到達活動時自動停止目標定位工作流程。 若要這麼做，請以滑鼠右鍵按一下將停止目標定位工作流程的活動，然後選取&#x200B;**[!UICONTROL Do not activate]**。

  ![](assets/donotactivate.png)

  此設定會以特殊圖示顯示。

  ![](assets/unactivation.png)


  >[!NOTE]
  >
  >在進階目標定位行銷活動設計和測試階段，此選項非常有用。

* 無條件停止

  在Explorer中，選取&#x200B;**[!UICONTROL Administration > Production > Object created automatically > Campaign workflows]**&#x200B;以存取並處理每個行銷活動工作流程。

  您可以按一下&#x200B;**[!UICONTROL Actions]**&#x200B;圖示並選取&#x200B;**[!UICONTROL Unconditional]**&#x200B;停止，無條件停止工作流程。 此動作會終止您的行銷活動工作流程。

  ![](assets/stop_unconditional.png)

  >[!CAUTION]
  >
  >管理員使用者僅限無條件停止。

## 新增控制組 {#add-a-control-group}

控制組是不接收傳遞的母體；它可用來追蹤傳遞後的行為，以及行銷活動影響，方法是與接收傳遞的目標母體的行為進行比較。

控制組可從主要目標擷取及/或來自特定群組或查詢。

>[!CAUTION]
>
>從外部檔案載入目標母體時，無法使用控制組。

### 啟用行銷活動的控制組 {#activate-the-control-group-for-a-campaign}

您可以在行銷活動層級定義控制組，在這種情況下，控制組將套用至相關行銷活動的每個傳送。

1. 編輯相關行銷活動，然後按一下「**[!UICONTROL Edit]**」標籤。
1. 按一下 **[!UICONTROL Advanced campaign parameters...]**。

   ![](assets/enable-control-group.png)

1. 選取 **[!UICONTROL Enable and edit control group configuration]** 選項。
1. 按一下&#x200B;**[!UICONTROL Edit...]**&#x200B;設定控制組。

   ![](assets/edit-control-group.png)

完整程式在[此區段](#extract-the-control-group-from-the-main-target)中有詳細說明。 在[本節](#add-a-population)中進一步瞭解控制組。

### 啟用傳遞的控制組 {#activate-the-control-group-for-a-delivery}

您可以在傳送層級定義控制組，此時控制組將套用至相關行銷活動的每個傳送。

根據預設，在行銷活動層級定義的控制群組設定會套用至該行銷活動的每次傳遞。 不過，您可以為個別傳遞調整控制組。

>[!NOTE]
>
>如果您已定義行銷活動的控制組，且還將其設定為連結至此行銷活動的傳送，則只會套用為傳送定義的控制組。

1. 編輯相關的傳遞，然後按一下&#x200B;**[!UICONTROL To]**&#x200B;連結。
1. 按一下&#x200B;**[!UICONTROL Control group]**&#x200B;標籤，然後選取&#x200B;**[!UICONTROL Enable and edit control group configuration]**。

   ![](assets/enable-control-group-for-a-delivery.png)

1. 按一下&#x200B;**[!UICONTROL Edit...]**&#x200B;設定控制組。

完整程式在[此區段](#extract-the-control-group-from-the-main-target)中有詳細說明。

### 使用新母體作為控制組 {#add-a-population}

您可對控制組使用特定人口。 在這種情況下，請在相關欄位中選取要作為控制組的清單。

此母體可能來自收件者清單，或者您可以透過特定查詢加以定義。

![](assets/new-population-as-control-group.png)

>[!NOTE]
>
>[此區段](../../v8/start/query-editor.md)中有Adobe Campaign查詢編輯器。

### 從主要目標擷取控制組 {#extract-the-control-group-from-the-main-target}

您也可以從傳遞的主要目標擷取收件者。 在此情況下，收件者將會從受此設定影響的傳遞動作目標中取得。 此擷取可以是隨機的，也可以是排序收件者的結果。

![](assets/extract-control-group-from-target.png)

若要擷取控制組，請啟用行銷活動或傳遞的控制組，並選取下列其中一個選項： **[!UICONTROL Activate random sampling]**&#x200B;或&#x200B;**[!UICONTROL Keep only the first records after sorting]**。

* 使用&#x200B;**[!UICONTROL Activate random sampling]**&#x200B;選項，將隨機抽樣套用至主要母體中的收件者。 如果您然後將臨界值設為100，控制組將由從目標人口隨機選取的100個收件者組成。 隨機抽樣取決於資料庫引擎。
* 使用&#x200B;**[!UICONTROL Keep only the first records after sorting]**&#x200B;選項，根據一或多個排序順序定義限制。 如果您選取&#x200B;**[!UICONTROL Age]**&#x200B;欄位作為排序標準，然後將100定義為臨界值，則控制組將由100個最年輕的收件者組成。 例如，定義包含很少購買的收件者或經常購買的收件者的控制組，並將他們的行為與已聯絡的收件者的行為進行比較，這可能很有趣。

按一下&#x200B;**[!UICONTROL Next]**&#x200B;以定義排序順序（如有必要），並選取收件者限制模式。

![](assets/limit-control-group.png)

此設定等同於工作流程中的&#x200B;**[!UICONTROL Split]**&#x200B;活動，可讓您將目標分割成子集。 控制組是這些子集的其中之一。


### 教學課程影片 {#create-email-video}

此影片說明如何新增控制組至行銷活動。

>[!VIDEO](https://video.tv.adobe.com/v/335606?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=zh-Hant){target="_blank"}提供其他Campaign操作說明影片。
