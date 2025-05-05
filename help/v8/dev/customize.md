---
title: 自訂您的執行個體
description: 瞭解如何自訂您的執行個體
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 1%

---

# 自訂您的執行個體 {#gs-ac-custom}

瞭解如何&#x200B;**自訂您的Campaign執行個體**。

>[!CAUTION]
>
>Adobe Campaign自訂功能僅供專家使用者使用。

## 建立新的資料欄位和結構描述

Adobe Campaign使用資料結構描述來：

* 定義應用程式內的資料物件如何繫結到基礎資料庫表格
* 定義Campaign應用程式中不同資料物件之間的連結
* 定義並描述每個物件中包含的個別欄位

例如，若要將欄位新增至現有表格，例如收件者表格(nms：recipient)，您必須擴充該綱要。

提供兩種表格擴充模式：

* 透過介面，使用&#x200B;**新欄位**&#x200B;小幫手

  在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=zh-Hant#configuring-campaign-classic){target="_blank"}中瞭解如何在Campaign中快速新增欄位

* 以程式設計方式，擴充綱要。 在[本節](../dev/extend-schema.md)中瞭解如何擴充現有結構描述。

您也可以在Campaign資料庫中建立新表格，並擴充內建資料模型。

若要新增不存在於Adobe Campaign中的現成全新資料型別（例如合約表格），您可以直接建立自訂結構描述。 如需詳細資訊，請參閱[此範例](../dev/create-schema.md#example--creating-a-contract-table)。

**相關主題**

[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=zh-Hant#configuring-campaign-classic){target="_blank"}中的結構描述版本範例

使用案例：將欄位連結至[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=zh-Hant#uc-link){target="_blank"}中的現有參考表格


## 修改輸入表單

Campaign輸入表單可進行調整以適合您的實施。 您可以藉由修改XML內容來新增或移除表單欄位。

瞭解如何在[本節](../dev/forms.md)中修改現有的輸入表單或建立新表單。

## 自訂儀表板{#gs-custom-dashboards}

Adobe Campaign介面使用許多網頁應用程式來存取、管理收件者、傳遞、行銷活動、庫存等，並與之互動。 在介面中，這些區段會以儀表板形式顯示，且只有一個頁面。

內建的Web應用程式儲存在Explorer的&#x200B;**管理>組態> Web應用程式**&#x200B;資料夾中。

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=zh-Hant#creating-a-single-page-web-application){target="_blank"}中瞭解如何在Campaign中建立概觀頁面


## 自訂清單並建立篩選器 {#gs-lists-and-filters}

行銷活動清單隨附預先定義的篩選器，以便利導覽和資料視覺化。

當您在Adobe Campaign Explorer樹狀結構中導覽時，資料庫中包含的資料會顯示於清單中。 您可以篩選這些清單、執行搜尋、新增資訊、篩選及排序資料。

瞭解如何在[此頁面](../start/campaign-ui.md)中設定清單並儲存清單設定。

您可以對這些清單套用篩選，以僅顯示運運算元所需的資料。 接著，您就可以針對篩選的資料執行動作。 篩選器設定可讓您從清單中動態選取資料。 如果修改資料，則會更新篩選的資料。

在[此頁面](../audiences/create-filters.md)中進一步瞭解篩選選項。
