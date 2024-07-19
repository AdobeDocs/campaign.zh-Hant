---
title: 使用工作流程資料
description: 瞭解如何使用工作流程資料
feature: Workflows, Data Management
exl-id: 5014c2ed-2a74-4122-b7b9-d3703db7ab12
source-git-commit: 41ba91fca46747760fc42ea6cd78600abbd74c02
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 8%

---

# 使用工作流程資料{#how-to-use-workflow-data}

您可以使用工作流程活動來執行多項工作。 尋找以下使用範例，說明如何透過建立清單、管理訂閱、透過工作流程傳送訊息，或豐富您的傳送內容及其閱聽眾，來更新資料庫。

[此區段](workflow-use-cases.md)提供一組工作流程使用案例。

## 資料生命週期 {#data-life-cycle}

### 工作流程臨時工作表 {#work-table}

在工作流程中，從某個活動傳輸到另一個活動的資料會儲存在臨時工作表中。

在適當的轉變上按一下滑鼠右鍵，即可顯示和分析此資料。

![](assets/wf-right-click-analyze.png)

要執行此操作，請選取相關功能表：

* **[!UICONTROL Display the target...]**

  此功能表會顯示目標母體上的可用資料。

  ![](assets/wf-right-click-display.png)

  您可以在&#x200B;**[!UICONTROL Schema]**&#x200B;索引標籤中存取工作表結構。

  ![](assets/wf-right-click-schema.png)

  如需詳細資訊，請參閱[本章節](monitor-workflow-execution.md#worktables-and-workflow-schema)。

* **[!UICONTROL Analyze target...]**

  使用此功能表存取描述性分析精靈，讓您產生轉換資料的統計資料和報表。

  在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html?lang=zh-Hant){target="_blank"}中瞭解如何使用描述性分析精靈。

在執行工作流程時清除目標資料。 只能存取最後一個工作表。 您可以設定工作流程，讓所有工作表保持可存取狀態：核取工作流程屬性中的&#x200B;**[!UICONTROL Keep the result of interim populations between two executions]**&#x200B;選項。

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>在&#x200B;**生產**&#x200B;工作流程中，**切勿**&#x200B;勾選此選項。此選項用於分析結果，且僅供用於測試目的，因此只能在開發或中繼環境中使用。


### 善用目標資料 {#target-data}

儲存在工作流程臨時工作表中的資料可用於個人化任務。 資料可用於[個人化欄位](../../v8/send/personalization-fields.md)。

舉例來說，這可讓您在傳送中使用透過清單所收集的資料。 要執行此操作，請使用下列語法：

```
%= targetData.FIELD %
```

**[!UICONTROL Target extension]** (targetData)型別個人化元素不適用於目標工作流程。 必須在工作流程中建置傳遞目標，並在傳遞的入站轉變中指定。

在以下範例中，您正在收集客戶資訊清單，以用於個人化電子郵件中。 應用以下步驟：

1. 建立工作流程以收集資訊，將其與資料庫中已存在的資料進行調解，然後開始傳遞。

   ![](assets/wf-targetdata-sample-1.png)

1. 在我們的範例中，檔案內容如下：

   ```
   Music,First name,Last name,Account,CD/DVD,Card
   Pop,David,BLAIR,4323,CD,0
   Rock,Daniel,ARCARI,3222,DVD,1
   Disco,Uma,ALTON,0488,DVD,0
   Jazz,Paul,BOLES,6475,CD,1
   Jazz,David,BOUKHARI,0841,DVD,1
   [...]
   ```

   若要載入檔案，請設定&#x200B;**[!UICONTROL Data loading (file)]**&#x200B;活動，如下所示：

   ![](assets/wf-targetdata-sample-2.png)

1. 設定&#x200B;**[!UICONTROL Enrichment]**&#x200B;活動，將收集的資料與Adobe Campaign資料庫中已存在的資料進行調解。 調解金鑰是帳號：

   ![](assets/wf-targetdata-sample-3.png)

1. 然後設定&#x200B;**[!UICONTROL Delivery]**：它是根據範本建立的，收件者是由入站轉變所指定。

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >只有轉換中包含的資料才可用來個人化傳遞。 **targetData**&#x200B;型別個人化欄位僅適用於&#x200B;**[!UICONTROL Delivery]**&#x200B;活動的傳入母體。

1. 在傳遞範本中，使用在工作流程中收集的欄位。

   若要這麼做，請插入&#x200B;**[!UICONTROL Target extension]**&#x200B;型別個人化欄位。

   ![](assets/wf-targetdata-sample-5.png)

   在此處，我們要插入客戶最愛的音樂流派和媒體型別（CD或DVD），如工作流程收集的檔案中所述。

   此外，我們將為熟客卡持有者（即「卡片」值等於1的收件者）新增優惠券。

   ![](assets/wf-targetdata-sample-6.png)

   **[!UICONTROL Target extension]** (targetData)型別資料是使用與所有個人化欄位相同的特性插入傳遞。 它們也可用於主旨、連結標籤或連結本身。


## 更新資料庫 {#update-the-database}

所有收集的資料都可用於更新資料庫或用於傳送。 例如，您可以豐富訊息內容個人化的可能性（包括訊息中的合約數、指定去年的平均購物車數量等） 或詳細母體目標定位（傳送訊息給合約共同持有者，目標定位線上服務的1,000個最佳訂閱者等）。 此資料也可以匯出或封存於清單中。

### 更新清單  {#list-updates}

Adobe Campaign資料庫和現有清單的資料可以使用兩個專用活動進行更新：

* **[!UICONTROL List update]**&#x200B;活動可讓您將工作表儲存在資料清單中。

  您可以選取或建立現有清單。 在這種情況下，將計算名稱，並可能計算記錄資料夾。

  ![](assets/s_user_create_list.png)

  請參閱[清單更新](list-update.md)。

* **[!UICONTROL Update data]**&#x200B;活動會大量更新資料庫中的欄位。

  如需詳細資訊，請參閱[更新資料](update-data.md)。

### 管理訂閱 {#subscription-management}

若要瞭解透過工作流程訂閱及取消訂閱收件者資訊服務的相關資訊，請參閱[訂閱服務](subscription-services.md)。
