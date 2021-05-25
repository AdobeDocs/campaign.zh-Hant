---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用設定檔
description: 開始使用設定檔
feature: 設定檔
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 905003b74a1f875432f08c5c70edf3d0451b861f
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 6%

---

# 將資料匯入促銷活動{#ootb-profiles}

Campaign可協助您將聯絡人新增至雲端資料庫。 您可以載入檔案、排程並自動執行多個連絡人更新、在網路上收集資料，或直接在收件者表格中輸入設定檔資訊。

：燈泡：開始使用[audiences](audiences.md)
：燈泡：了解促銷活動[資料模型](../dev/datamodel.md)

## 在工作流程中匯入設定檔

設定檔匯入是在透過&#x200B;**Import**&#x200B;活動透過工作流程執行的專用範本中設定。 它們可以根據時間表自動重複，例如多個資訊系統之間的自動化資料交換。進一步了解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html)。

![](assets/import-wf.png)

進一步了解Campaign Classicv7檔案：

:arrow_upper_right:[開始匯入和匯出](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

:arrow_upper_right:[匯入和匯出最佳實務](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

:arrow_upper_right:[配置並執行匯入](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## 運行統一導入

建立並執行一般資料匯入工作，以在雲端資料庫中載入連絡人。

![](assets/new-import.png)

:arrow_upper_right:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html)中了解如何執行統一匯入作業以饋送資料庫。

## 透過網頁應用程式收集設定檔

使用Campaign建立網路表單，並輕鬆、有效率地收集和管理設定檔資訊。 您可以將這些表單共用到您的網站中，這樣您的聯繫人就可以輕鬆提供其資訊。 他們的資訊會傳送至Campaign，以建立其設定檔，或更新其資訊（如果資訊已存在於資料庫中）。

![](assets/web-form-page.png)

:arrow_upper_right:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html)中建立網路表單。

**相關主題**

* [建立對象](audiences.md)
* [刪除重複的設定檔](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [擴充設定檔資料](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
