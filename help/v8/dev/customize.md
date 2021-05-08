---
solution: Campaign
product: Adobe Campaign
title: 自訂您的例項
description: 瞭解如何自訂實例
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
translation-type: tm+mt
source-git-commit: ddf60fb823cb0df99bdf3bc99f17d7a1abe6a33b
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# 自訂您的例項{#gs-ac-custom}

瞭解如何&#x200B;**自訂您的促銷活動例項**

>[!CAUTION]
>
>Adobe Campaign自訂僅保留給專家使用者。

## 建立新的資料欄位和結構描述

Adobe Campaign利用資料結構來：

* 定義應用程式中資料對象與基礎資料庫表的關聯方式
* 定義促銷活動應用程式中不同資料物件之間的連結
* 定義並說明每個物件所包含的個別欄位

例如，要向現有表添加欄位，如收件者表(nms:recipient)，必須擴展該模式。

有兩種表格擴充模式可供使用：

* 通過介面，使用&#x200B;**New field** assistant

   :arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)中快速新增促銷活動欄位

* 以程式設計方式，借由擴充架構

   ：球：瞭解如何在[本節](../dev/extend-schema.md)中擴展現有模式。


您也可以在Campaign資料庫中建立新表格，並擴充內建的資料模型。

若要新增在Adobe Campaign不現成可用的全新資料類型（例如合約表格），您可以直接建立自訂結構。 有關詳細資訊，請參閱[此示例](../dev/create-schema.md#example--creating-a-contract-table)。

**相關主題**

:arrow_upper_right:[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)中的架構版示例

:arrow_upper_right:使用案例：將欄位連結到[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)中的現有參考表


## 修改輸入表單

促銷活動輸入表單可以調整以配合您的實施。 您可以修改XML內容來新增或移除表格欄位。

：球：瞭解如何修改現有輸入表單或在[本節](../dev/forms.md)中建立新表單。

## 自訂控制面板{#gs-custom-dashboards}

Adobe Campaign介面使用許多Web應用程式來存取、管理並與收件者、傳送、促銷活動、股票等互動。 在介面中，只有一個頁面的控制面板就會顯示它們。

現成可用的Web應用程式會儲存在「管理>設定> Web應用程式」節點中。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)的促銷活動中建立概述頁面


## 自訂清單並建立篩選器{#gs-lists-and-filters}

### 從控制面板存取資料

促銷活動清單隨附預先定義的篩選，以利導覽和資料視覺化。

:arrow_upper_right:進一步瞭解[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)中的篩選選項


### 從瀏覽器存取資料

在Adobe Campaign瀏覽器樹中導航時，資料庫中包含的資料將顯示在清單中。 您可以篩選這些清單、執行搜尋、新增資訊、篩選及排序資料。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)中配置清單並保存清單配置


您可以對這些清單套用篩選，只顯示運算子所需的資料。 然後，可以對篩選資料執行動作。 篩選設定可讓您動態地從清單中選取資料。 如果修改了資料，則更新過濾的資料。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)中篩選資料
