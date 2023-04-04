---
title: 在Campaign中匯入設定檔
description: 了解如何在Campaign中匯入連絡人
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 24%

---

# 從檔案匯入設定檔{#create-profiles}

若要填入您的Campaign資料庫，您可以 [手動新增設定檔](create-profiles.md) 或匯入設定檔，如下所述。 您也可以使用匯入的檔案來更新聯絡人資料。

## 使用工作流程匯入設定檔 {#import-profiles-with-a-wf}

工作流程可以用來自動執行某些匯入過程。無論是從本地檔案還是從 SFTP 匯入資料，都可以使用工作流程來標準化資料管理過程。

### 使用清單中的資料：讀取清單 {#data-from-read-list}

在檔案中準備和建構資料，以使用工作流程匯入資料。 [了解更多資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html)。

### 從檔案載入資料 {#data-from-a-file}

工作流程中處理的資料可從結構化檔案中擷取，以便匯入至Adobe Campaign。 [了解更多資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html)。

收集完資料後，您就可以在工作流程中使用資料，例如擴充傳送或更新資料庫。 如需詳細資訊，請參閱[本章節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html)。

## 一次性進口{#import-jobs}

Adobe Campaign提供一般匯入功能，例如，可讓您擷取客戶或潛在客戶的清單，這些客戶或潛在客戶隨後將成為目標母體的一部分，或將外部檔案的資料提供給您的資料庫。

一般匯入會從 **[!UICONTROL Profiles and Targets > Jobs]** Adobe Campaign首頁的功能表。

![](assets/new-import-job.png)

執行一般匯入的步驟在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hant){target="_blank"}.
