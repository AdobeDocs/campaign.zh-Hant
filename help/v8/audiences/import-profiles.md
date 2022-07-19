---
title: 導入市場活動中的配置檔案
description: 瞭解如何在市場活動中導入聯繫人
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 24%

---

# 從檔案匯入設定檔{#create-profiles}

要填充市場活動資料庫，您可以 [手動添加配置檔案](create-profiles.md) 或導入配置式（如下所述）。 您還可以使用導入的檔案來更新聯繫人資料。

## 使用工作流程匯入設定檔 {#import-profiles-with-a-wf}

工作流程可以用來自動執行某些匯入過程。無論是從本地檔案還是從 SFTP 匯入資料，都可以使用工作流程來標準化資料管理過程。

### 使用清單中的資料：讀取清單 {#data-from-read-list}

準備並構建檔案中的資料，以使用工作流導入資料。 [了解更多資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html)。

### 從檔案載入資料 {#data-from-a-file}

工作流中處理的資料可以從結構化檔案中提取，以便可以導入到Adobe Campaign。 [了解更多資訊](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html)。

收集資料後，您就可以在工作流中使用它，例如，用於豐富傳遞內容或更新資料庫。 如需詳細資訊，請參閱[本章節](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html)。

## 一次性進口{#import-jobs}

Adobe Campaign提供通用導入功能，例如，允許您提取客戶或潛在客戶的清單，這些客戶或潛在客戶隨後將成為目標群體的一部分，或向資料庫提供來自外部檔案的資料。

通用導入從 **[!UICONTROL Profiles and Targets > Jobs]** 菜單開啟它。

![](assets/new-import-job.png)

執行泛型導入的步驟詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hant){target=&quot;_blank&quot;}。
