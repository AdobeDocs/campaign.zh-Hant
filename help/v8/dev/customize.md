---
solution: Campaign v8
product: Adobe Campaign
title: 自訂您的執行個體
description: 了解如何自訂您的執行個體
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# 自訂您的執行個體{#gs-ac-custom}

了解如何&#x200B;**自訂您的Campaign執行個體**

>[!CAUTION]
>
>Adobe Campaign自訂僅保留給專家使用者。

## 建立新資料欄位和結構

Adobe Campaign利用資料結構來：

* 定義應用程式內資料對象與基礎資料庫表的綁定方式
* 定義Campaign應用程式內不同資料物件之間的連結
* 定義並說明每個物件中包含的個別欄位

例如，若要將欄位新增至現有表格，例如收件者表格(nms:recipient)，您必須擴充該架構。

提供兩種表格擴充模式：

* 透過介面，使用&#x200B;**新欄位**&#x200B;助理

   :[!DNL :arrow_upper_right:]:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)中快速在Campaign中新增欄位

* 以程式設計方式，借由擴充架構

   [!DNL :bulb:] 在本小節中了解如何擴充現有 [的結構](../dev/extend-schema.md)。


您也可以在Campaign資料庫中建立新表格，並擴充內建的資料模型。

若要新增Adobe Campaign中不存在的全新資料類型（例如合約表格），您可以直接建立自訂結構。 有關詳細資訊，請參閱[此示例](../dev/create-schema.md#example--creating-a-contract-table)。

**相關主題**

:[!DNL :arrow_upper_right:]:[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)中的架構版本範例

:[!DNL :arrow_upper_right:]:使用案例：將欄位連結至[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)中的現有參考表


## 修改輸入表單

Campaign輸入表單可適應您的實作。 您可以修改XML內容，以新增或移除表單欄位。

[!DNL :bulb:] 了解如何在本小節修改現有輸入表單或建立 [新表單](../dev/forms.md)。

## 自訂控制面板{#gs-custom-dashboards}

Adobe Campaign介面使用許多網頁應用程式來存取、管理收件者、傳遞、行銷活動、股票等項目，並與之互動。 在介面中，控制面板只會顯示一個頁面。

現成的Web應用程式儲存在「管理>配置> Web應用程式」節點中。

:[!DNL :arrow_upper_right:]:在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)中了解如何在Campaign中建立概覽頁面


## 自訂清單並建立篩選器{#gs-lists-and-filters}

### 從控制面板存取資料

促銷活動清單隨附預先定義的篩選器，以促進導覽和資料視覺化。

:[!DNL :arrow_upper_right:]:進一步了解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)中的篩選選項


### 從資源管理器訪問資料

在Adobe Campaign資源管理器樹中導航時，資料庫中包含的資料將顯示在清單中。 您可以篩選這些清單、執行搜尋、新增資訊、篩選及排序資料。

:[!DNL :arrow_upper_right:]:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)中設定清單並儲存清單設定


您可以對這些清單套用篩選，以僅顯示運算子所需的資料。 然後，即可對篩選的資料執行動作。 篩選設定可讓您動態地從清單中選取資料。 如果修改了資料，則更新篩選的資料。

:[!DNL :arrow_upper_right:]:了解如何在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)中篩選資料
