---
title: Campaign Classic v7 - Campaign v8 功能對照表
description: 瞭解 Campaign Classic v7 和 Campaign v8 之間的差異
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 98%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 功能{#gs-matrix}

[!DNL Campaign Classic]身為 v7 的現有使用者，您和 [!DNL Adobe Campaign] 的互動方式差異應該不會太大。除了 UI 和設定步驟中出現的小變更以外，v8 中的大多數變更都看不太到。

主要變更：

* 建立區段的速度加快 200 倍
* 提高傳遞速度
* 即時報告含立方體

身為 [!DNL Campaign Classic] 使用者，請注意， [!DNL Campaign] v8 中除了[本節](#gs-removed)所列的一小部分功能外，也提供大部份 [!DNL Campaign Classic] v7 的功能。 其他內容將在未來發行中推出。 [在本節了解更多資訊](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png) 在本頁面了解更多 [!DNL Campaign] v8 [架構](../dev/architecture.md)。

## 產品設定變更

### [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8可與兩個資料庫一起使用：本機資料庫，用於使用者介面即時傳送訊息和透過 API 統一查詢及寫入，以及雲端資料庫，用於行銷活動執行、批次查詢及工作流程執行。

這是軟體架構的重大變更。 資料現在是遠端的，而 Campaign 會聯合所有資料，包括設定檔。 [!DNL Campaign] 流程現在可以調整端對端規模，包含從目標定位到訊息執行：資料擷取、細分、目標定位、查詢、傳送，現在通常只需幾分鐘即可完成。此新版本可解決拓展規模的整體挑戰，同時維持相同彈性和擴充性。 設定檔的數量幾乎不受限制，資料保留期也可以延長。

在 **[!DNL Snowflake]** 中執行雲端儲存空間：新的內建 **外部帳戶** 可確保與雲端資料庫的連線。由 Adobe 設定，且不得修改。 [深入瞭解](../config/external-accounts.md)

任何需要在雲端資料庫中移動或複製的內建方案/表格都在 **xxl** 命名空間下包含內建方案擴充功能。這些擴充功能包含將內建方案從 [!DNL Campaign] 本機資料庫移至 [!DNL Snowflake] 雲端資料庫，並據以調整其結構所需的任何修改：新的 UUID、更新的連結等。

>[!CAUTION]
>
> 客戶資料不會儲存在本機 [!DNL Campaign] 資料庫中。 因此，任何自訂表格都必須在雲端資料庫中建立。

可利用特定 API 來管理本機和雲端資料庫之間的資料。 在[此頁面](../dev/new-apis.md)瞭解這些新 API 如何運作，以及如何使用它們。

### 資料複製

特定技術工作流程可處理需要同時存在於兩端 (Campaign 本機資料庫和雲端資料庫) 的表格複製。此工作流程每小時都會觸發一次，而且需仰賴新的內建 JavaScript 資料庫。

>[!NOTE]
>
> 已根據表格 (XS、XL等) 的大小建立了多個複製策略。
> 有些表格會即時複製，有些表格則會每小時進行複製。 有些表格會有逐漸更新，有些則會進行完整更新。

[深入瞭解資料複製](../config/replication.md)

### ID 管理

Campaign v8 物件現在使用&#x200B;**通用唯一 ID (UUID)**，此 UUID 允許無限制的唯一值來識別資料.

請注意此 ID 是字串且並非循序。主索引鍵不是 Campaign v8 中的數值，且您需要在結構中使用 **autouuid** 和 **autopk** 屬性。

在 Campaign Classic v7 及舊版中，對於方案 (即表格) 中的金鑰其唯一性在資料庫引擎層級處理。 更一般而言，PostgreSQL、Oracle 或 SQL Server 等傳統資料庫引擎包含本機機制，以防止透過主索引鍵和/或唯一索引，根據一列或一組列插入重複行。 在資料庫層級設定正確的索引和主索引鍵時，這些版本不會存在重複的 ID。

Adobe Campaignv8以Snowflake為核心資料庫。 由於它顯著增加了查詢規模，Snowflake 資料庫的分散式架構不提供這樣的機制來管理並強制在表格內要求索引鍵的唯一性。 因此，使用 Adobe Campaign v8 時，將無法防止在表格中擷取重複的索引鍵。 終端使用者現在負責在 Adobe Campaign 資料庫內確保索引鍵的一致性。 [深入瞭解](../dev/keys.md)

### 簡化維護作業

Campaign 使用者不需要成為資料庫專家：不再需要複雜的資料庫維護操作或複雜的表格索引。

## 與 Campaign 的連線

Campaign 使用者透過其 Adobe ID 連線。 相同的 Adobe ID 可用來保留與單一帳戶相關聯的所有 Adobe 計畫和產品。

![](../assets/do-not-localize/glass.png)瞭解在[此頁面](connect.md)如何連結到[!DNL Campaign].。

## 報告

請注意，Adobe Campaign 報告已最佳化，且提供比 Campaign Classic v7 更好的擴充功能。 對立方體的限制不適用。

## 工作流程 {#workflow}

Campaign v8 提供額外目標定位工作流程活動：**[!UICONTROL Change data source]**。

**[!UICONTROL Change data source]**&#x200B;活動可讓您變更工作流程的資料來源&#x200B;**[!UICONTROL Working table]**，以管理不同資料來源 (例如FDA、FFDA 和本機資料庫) 的資料。

![](../assets/do-not-localize/glass.png)**[!UICONTROL Change data source]**&#x200B;在[本頁面](../config/workflows.md#change-data-source-activity)瞭解活動的更多資訊。

## 未提供的功能{#gs-unavailable-features}

請注意此 Campaign 版本尚未提供部分功能，例如：

* 行銷資源管理
* 分散式行銷
* 回應管理員
* 混合/內部部署模型

>[!CAUTION]
>
>* 目前，Campaign v8 僅&#x200B;****&#x200B;可作為托管 Cloud Service 使用，而且無法在內部部署或混合環境中進行部署。
>
>* 尚無法從現有 Campaign Classic v7 環境進行移轉。
>
>* 如果您不確定部署模式，或有任何疑問，請洽詢您的帳戶團隊。


## 不支援的功能{#gs-removed}

為符合 Campaign v8 的新架構和部署模型，Campaign v8 中已不再提供一些 Campaign Classic v7 的歷史性功能。例如:

* 優惠券
* 網路追蹤
* 調查
* 社交行銷搭配 Facebook
* ACS 連接器 (主要優惠)
* 與 LDAP 整合
* 使用者/密碼登入

>[!NOTE]
>
>使用者介面中仍會顯示某些無法使用或不支援的功能。
