---
solution: Campaign Classic
product: campaign
title: Campaign Classicv7 —— 促銷活動v8功能表
description: 瞭解Campaign Classicv7和Campaign v8之間的差異
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: 04859274593f507a0b07f46cf6a65434b6a4bc60
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# Campaign Classicv7 —— 促銷活動v8功能{#gs-matrix}


身為Campaign Classicv7的既有使用者，您應該期待您與Adobe Campaign的「玩」方式會出現任何大的中斷。 大多數更改都不可見，但UI和配置步驟中出現的小更改除外。

主要變更：

* 建立區段的速度快上200倍

* 提高傳送速度

* 即時報告

身為Campaign Classic使用者，請注意，Campaign v8中除了[本節](#gs-removed)所列的一小組功能外，大部份的Campaign Classicv7功能都提供。 其他公司將在未來發行。 [了解更多](#gs-unavailable-features)


## 產品設定變更

### 促銷活動與Snowflake{#ac-gs-snowflake}

雲端儲存空間是在Snowflake中執行：新的外部帳戶可確保與雲端資料庫的連線。 [了解更多](#ac-gs-snowflake)。

這是軟體架構的根本變更。 資料現在是遠程的：促銷活動會聯合整個資料，包括描述檔。 促銷活動程式現在可以從定位到傳送執行，端對端調整：資料擷取、分段、定位、查詢、傳送執行現在只需幾分鐘即可執行。

此新版本可解決縮放的整個挑戰，並維持相同等級的彈性和擴充性。 配置檔案的數量幾乎不受限制，資料保留期也可以延長。

全FDA專門提供新的內建&#x200B;**外部帳戶**。 這是雲資料庫連接的核心。 我們建議按原樣離開。

任何需要在雲資料庫中移動或複製的內置模式／表都帶有命名空間&#x200B;**xxl**&#x200B;下的內置模式擴展。 至於架構擴充，新的XXL命名空間將用於任何新的OOTB組態，例如JavaScript、JSSP等。

這些擴充功能包含從Campaign本機資料庫移動內建結構描述至SnowflakeCloud資料庫並據以調整其結構所需的任何修改：新的UUID、更新的連結等。

>[!CAUTION]
>
> 客戶資料不會儲存在本機促銷活動資料庫中。 因此，任何自訂表格都必須在Cloud資料庫中建立。


### 資料複製

特定技術工作流程可處理需要同時存在於兩側的表（Campaign本機資料庫和雲端資料庫）的複製。 此工作流程每小時都會觸發一次，而且需仰賴新的內建JavaScript程式庫。

>[!NOTE]
>
> 已根據表（XS、XL等）的大小建立了多個複製策略。
> 有些表格會即時複製，有些表格則會每小時複製。 某些表將具有增量更新，而其他表將具有完整更新。


[進一步瞭解資料複製](../config/replication.md)

### ID管理

促銷活動v8物件現在使用&#x200B;**通用唯一ID(UUID)**，這表示不限的唯一值來識別資料

請不要說此ID是以字串為基礎，而非循序。

### 簡化維護作業

促銷活動使用者不需要成為資料庫專家：不再需要維護資料庫，而需要長時間的工作流程或複雜的表索引。

## 暫時無法使用的功能{#gs-unavailable-features}

請注意，本第一個版本中不提供某些功能，但即將發行，例如：

* 行銷資源管理
* 分散式行銷
* 選件管理傳入訊息（互動模組）
* 行銷活動最佳化
* 回應管理員
* 社交行銷與Twitter
* 混合／內部部署模型

## 已移除的功能{#gs-removed}

為了與Campaign v8的新架構和部署模型一致，Campaign v8中不提供一些歷史性的Campaign Classicv7功能。

* 優惠券
* 網站追蹤
* 調查
* 社交行銷與Facebook
* ACS連接器（Prime產品）
* Microsoft SQL資料庫
* Oracle資料庫
