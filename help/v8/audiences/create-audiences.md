---
title: 在Campaign中建立設定檔對象
description: 了解如何建立清單和建立受眾
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 22%

---

# 在清單中建立對象{#create-segments}

使用Campaign清單來建立和組織您的對象。

清單是一組靜態的聯繫人，可在傳遞操作中定位，或在導入或其他工作流操作期間更新。 例如，透過查詢從資料庫擷取的母體可儲存為清單。

清單會透過 **[!UICONTROL Lists]** 連結 **[!UICONTROL Profiles and targets]** 標籤。 這些清單以預設的Adobe Campaign設定檔表格(nms:recipient)為基礎。 [了解更多](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

您可以使用 **更新清單** 活動。 此活動會將產生的母體儲存至清單中。 使用它建立新清單或更新現有清單。 若要建立包含內建設定檔表格以外其他類型資料的清單，您必須執行工作流程。 例如，透過在訪客資料表上查詢並更新清單，您可以建立訪客清單。[了解更多資訊](#create-a-list-wf)。

請觀看此影片，深入了解Adobe Campaign中的清單管理。

>[!VIDEO](https://video.tv.adobe.com/v/334909?quality=12)


## 建立連絡人清單 {#create-a-list-of-contacts}

要建立聯繫人清單，請執行以下步驟：

1. 按一下 **[!UICONTROL Create]** 按鈕並選取 **[!UICONTROL New list]**.

   ![](assets/new-list.png)

1. 在清單建立視窗的 **[!UICONTROL Edit]** 索引標籤中輸入資訊。

   ![](assets/list-details.png)

   * 在 **[!UICONTROL Label]** 欄位中輸入清單名稱，並視需要變更內部名稱。
   * 新增此清單的描述。
   * 您可以指定到期日：達到此日期時，清單會被清除並自動刪除。


1. 在 **[!UICONTROL Content]** 索引標籤中，按一下 **[!UICONTROL Add]** 以選取屬於清單的用戶檔案。

   ![](assets/add-profiles-to-a-list.png)

   您可以建立新的設定檔，並直接從此視窗使用 **[!UICONTROL Create]** 表徵圖。 該用戶檔案將新增至資料庫。

1. 按一下 **[!UICONTROL Save]** 儲存清單。然後，清單便會新增至清單概要中。


## 將篩選的聯繫人轉換為清單 {#convert-data-to-a-list}

您可以選取設定檔並將其新增至清單。 若要執行此作業，請遵循下列步驟：

1. 從Campaign Explorer中，選取設定檔並按一下滑鼠右鍵。

   您可以篩選這些設定檔以符合特定條件。

1. 選取 **[!UICONTROL Actions > Associate selection with a list...]**。

   ![](assets/add-selection-to-a-list.png)

1. 選取現有清單或建立新清單，然後按一下 **[!UICONTROL Next]**.

   ![](assets/select-the-list.png)

1. 按一下 **[!UICONTROL Start]** 按鈕。

   ![](assets/record-a-list.png)

選取 **[!UICONTROL Recreate the list]** 選項，從清單中刪除現有內容並最佳化清單的建立（無需查詢即可確認設定檔是否已連結至清單）。

如果您取消核取 **[!UICONTROL No trace of this job is saved in the database]** 選項，可以選擇（或建立）執行資料夾，其中將儲存連結到此進程的資訊。

使用視窗的上方區域可監視執行情況。使用 **[!UICONTROL Stop]** 按鈕可停止程序。已處理的連絡人將連結至清單。

執行完成後，請存取 **[!UICONTROL Profiles and Targets > Lists]** ，然後選取清單：the **[!UICONTROL Content]** 標籤顯示連結到此清單的配置檔案。


## 使用工作流程建立清單  {#create-a-list-wf}

您可以使用 **[!UICONTROL List update]** 建立清單或將人口新增至收件者清單的活動。

在以下範例中，您會建立25到40之間的所有收件者清單。

1. 選擇 **[!UICONTROL Profiles and targets]**，和 **[!UICONTROL Targeting workflows]**，然後從 **[!UICONTROL Create]** 按鈕。
1. 輸入此工作流的標籤，例如「25-40個聯繫人」，添加說明，然後按一下 **[!UICONTROL Next]**.

   ![](assets/targeting-wf-sample.png)

1. 插入 **[!UICONTROL Query]** 活動來定義目標母體及編輯查詢。

   ![](assets/targeting-wf-edit-query.png)

1. 定義篩選條件，如下所示：

   ![](assets/targeting-wf-age-filter.png)

   了解如何在 [本節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. 為此查詢添加標籤並保存更改。
1. 新增 **[!UICONTROL List update]** 活動，並加以編輯。

   ![](assets/list-update-activity.png)

1. 輸入活動的標籤。
1. 選取 **[!UICONTROL Create the list if necessary (Computed name)]** 選項，顯示執行第一個工作流程後將建立清單，然後以下列執行更新。
1. 選擇資料夾並為清單輸入標籤。
1. 選取 **[!UICONTROL Database of the targeting dimension]** 儲存表格。
1. 保留 **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** 選項，刪除不符合定位條件的收件者，並將新收件者插入清單中。
1. 同時將 **[!UICONTROL Create or use a list with its own table]** 選項。
1. 保留 **[!UICONTROL Generate an outbound transition]** 選項。
1. 按一下 **[!UICONTROL Ok]**，並儲存工作流程。
1. 啟動工作流程。

   然後會建立相符的收件者清單。 您可以從 **[!UICONTROL Lists]** 首頁的項目。

   ![](assets/access-new-list.png)

   您可以將排程器新增至工作流程，讓此工作流程重複執行。 [了解更多資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html)。

## 從清單中移除設定檔 {#remove-a-profile-from-a-list}

要從清單中刪除配置檔案，請編輯該清單，在 **[!UICONTROL Content]** ，然後按一下 **[!UICONTROL Delete]** 表徵圖。

## 刪除設定檔清單 {#delete-a-list-of-profiles}

若要刪除清單，請從「促銷活動總管」瀏覽至該清單，選取該清單，然後按一下滑鼠右鍵。 選擇 **[!UICONTROL Delete]**. 此時將顯示警告訊息，要求您確認是否刪除。

>[!NOTE]
>
>刪除清單時，清單上的用戶檔案不受影響，但是將更新用戶檔案中的資料。
