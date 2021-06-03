---
product: Adobe Campaign
title: Campaign Classic v7 - Campaign v8 功能對照表
description: 瞭解 Campaign Classic v7 和 Campaign v8 之間的差異
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 44%

---

# [!DNL Campaign Classic] v7 - v8 [!DNL Campaign] 功能{#gs-matrix}

作為現有的[!DNL Campaign Classic] v7用戶，您不應期望與[!DNL Adobe Campaign]交互的方式出現任何大的中斷。 除了 UI 和設定步驟中出現的小變更以外，v8 中的大多數變更都看不太到。

主要變更：

* 建立區段的速度加快 200 倍
* 提高傳遞速度
* 即時報告 含立方體

作為[!DNL Campaign Classic]使用者，請注意，除了[此區段](#gs-removed)中列出的小組功能外，大部分的[!DNL Campaign Classic] v7功能都可搭配[!DNL Campaign] v8使用。 其他內容將在未來發行中推出。 [了解更多資訊](#gs-unavailable-features)

[!DNL :bulb:] 在本頁面中 [!DNL Campaign] 深入了解v8 [架構](../dev/architecture.md)。

## 產品設定變更

### [!DNL Campaign] 和  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8可與兩個資料庫一起使用：用於使用者介面即時訊息傳送和統一查詢及透過API寫入的本機資料庫，以及用於行銷活動執行、批次查詢及工作流程執行的雲端資料庫。

這是軟體架構的重大變更。 資料現在是遠端的，而 Campaign 會聯合所有資料，包括設定檔。 [!DNL Campaign] 流程現在可以從定位到訊息執行，進行端對端調整：資料擷取、細分、目標定位、查詢、傳遞，現在通常只需幾分鐘即可完成。此新版本可解決拓展規模的整體挑戰，同時維持相同彈性和擴充性。 設定檔的數量幾乎不受限制，資料保留期也可以延長。

在&#x200B;**[!DNL Snowflake]**&#x200B;中執行雲儲存：新的內建&#x200B;**外部帳戶**&#x200B;可確保與雲端資料庫的連線。 由Adobe設定，且不得修改。 [瞭解更多](../config/external-accounts.md)

任何需要在雲端資料庫中移動或複製的內建方案/表格都在&#x200B;**xxl**&#x200B;命名空間下附有內建方案擴充功能。這些擴充功能包含將內建結構從[!DNL Campaign]本機資料庫移至[!DNL Snowflake]雲端資料庫並據此調整其結構所需的任何修改：新的UUID、更新的連結等

>[!CAUTION]
>
> 客戶資料不儲存在本地[!DNL Campaign]資料庫中。 因此，任何自訂表格都必須在雲端資料庫中建立。


特定API可用來管理本機和雲端資料庫之間的資料。 了解這些新API如何運作，以及如何在[本頁面](../dev/new-apis.md)中使用它們。

### 資料複製

特定技術工作流程可處理需要同時存在於兩端 (Campaign 本機資料庫和雲端資料庫) 的表格複製。此工作流程每小時都會觸發一次，而且需仰賴新的內建 JavaScript 資料庫。

>[!NOTE]
>
> 已根據表格 (XS、XL等) 的大小建立了多個複製策略。
> 有些表格會即時複製，有些表格則會每小時進行複製。 有些表格會有逐漸更新，有些則會進行完整更新。


[進一步瞭解資料複製](../config/replication.md)

### ID 管理

Campaign v8 物件現在使用&#x200B;**通用唯一 ID (UUID)**，此 UUID 允許無限制的唯一值來識別資料.

請注意，此ID是字串型且非循序。 主要金鑰不是Campaign v8中的數值，且您需要在結構中使用&#x200B;**autouuid**&#x200B;和&#x200B;**autopk**&#x200B;屬性。

在Campaign Classicv7及舊版中，結構（即表格）中的金鑰的唯一性是在資料庫引擎的層級處理。 更一般地，PostgreSQL、Oracle或SQL Server等傳統資料庫引擎包括本機機制，以防止通過主鍵和/或唯一索引根據列或一組列插入重複行。 在資料庫級別設定正確的索引和主鍵時，這些版本中不存在重複的ID。

Adobe促銷活動v8以Snowflake為核心資料庫。 由於它顯著地增加了查詢的規模，Snowflake資料庫的分佈式體系結構不提供這樣的機制來管理然後強制表內密鑰的唯一性。 因此，使用Adobe Campaign v8時，不會有任何項目能防止在表格中擷取重複的金鑰。 一般使用者現在負責確保Adobe Campaign資料庫內金鑰的一致性。 [瞭解更多](../dev/keys.md)

### 簡化維護作業

Campaign 使用者不需要成為資料庫專家：不再需要複雜的資料庫維護操作或複雜的表格索引。

## 不可用功能{#gs-unavailable-features}

請注意，此第一版中未提供某些功能，例如：

* 行銷資源管理
* 分散式行銷
* 傳入活動內容管理 (互動模組)
* 行銷活動最佳化
* 回應管理員
* 混合/內部部署模型
* 線路報文傳送
* Campaign 控制面板

>[!CAUTION]
>
>目前，Campaign v8僅&#x200B;****&#x200B;可作為托管Cloud Service使用，且無法部署在內部部署或混合環境中。
>
>尚無法從現有Campaign Classicv7環境進行移轉。
>
>如果您不確定部署模式或有任何疑問，請洽詢您的客戶團隊。

## 已移除的功能{#gs-removed}

為符合 Campaign v8 的新架構和部署模型，Campaign v8 中已不再提供一些歷史性的 Campaign Classicv7 功能。

* 優惠券
* 網路追蹤
* 調查
* 社交行銷
* ACS 連接器 (Prime 產品)

