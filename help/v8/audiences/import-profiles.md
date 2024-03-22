---
title: 在Campaign中匯入設定檔
description: 瞭解如何在Campaign中匯入連絡人
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 15%

---

# 從檔案匯入設定檔{#create-profiles}

若要填入Campaign資料庫，您可以 [手動新增設定檔](create-profiles.md) 或匯入設定檔，如下所述。 您也可以使用匯入的檔案來更新聯絡資料。

## 使用工作流程匯入設定檔 {#import-profiles-with-a-wf}

工作流程可能是自動化部分匯入流程的實用方式。 無論是從本地檔案還是從 SFTP 匯入資料，都可以使用工作流程來標準化資料管理過程。

### 使用清單中的資料：讀取清單 {#data-from-read-list}

在檔案中準備和建構您的資料，以使用工作流程匯入資料。 [了解更多](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}。

### 從檔案載入資料 {#data-from-a-file}

工作流程中處理的資料可從結構化檔案中擷取，以便匯入Adobe Campaign中。 [了解更多](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}。

收集到資料後，您便可以在工作流程中使用資料，例如擴充傳遞或更新資料庫。 有關詳細資訊，請參閱 [本節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"}.

## 一次性匯入{#import-jobs}

Adobe Campaign提供一般匯入功能，例如可讓您擷取隨後將成為目標母體一部分的客戶或潛在客戶清單，或向您的資料庫提供外部檔案中的資料。

一般匯入是從以下專案進行管理： **[!UICONTROL Profiles and Targets > Jobs]** Adobe Campaign首頁的功能表。

![](assets/new-import-job.png)

執行一般匯入的步驟詳見 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hant){target="_blank"}.
