---
title: 瞭解市場活動交互體系結構
description: 市場活動交互體系結構基礎
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: dafdf471fcaf2b6c6e3e8d5028cd65e35e7df3eb
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 瞭解市場活動交互環境和體系結構

## 環境 {#environments}

在管理優惠時，每個目標維都有兩個環境：

* A **設計** 在此環境中，聘用經理負責建立和分類聘用、編輯聘用和啟動審批流程，以便使用聘用。 每個類別的規則、可提供優惠的優惠空間以及用於定義優惠資格的預定義篩選器也在此環境中定義。

   也可以在聯機環境中手動發佈類別。

   批准聘用的過程是詳細的 [此部分](interaction-offer.md#approve-offers)。

* A **活** 可以找到設計環境中批准的服務，以及設計環境中配置的各種服務空間、過濾器、類別和規則。 在調用「提供」引擎時，引擎將始終使用來自即時環境的提供。

僅在審批流程中選定的要約空間上部署要約。 因此，一個產品可以是即時的，但在同樣是即時的產品空間中無法使用。

## 入站和出站交互 {#interaction-types}

Adobe Campaign互動模組提出兩種互動：

* **入站** 交互，由聯繫人啟動。 [了解更多](interaction-present-offers.md)
* **出站** 交互，由市場活動交付經理啟動。 [了解更多](interaction-send-offers.md)

這兩種相互作用可以在 **幺模** （為單個聯繫人計算優惠），或 **批處理模式** （為一組聯繫人計算要約）。 通常，入站交互以酉模式進行，出站交互以批模式進行。 然而，可能有若干例外， [事務性消息](../send/transactional.md) 例如，使出站交互以整體模式進行。

一旦能夠或必須提供（根據所執行的配置）優惠，優惠引擎即扮演中介角色：它通過組合接收的關於聯繫人的資料和應用程式中指定的可以應用的不同規則，自動計算可用聯繫人的最佳報價。

![](assets/architecture_interaction2.png)

## 分佈式體系結構

為了能夠支援可擴充性並在入站通道上提供全天候服務， **交互** 模組在分佈式架構中實現。 此類體系結構已與 [消息中心](../dev/architecture.md#transac-msg-archi) 由幾個實例組成：

* 一個或多個專用於出站渠道並包含營銷和環境設計基礎的控制實例
* 專用於入站通道的一個或多個執行實例

![](assets/interaction_powerbooster_schema.png)

控制實例專用於入站通道並包含目錄的聯機版本。 每個執行實例都是獨立的，並專用於一個聯繫段（例如，每個國家/地區一個執行實例）。 必須在執行時直接調用服務引擎（每個執行實例有一個特定URL）。 由於實例之間的同步不是自動的，因此必須通過同一實例發送來自同一聯繫人的交互。

### 同步 {#synchronization}

服務同步通過包執行。 在執行實例中，所有目錄對象都以外部帳戶名為前置詞。 這意味著可以在同一個執行實例上支援多個控制實例（例如開發和生產實例）。

>[!CAUTION]
>
>使用簡短和顯式的內部名稱。

服務將自動部署，然後在執行和控制實例上發佈。

在設計環境中刪除的優惠在所有聯機實例上都被禁用。 在清除期（在每個實例的部署助理中指定）和滑動期（在傳入命題的類型規則中指定）之後，將在所有實例上自動刪除過時命題和優惠。

![](assets/interaction_powerbooster_schema2.png)

為每個環境和外部帳戶建立工作流以進行命題同步。 可以針對每個環境和外部帳戶調整同步頻率。

您必須瞭解以下同步機制：

* 如果您使用從匿名環境到已標識環境的回退功能，這兩個環境必須位於同一執行實例上。
* 多個執行實例之間的同步不會即時執行。 必須將同一聯繫人的交互發送到同一實例。 控制實例必須專用於出站通道（非即時）。
* 市場營銷資料庫未自動同步。 權重和資格規則中使用的市場營銷資料必須在執行實例上重複。 此過程不是標準的，您必須在整合期間開發它。
* 命題同步完全由FDA連接執行。
* 如果在同一實例上使用交互和消息中心，則在這兩種情況下都將通過FDA協定進行同步。

### 包配置 {#packages-configuration}

直接連結到的任何架構擴展 **交互** （優惠、建議、收件人等） 必須部署在執行實例上。

的 **交互** 軟體包安裝在所有實例（控制和執行）上。 另外還提供兩個包：一個包用於控制實例，另一個包用於每個執行實例。

>[!NOTE]
>
>安裝軟體包時， **長** 類型欄位 **nms：命題** 表，如命題ID，成為 **int64** 的下界。 此類型的資料在 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data){target=&quot;_blank&quot;}。

資料保留期是在每個實例上配置的(通過 **[!UICONTROL Data purge]** )的正平方根。 在執行實例中，此期間必須與要計算的類型規則（滑動期間）和資格規則所需的歷史深度相對應。

在控制項實例上：

1. 為每個執行實例建立一個外部帳戶：

   ![](assets/interaction_powerbooster1.png)

   * 完成標籤並添加一個簡短且顯式的內部名稱。
   * 選取 **[!UICONTROL Execution instance]**。
   * 核取 **[!UICONTROL Enabled]** 選項。
   * 完成執行實例的連接參數。
   * 每個執行實例都必須連結到ID。 按一下 **[!UICONTROL Initialize connection]** 按鈕
   * 檢查所用應用程式的類型： **[!UICONTROL Message Center]**。 **[!UICONTROL Interaction]**，或兩者兼有。
   * 輸入使用的FDA帳戶。 必須在執行實例上建立運算子，並且必須對有關實例的資料庫具有以下讀寫權限：

      ```
      grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
      grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
      ```
   >[!NOTE]
   >
   >必須在執行實例上授權控制實例的IP地址。

1. 配置環境：

   ![](assets/interaction_powerbooster2.png)

   * 添加執行實例清單。
   * 對於每個同步週期，指定同步週期和篩選條件（例如，按國家/地區）。

      >[!NOTE]
      >
      >如果遇到錯誤，可以參考同步工作流並提供通知。 可以在應用程式的技術工作流中找到這些。

如果出於優化原因，只有部分市場營銷資料庫在執行實例上重複，則可以指定連結到環境的受限方案，以允許用戶僅使用執行實例上可用的資料。 您可以使用執行實例上不可用的資料建立優惠。 為此，必須通過限制出站通道上的此規則(**[!UICONTROL Taken into account if]** )。

![](assets/ita_filtering.png)

### 維護選項 {#maintenance-options}

以下是控制實例上可用的維護選項清單：

>[!CAUTION]
>
>這些選項只能用於特定的維護案例。

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**:環境在給定實例上同步的上次日期。
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**:給定架構中的命題從一個實例同步到另一個實例的最後日期。
* **`NmsInteraction_MapWorkflowId`**:包含所有生成的同步工作流清單的選項。

以下選項可用於執行實例：

**NmsExecutionInstanceId**:選項。

### 軟體包安裝 {#packages-installation}

如果您的實例以前沒有 **交互** 包，無需遷移。 預設情況下，在安裝軟體包後，命題表將以64位為單位。

>[!CAUTION]
>
>根據實例中現有陳述的數量，此操作可能需要一段時間。

* 如果實例的陳述很少或沒有，則無需手動修改陳述表。 在安裝軟體包時將進行修改。
* 如果實例有許多建議，最好在安裝控制包並運行它們之前更改建議表的結構。 我們建議在低活動期間運行查詢。

>[!NOTE]
>
>如果已在命題表中執行了特定配置，請相應地調整查詢。


有兩種方法：

**工作表** （推薦）

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**更改表**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```
