---
title: 自訂您的執行個體
description: 了解如何自訂您的執行個體
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 1%

---

# 自訂您的執行個體{#gs-ac-custom}

了解如何 **自訂您的Campaign執行個體**.

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

* 透過介面，使用 **新欄位** 助理

   ![](../assets/do-not-localize/book.png) 了解如何在中快速新增Campaign中的欄位 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target="_blank"}

* 以程式設計方式，借由擴充架構

   ![](../assets/do-not-localize/glass.png) 了解如何在 [本節](../dev/extend-schema.md).


您也可以在Campaign資料庫中建立新表格，並擴充內建的資料模型。

若要新增Adobe Campaign中不存在的全新資料類型（例如合約表格），您可以直接建立自訂結構。 有關詳細資訊，請參閱 [此範例](../dev/create-schema.md#example--creating-a-contract-table).

**相關主題**

![](../assets/do-not-localize/book.png) 中的架構版本範例 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target="_blank"}

![](../assets/do-not-localize/book.png) 使用案例：將欄位連結到 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target="_blank"}


## 修改輸入表單

Campaign輸入表單可適應您的實作。 您可以修改XML內容來新增或移除表單欄位。

![](../assets/do-not-localize/glass.png) 了解如何修改現有的輸入表單或在 [本節](../dev/forms.md).

## 自訂控制面板{#gs-custom-dashboards}

Adobe Campaign介面使用許多網頁應用程式來存取、管理收件者、傳遞、行銷活動、股票等項目，並與之互動。 在介面中，控制面板只會顯示一個頁面。

現成的Web應用程式儲存在「管理>配置> Web應用程式」節點中。

![](../assets/do-not-localize/book.png) 了解如何在Campaign中建立概觀頁面，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target="_blank"}


## 自訂清單和建立篩選器 {#gs-lists-and-filters}

### 從控制面板存取資料

促銷活動清單隨附預先定義的篩選器，以促進導覽和資料視覺化。

![](../assets/do-not-localize/book.png) 進一步了解中的篩選選項 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering){target="_blank"}


### 從資源管理器訪問資料

在Adobe Campaign資源管理器樹中導航時，資料庫中包含的資料將顯示在清單中。 您可以篩選這些清單、執行搜尋、新增資訊、篩選及排序資料。

![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started){target="_blank"}


您可以對這些清單套用篩選，以僅顯示運算子所需的資料。 然後，即可對篩選的資料執行動作。 篩選設定可讓您動態地從清單中選取資料。 如果修改了資料，則更新篩選的資料。

![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters){target="_blank"}
