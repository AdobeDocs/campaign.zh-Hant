---
product: campaign
title: 建立循環和定期行銷活動
description: 瞭解如何建立及執行週期性行銷活動
feature: Campaigns, Cross Channel Orchestration, Programs
role: User
exl-id: 68c5b903-5043-4e74-b3f6-90a7f2fb3b9a
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---

# 循環和定期行銷活動 {#recurring-and-periodic-campaigns}

**週期性行銷活動**&#x200B;是基於特定範本的行銷活動，其工作流程已設定為根據關聯的排程執行。 目標定位會在每次執行時重複，並追蹤各種流程和目標母體。  設定之後，循環行銷活動會自動建立新工作流程（透過複製工作流程範本）並執行它。 例如，如果您需要傳送每月提醒至對象區段，請設定循環行銷活動，以便在每年年初建立12個工作流程，每個月一個。 [了解更多](#create-a-recurring-campaign)

**週期性行銷活動**&#x200B;是根據特定範本的行銷活動，可讓您根據執行排程建立行銷活動執行個體。 系統會根據週期性行銷活動範本，根據範本排程中定義的頻率，自動建立行銷活動例項。 [了解更多](#create-a-periodic-campaign)

## 建立週期性行銷活動 {#create-a-recurring-campaign}

循環行銷活動是從定義要執行的工作流程範本和執行排程的特定範本建立。

### 建立週期性行銷活動的範本 {#create-the-campaign-template}

若要建立週期性行銷活動的範本，請遵循下列步驟：

1. 開啟Campaign檔案總管並瀏覽至&#x200B;**[!UICONTROL Resources > Templates > Campaign templates]**。
1. 複製內建&#x200B;**[!UICONTROL Recurring campaign]**範本。
   ![](assets/recurring-campaign-duplicate.png)
1. 輸入範本名稱和行銷活動的持續時間。
1. 針對此型別的行銷活動，已新增&#x200B;**[!UICONTROL Schedule]**索引標籤以建立範本執行排程。 使用此索引標籤可根據此範本定義行銷活動的執行日期。
   ![](assets/recurring-campaign-schedule.png)

   執行排程的設定模式與工作流程的&#x200B;**[!UICONTROL Scheduler]**&#x200B;物件一致。 [了解更多](../workflow/scheduler.md)。

   >[!CAUTION]
   >
   >執行排程設定必須小心執行。 週期性行銷活動會根據指定的排程複製其範本的工作流程。 此作業可能會使資料庫超載。

1. 在&#x200B;**[!UICONTROL Create in advance for]**&#x200B;欄位中指定一個值，以便在指定的期間內建立對應的工作流程。
1. 在&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;索引標籤中，根據此範本設計要用於行銷活動的工作流程範本。 此工作流程通常包含目標定位引數以及一或多個傳送。

   >[!NOTE]
   >
   >此工作流程必須儲存為週期性工作流程範本。 若要這麼做，請編輯工作流程屬性，並在&#x200B;**[!UICONTROL Execution]**&#x200B;索引標籤中選取&#x200B;**[!UICONTROL Recurring workflow template]**&#x200B;選項。

   ![](assets/recurring-campaign-wf-properties.png)

### 建立週期性行銷活動 {#create-the-recurring-campaign}

若要建立週期性行銷活動，並根據範本中定義的排程執行其工作流程，您必須：

1. 根據您的週期性行銷活動範本，建立新的行銷活動。
1. 在&#x200B;**[!UICONTROL Schedule]**&#x200B;索引標籤中填寫工作流程執行排程。 行銷活動排程可讓您輸入每行的自動工作流程建立或執行開始日期。

   您可以為每行新增下列其他選項：

   * 啟用&#x200B;**[!UICONTROL To be approved]**&#x200B;選項以強制在工作流程中傳送核准請求。
   * 啟用&#x200B;**[!UICONTROL To be started]**&#x200B;選項，以便在到達開始日期時啟動工作流程。

   **[!UICONTROL Create in advance for]**&#x200B;欄位可讓您建立涵蓋輸入期間的所有工作流程。

   在執行&#x200B;**[!UICONTROL Jobs on campaigns]**&#x200B;工作流程時，會根據行銷活動排程中定義的發生次數來建立專用工作流程。 因此，會為每個執行日期建立工作流程。

1. 循環工作流程是從行銷活動中存在的工作流程範本自動建立。 可從行銷活動的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;索引標籤中看到。

   ![](assets/recurring-wf-created.png)

   循環工作流程例項的標籤由其範本標籤和工作流程編號組成，其中的#字元介於。

   從排程建立的工作流程會自動與&#x200B;**[!UICONTROL Schedule]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Workflow]**&#x200B;欄相關聯。

   ![](assets/recurring-wf-schedule-executed.png)

   每個工作流程都可以從此索引標籤進行編輯。

   >[!NOTE]
   >
   >與工作流程相關之排程明細行的開始日期可從工作流程的變數取得，其語法如下：\
   >`$date(instance/vars/@startPlanningDate)`

## 建立定期行銷活動 {#create-a-periodic-campaign}

定期行銷活動是根據特定範本的行銷活動，可讓您根據執行排程建立行銷活動執行個體。 系統會根據週期性行銷活動範本，根據範本排程中定義的頻率，自動建立行銷活動例項。

### 建立行銷活動範本 {#create-the-campaign-template-1}

1. 開啟Campaign檔案總管並瀏覽至&#x200B;**[!UICONTROL Resources > Templates > Campaign templates]**。
1. 複製內建&#x200B;**[!UICONTROL Periodic campaign]**&#x200B;範本。
1. 輸入範本的屬性。

   >[!NOTE]
   >
   >指派範本的操作者必須具有適當許可權，才能在選取的方案建立行銷活動。

1. 建立與此範本關聯的工作流程。 此工作流程會在範本建立的每個定期行銷活動中重複。

   >[!NOTE]
   >
   >此工作流程是工作流程範本。 無法從行銷活動範本執行此動作。

1. 完成其定期行銷活動範本的執行排程：按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕並定義開始和結束日期，或透過連結填寫執行排程。

   >[!CAUTION]
   >
   >定期行銷活動範本會根據上述定義的排程建立新的行銷活動。 因此，必須小心完成，以避免Adobe Campaign資料庫超載。

1. 一旦達到執行開始日期，就會自動建立相符的行銷活動。 它會使用其範本的所有特性。

   每個行銷活動都可透過範本排程進行編輯。

   每個定期行銷活動都包含相同的元素。 建立後，即作為標準行銷活動進行管理。
