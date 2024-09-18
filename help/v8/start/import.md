---
title: 開始使用設定檔
description: 開始使用設定檔
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 98%

---

# 將資料匯入 Campaign {#ootb-profiles}

Campaign 可協助您將聯絡人新增至雲端資料庫。 您可以載入檔案、排程並自動化多個聯絡人更新、在網路上收集資料，或直接在收件者表格中輸入設定檔資訊。

開始使用[客群](audiences.md)

瞭解Campaign [資料模型](../dev/datamodel.md)

## 在工作流程中匯入設定檔

設定檔匯入是在專用範本中設定的，專用範本則是在工作流程透過&#x200B;**匯入**&#x200B;活動執行。 它們可以根據排程自動重複，例如多個資訊系統之間的自動化資料交換。在[本節](../../automation/workflow/recurring-import-workflow.md)了解更多資訊。

![](assets/import-wf.png)


## 執行單一匯入

建立並執行一般資料匯入作業，以載入雲端資料庫中的聯絡人。

![](assets/new-import.png)

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hant){target="_blank"}瞭解如何執行單一匯入作業，以供資料庫使用。

## 透過網頁應用程式收集設定檔

使用 Campaign 建立網路表單，輕鬆、有效率地收集並管理設定檔資訊。 您可以在您的網站共用這些表單，讓您的聯絡人輕鬆提供資訊。 他們的資訊會傳送至 Campaign 建立其設定檔，或更新其資訊 (如果資訊已存在於資料庫中)。

![](assets/web-form-page.png)

在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=zh-Hant){target="_blank"}瞭解如何建立網路表單。

**相關主題**

* [建立客群](audiences.md)
* [重複設定檔](../../automation/workflow/deduplication-merge.md)
* [豐富設定檔資料](../../automation/workflow/enrich-data.md)
