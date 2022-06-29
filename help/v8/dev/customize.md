---
title: 自訂您的執行個體
description: 瞭解如何自定義實例
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---

# 自訂您的執行個體{#gs-ac-custom}

瞭解如何 **自定義您的市場活動實例**。

>[!CAUTION]
>
>Adobe Campaign定制只保留給專家用戶。

## 建立新資料欄位和方案

Adobe Campaign利用資料架構：

* 定義應用程式內的資料對象如何與基礎資料庫表關聯
* 定義市場活動應用程式中不同資料對象之間的連結
* 定義和描述每個對象中包括的各個欄位

例如，要將欄位添加到現有表(如收件人表(nms:recipient))，必須擴展該模式。

有兩種表擴展模式可用：

* 通過介面，使用 **新建欄位** 助理

   ![](../assets/do-not-localize/book.png) 瞭解如何快速在市場活動中添加新欄位 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target=&quot;_blank&quot;

* 以寫程式方式，通過擴展模式

   ![](../assets/do-not-localize/glass.png) 瞭解如何在中擴展現有架構 [此部分](../dev/extend-schema.md)。


您還可以在市場活動資料庫中建立新表並擴展內置資料模型。

要添加在Adobe Campaign（例如合同表）中不現成的全新類型資料，您可以直接建立自定義架構。 有關此內容的詳細資訊，請參閱 [此示例](../dev/create-schema.md#example--creating-a-contract-table)。

**相關主題**

![](../assets/do-not-localize/book.png) 中的架構版本示例 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target=&quot;_blank&quot;

![](../assets/do-not-localize/book.png) 用例：將欄位連結到中的現有引用表 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target=&quot;_blank&quot;


## 修改輸入表單

市場活動輸入表格可以適應您的實施。 可以通過修改XML內容來添加或刪除表單域。

![](../assets/do-not-localize/glass.png) 瞭解如何修改現有輸入表單或在 [此部分](../dev/forms.md)。

## 自定義儀表板{#gs-custom-dashboards}

Adobe Campaign介面使用許多Web應用程式來訪問、管理和與收件人、遞送、市場活動、庫存等進行交互。 在介面中，它們以僅包含一頁的儀表板的形式顯示。

預置的Web應用程式儲存在「管理」>「配置」>「Web應用程式」節點中。

![](../assets/do-not-localize/book.png) 瞭解如何在中的市場活動中建立概覽頁 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target=&quot;_blank&quot;


## 自定義清單並建立篩選器 {#gs-lists-and-filters}

### 從儀表板訪問資料

市場活動清單附帶了預定義的篩選器，以便於導航和資料可視化。

![](../assets/do-not-localize/book.png) 瞭解有關篩選選項的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering){target=&quot;_blank&quot;


### 從資源管理器訪問資料

在Adobe Campaign資源管理器樹中導航時，資料庫中包含的資料將顯示在清單中。 您可以過濾這些清單、運行搜索、添加資訊、過濾和排序資料。

![](../assets/do-not-localize/book.png) 瞭解如何在中配置清單和保存清單配置 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started){target=&quot;_blank&quot;


您可以對這些清單應用篩選器，以僅顯示運算子所需的資料。 然後，可以對過濾的資料執行動作。 篩選器配置允許您動態地從清單中選擇資料。 如果資料被修改，則更新過濾的資料。

![](../assets/do-not-localize/book.png) 瞭解如何篩選中的資料 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters){target=&quot;_blank&quot;
