---
title: 開始部署Campaigment FDA
description: 開始部署Campaigment FDA
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 53%

---

# [!DNL Campaign] FFDA部署{#gs-ac-ffda}

通過利用 [[!DNL Snowflake]](https://www.snowflake.com/)、雲資料庫技術，Adobe Campaign企業完全聯合訪問(FFDA)部署可顯著提高其規模和速度，能夠管理更多客戶配置檔案，以及更高的每小時交付率和事務。

## 好處 {#ffda-benefits}

市場活動v8企業版(FFDA)在流程的任何步驟（從目標到最終報告）都提供端到端的規模：

* 擴充可處理的資料量 (至 8 TB)
* 針對細分和目標定位以及資料擷取與匯出調整查詢的效能
* 調整傳送準備規模 (從小時到分鐘)

這是軟體架構的重大變更。 資料現在是遠端的，而 Campaign 會聯合所有資料，包括設定檔。 [!DNL Campaign] 流程現在可以調整端對端規模，包含從目標定位到訊息執行：資料擷取、細分、目標定位、查詢、傳送，現在通常只需幾分鐘即可完成。此新版本可解決拓展規模的整體挑戰，同時維持相同彈性和擴充性。 設定檔的數量幾乎不受限制，資料保留期也可以延長。

在 **[!DNL Snowflake]** 中執行雲端儲存空間：新的內建 **外部帳戶** 可確保與雲端資料庫的連線。由 Adobe 設定，且不得修改。 [深入瞭解](../config/external-accounts.md)

任何需要在雲端資料庫中移動或複製的內建方案/表格都在 **xxl** 命名空間下包含內建方案擴充功能。這些擴充功能包含將內建方案從 [!DNL Campaign] 本機資料庫移至 [!DNL Snowflake] 雲端資料庫，並據以調整其結構所需的任何修改：新的 UUID、更新的連結等。

>[!CAUTION]
>
> 客戶資料不會儲存在本機 [!DNL Campaign] 資料庫中。 因此，任何自訂表格都必須在雲端資料庫中建立。

## 市場活動企業(FDA)體系結構{#ffda-archi}

在 [企業(FDA)部署](../architecture/enterprise-deployment.md)。 [!DNL Adobe Campaign] v8適用於兩個資料庫：當地 [!DNL Campaign] 用於用戶介面即時消息傳遞和統一查詢及通過API和雲寫入的資料庫 [!DNL Snowflake] 用於市場活動執行、批處理查詢和工作流執行的資料庫。

Campaig v8 Enterprise帶來了 **完全聯合資料存取** (FFDA):現在，雲資料庫上的所有資料都是遠程資料。

可利用特定 API 來管理本機和雲端資料庫之間的資料。 在[此頁面](new-apis.md)瞭解這些新 API 如何運作，以及如何使用它們。

伺服器和進程之間的一般通信按照以下模式進行：

![](assets/architecture.png)

* 實例上禁用了執行和彈出管理模組。
* 該應用程式配置為在使用SOAP調用（通過HTTP或HTTPS）驅動的遠程「中間源」伺服器上執行消息。

的 [!DNL Snowflake] 市場營銷方面的資料庫用於：

* 儲存所有客戶資料：配置檔案、自定義資料，如事務、產品、位置等。
* 儲存市場活動生成或收集的所有事件和行為資料，如交貨日誌、跟蹤日誌、推送註冊等。
* 儲存上述所有資料聚合。
* 儲存引用表（如交貨、枚舉、國家等）的副本(h+1) 用於工作流、市場活動和報表。
* 運行所有批處理和工作負載


市場營銷實例上的PostgreSQL資料庫用於：

* 執行某些工作負載，如低卷API。
* 儲存所有市場活動資料，包括交貨和市場活動設定、工作流和服務定義。
* 儲存所有內置引用表（枚舉、國家等） 複製到 [!DNL Snowflake]。

   但是，您不能：
   * 為客戶資料建立自定義項，例如，不在PostgreSQL中建立家庭表，而只是在Snowflake中
   * 儲存任何交貨日誌、跟蹤日誌等。 在FFDA目標維度上。
   * 儲存大量資料。


中間採購實例上的PostgreSQL資料庫用於：

* 執行批處理和即時(RT)交貨。
* 發送傳遞和跟蹤日誌 — 請注意，傳遞和跟蹤日誌ID是UUID，不是32位ID。
* 收集和儲存跟蹤資料。


## 影響{#ffda-impacts}

### [!DNL Campaign] API 準備機制{#staging-api}

與 [!DNL Campaign] 由於效能（延遲和併發），建議不要對雲資料庫、Blast統一調用進行處理。 批處理操作始終是首選的。 為了保證API的最佳效能，Campign會在本地資料庫級別處理API調用。

![](../assets/do-not-localize/glass.png) [本頁詳細介紹了API暫存機制](staging.md)

### 新 API{#new-apis}

新的API可用於管理之間的資料同步 [!DNL Campaign] 本地資料庫和雲資料庫。 此外，還引入了一種新機制來處理本地資料庫級別的API調用，以避免延遲並提高整體效能。

![](../assets/do-not-localize/glass.png) [本頁詳細介紹了新API](new-apis.md)


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
