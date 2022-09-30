---
title: 開始部署Campaign FDA
description: 開始部署Campaign FDA
feature: Architecture, FFDA
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 55%

---

# [!DNL Campaign] FFDA部署{#gs-ac-ffda}

透過善用 [[!DNL Snowflake]](https://www.snowflake.com/)，是雲端資料庫技術，Adobe Campaign企業完整同盟存取(FFDA)部署可大幅改善其規模和速度，並能管理更多客戶設定檔，以及更高的每小時傳送率和交易。

## 好處 {#ffda-benefits}

Campaign v8 Enterprise(FFDA)可在程式的任何步驟（從定位到最終報告）提供端對端規模：

* 擴充可處理的資料量 (至 8 TB)
* 針對細分和目標定位以及資料擷取與匯出調整查詢的效能
* 調整傳送準備規模 (從小時到分鐘)

這是軟體架構的重大變更。 資料現在是遠端的，而 Campaign 會聯合所有資料，包括設定檔。 [!DNL Campaign] 流程現在可以調整端對端規模，包含從目標定位到訊息執行：資料擷取、細分、目標定位、查詢、傳送，現在通常只需幾分鐘即可完成。此新版本可解決拓展規模的整體挑戰，同時維持相同彈性和擴充性。 設定檔的數量幾乎不受限制，資料保留期也可以延長。

在 **[!DNL Snowflake]** 中執行雲端儲存空間：新的內建 **外部帳戶** 可確保與雲端資料庫的連線。由 Adobe 設定，且不得修改。 [深入瞭解](../config/external-accounts.md)

任何需要在雲端資料庫中移動或複製的內建方案/表格都在 **xxl** 命名空間下包含內建方案擴充功能。這些擴充功能包含將內建方案從 [!DNL Campaign] 本機資料庫移至 [!DNL Snowflake] 雲端資料庫，並據以調整其結構所需的任何修改：新的 UUID、更新的連結等。

>[!CAUTION]
>
> 客戶資料不會儲存在本機 [!DNL Campaign] 資料庫中。 因此，任何自訂表格都必須在雲端資料庫中建立。

## Campaign Enterprise(FFDA)架構{#ffda-archi}

在 [企業(FFDA)部署](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8可與兩個資料庫一起使用：本地 [!DNL Campaign] 資料庫，用於透過API和雲端的使用者介面即時訊息傳送和統一查詢與寫入 [!DNL Snowflake] 用於促銷活動執行、批次查詢和工作流程執行的資料庫。

Campaign v8 企業版帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。

可利用特定 API 來管理本機和雲端資料庫之間的資料。 在[此頁面](new-apis.md)瞭解這些新 API 如何運作，以及如何使用它們。

伺服器和進程之間的一般通信根據以下模式執行：

![](assets/architecture.png)

* 執行和退信管理模組在執行個體上是停用的。
* 應用程式可配置為在使用SOAP呼叫（通過HTTP或HTTPS）驅動的遠程「中源」伺服器上執行消息。

此 [!DNL Snowflake] 行銷端的資料庫用於：

* 儲存所有客戶資料：設定檔、自訂資料，例如交易、產品、位置等。
* 儲存Campaign產生或收集的所有事件和行為資料，例如傳送記錄、追蹤記錄、推播註冊等。
* 儲存上述的所有資料匯總。
* 儲存參考表的副本(h+1)（例如傳送、列舉、國家等） 用於工作流程、行銷活動和報表。
* 運行所有批處理和工作負載


行銷實例上的PostgreSQL資料庫用於：

* 執行某些工作負載，如低容量API。
* 儲存所有促銷活動資料，包括傳遞和促銷活動設定、工作流程和服務定義。
* 儲存所有內建的參考表（列舉、國家等） 複製到 [!DNL Snowflake].

   但您不能：
   * 為客戶資料建立自定義項，例如，不要在PostgreSQL中建立家庭表，而只在Snowflake中
   * 儲存任何傳送記錄、追蹤記錄等。 在FFDA目標維度上。
   * 儲存大量資料。


中間來源實例上的PostgreSQL資料庫用於：

* 執行批次和即時(RT)傳送。
* 傳送傳送和追蹤記錄檔 — 請注意，傳送和追蹤記錄檔ID是UUID，而非32位元ID。
* 收集和儲存追蹤資料。


## 影響{#ffda-impacts}

### [!DNL Campaign] API 準備機制{#staging-api}

使用 [!DNL Campaign] 由於效能（延遲和並行），不建議使用雲資料庫、blast統一調用。 總是首選批操作。 為保證API的最佳效能，Campaign會持續在本機資料庫層級處理API呼叫。

![](../assets/do-not-localize/glass.png) [本頁面詳細說明API中繼機制](staging.md)

### 新 API{#new-apis}

新的API可用來管理 [!DNL Campaign] 本地資料庫和雲資料庫。 此外，也推出新機制，在本機資料庫層級處理API呼叫，以避免延遲並提升整體效能。

![](../assets/do-not-localize/glass.png) [本頁詳細說明新API](new-apis.md)


### 資料複製{#data-replication}

特定技術工作流程可處理需要同時存在於兩端 (Campaign 本機資料庫和雲端資料庫) 的表格複製。此工作流程每小時都會觸發一次，而且需仰賴新的內建 JavaScript 資料庫。

>[!NOTE]
>
> 已根據表格 (XS、XL等) 的大小建立了多個複製策略。
> 有些表格會即時複製，有些表格則會每小時進行複製。 有些表格會有逐漸更新，有些則會進行完整更新。

[深入瞭解資料複製](replication.md)

### ID 管理{#id-mgt-ffda}

Campaign v8 物件現在使用&#x200B;**通用唯一 ID (UUID)**，此 UUID 允許無限制的唯一值來識別資料.

請注意此 ID 是字串且並非循序。主索引鍵不是 Campaign v8 中的數值，且您需要在結構中使用 **autouuid** 和 **autopk** 屬性。

在 Campaign Classic v7 及舊版中，對於方案 (即表格) 中的金鑰其唯一性在資料庫引擎層級處理。 更一般而言，PostgreSQL、Oracle 或 SQL Server 等傳統資料庫引擎包含本機機制，以防止透過主索引鍵和/或唯一索引，根據一列或一組列插入重複行。 在資料庫層級設定正確的索引和主索引鍵時，這些版本不會存在重複的 ID。

Adobe Campaign v8 以 Snowflake 作為核心資料庫。 由於它顯著增加了查詢規模，Snowflake 資料庫的分散式架構不提供這樣的機制來管理並強制在表格內要求索引鍵的唯一性。 因此，使用 Adobe Campaign v8 時，將無法防止在表格中擷取重複的索引鍵。 終端使用者現在負責在 Adobe Campaign 資料庫內確保索引鍵的一致性。 [深入瞭解](keys.md)

**相關主題**

* [資料模型最佳實務](../dev/datamodel-best-practices.md)
