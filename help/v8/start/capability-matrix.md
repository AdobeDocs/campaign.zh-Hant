---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Classicv7 - Campaign v8功能矩陣
description: 了解Campaign Classicv7和Campaign v8之間的差異
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 2%

---

# [!DNL Campaign Classic] v7 - v8 [!DNL Campaign] 功能{#gs-matrix}

作為現有的[!DNL Campaign Classic] v7用戶，您不應期望與[!DNL Adobe Campaign]交互的方式出現任何大的中斷。 除了UI和配置步驟中出現的小更改外，v8中的大多數更改都不可見。

主要變更：

* 以最快200倍的速度建立區段
* 提高傳送速度
* 使用立方體進行即時報表

作為[!DNL Campaign Classic]使用者，請注意，除了[此區段](#gs-removed)中列出的小組功能外，大部分的[!DNL Campaign Classic] v7功能都可搭配[!DNL Campaign] v8使用。 其他將在未來發行。 [了解更多資訊](#gs-unavailable-features)

：燈泡：了解[本頁](../dev/architecture.md)中[!DNL Campaign] v8架構的詳細資訊。

## 產品設定變更

### [!DNL Campaign] 和  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8可與兩個資料庫一起使用：用於使用者介面即時訊息傳送和統一查詢及透過API寫入的本機資料庫，以及用於行銷活動執行、批次查詢及工作流程執行的雲端資料庫。

這是軟體架構的基本變更。 資料現在為遠端，且Campaign會聯合整個資料，包括設定檔。 [!DNL Campaign] 程式現在可端對端擴展，從目標鎖定到訊息執行：資料擷取、細分、鎖定目標、查詢、傳送現在通常會在數分鐘內執行。這個新版本解決了擴展的整個難題，同時保持了相同的靈活性和可擴充性。 設定檔的數量幾乎無限制，且資料保留期可延長。

在&#x200B;**[!DNL Snowflake]**&#x200B;中執行雲儲存：新的內建&#x200B;**外部帳戶**&#x200B;可確保與雲端資料庫的連線。 由Adobe設定，且不得修改。 [了解更多](../config/external-accounts.md)。

需要在雲資料庫中移動或複製的任何內建架構/表都會在&#x200B;**xxl**&#x200B;命名空間下隨附內建架構擴充功能。 這些擴充功能包含將內建結構從[!DNL Campaign]本機資料庫移至[!DNL Snowflake]雲端資料庫並據此調整其結構所需的任何修改：新的UUID、更新的連結等

>[!CAUTION]
>
> 客戶資料不儲存在本地[!DNL Campaign]資料庫中。 因此，任何自訂表格都必須在雲端資料庫中建立。


特定API可用來管理本機和雲端資料庫之間的資料。 了解這些新API如何運作，以及如何在[本頁面](../dev/new-apis.md)中使用它們。

### 資料復寫

特定技術工作流程會處理需要存在於兩側的表格復寫（Campaign本機資料庫和雲端資料庫）。 此工作流程每小時會觸發一次，因此需仰賴新的內建JavaScript程式庫。

>[!NOTE]
>
> 已根據表（XS、XL等）的大小建立多個複製策略。
> 有些表是即時複製的，有些表是每小時複製的。 某些表將進行增量更新，其他表將進行完整更新。


[進一步了解資料復寫](../config/replication.md)

### ID管理

Campaign v8物件現在使用&#x200B;**通用唯一ID(UUID)**，此ID允許不限數量的唯一值來識別資料

請注意，此ID是字串型且非循序。

### 簡化維護

Campaign使用者不需要是資料庫專家：不再需要複雜的資料庫維護操作或複雜的表索引。

## 臨時不可用功能{#gs-unavailable-features}

請注意，此第一版尚未提供某些功能，例如：

* 行銷資源管理
* 分散式行銷
* 傳入Offer Management（互動模組）
* 行銷活動最佳化
* 回應管理員
* 混合/內部部署模型

## 已移除的功能{#gs-removed}

為了與Campaign v8的新架構和部署模型保持一致，Campaign v8中不再提供一些歷史性的Campaign Classicv7功能。

* 優惠券
* 網站追蹤
* 調查
* 社交行銷
* ACS Connector（Prime產品）

