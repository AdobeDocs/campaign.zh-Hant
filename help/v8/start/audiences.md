---
title: 在活動中與受眾協作
description: 在活動中與受眾協作
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: b5fb8825734bce2ec62485208b468757b461005f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 19%

---

# 在活動中與受眾協作{#gs-ac-audiences}

配置檔案是儲存在市場活動資料庫中的聯繫人。

在Adobe Campaign, **收件人** 是用於發送遞送（電子郵件、SMS等）的預設配置檔案。 儲存在資料庫中的收件人資料使您能夠篩選將接收任何給定傳遞的目標，並在傳遞內容中添加個性化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。

瞭解如何導入、更新和管理配置檔案和受眾 [此部分](../audiences/gs-audiences.md)。

## 建立清單{#create-lists}

清單是一組靜態聯繫人，可以在交貨操作中針對這些聯繫人，或在導入或其他工作流操作期間更新這些聯繫人。 例如，通過查詢從資料庫提取的總體可以儲存為清單。

![](../assets/do-not-localize/glass.png) 瞭解如何在中建立和管理清單 [此頁](../audiences/create-audiences.md)。

## 篩選資料庫{#filter-the-database}

篩選器配置允許您從清單中選擇資料 **[!UICONTROL dynamically]**:當資料被修改時，過濾的資料被更新。 您可以建立自己的篩選器或使用內置篩選器來定義目標受眾。

![](../assets/do-not-localize/glass.png) 瞭解如何在中建立和管理篩選器 [此頁](../audiences/create-filters.md)。

## 在工作流中建立訪問群體

目標可以通過工作流中圖形序列中的查詢組合來建立。 您可以根據您的要求建立目標受眾。 要顯示工作流編輯器，請按一下 **[!UICONTROL Targeting and workflows]** 頁籤

![](../assets/do-not-localize/book.png) 瞭解如何在中的市場活動工作流中構建受眾 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}。


## 使用中的設定檔案{#active-profiles}

根據您的合同，您的每個市場活動實例都配置了特定數量的有效配置檔案，這些配置檔案被計為用於開單目的。 請參閱您的最新合約，以參考已購買作用中設定檔數目。

**配置檔案** 指資訊記錄(例如：記錄 [收件人表](../dev/datamodel.md) 或包含cookie ID、客戶ID、移動標識符或與特定渠道相關的其他資訊的外部表)，這些資訊代表最終客戶、潛在客戶或潛在客戶。 如果配置檔案在過去12個月內通過任何渠道成為目標或進行通信，則它們被視為活動。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->


## 隱私權與同意

Adobe Campaign是收集和處理大量資料（包括個人資訊和敏感資料）的強大工具。 Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

![](../assets/do-not-localize/book.png) 瞭解如何管理中的隱私和同意 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant){target=&quot;_blank&quot;}。


Campaign Classic v7 文件中的&#x200B;**相關主題**：

* [設計和執行市場活動特定的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;

* [瞭解如何選擇市場活動的受眾](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;

* [開始使用工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;
