---
title: 市場活動API登台機制
description: 市場活動API登台機制
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# 市場活動API登台機制

使用Campaign Cloud資料庫，不建議在效能（延遲和併發）方面進行單一呼叫爆破。 批處理操作始終是首選的。 為了提高效能，接收API被重定向到本地資料庫。

預設情況下，在某些內置架構上啟用市場活動轉移功能。 我們還可以在任何自定義架構上啟用它。 簡要地說，分級機制：

* 資料架構結構複製到本地臨時表中
* 專用於資料接收的新API直接流入本地臨時表。 [了解更多](new-apis.md)
* 計畫的工作流每小時都會觸發一次，並將資料同步回雲資料庫。 [了解更多](../config/replication.md)

預設情況下，某些內置架構會被轉移，如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classicv7 API仍然可用，但無法從此新的轉移機制中獲益：API調用直接流到雲資料庫。 Adobe建議盡可能使用新的轉移機制，以減少市場活動雲資料庫的總體壓力和延遲。

>[!CAUTION]
>
>* 利用此新機制，現在即可進行通道輸出、訂閱、取消訂閱或移動註冊的資料同步 **非同步**。
>
>* 暫存僅適用於儲存在雲資料庫上的架構。 不在複製的架構上啟用暫存。 不在本地架構上啟用暫存。 不在轉移架構上啟用轉移
>


## 實施步驟{#implement-staging}

要在特定表上實施市場活動轉移機制，請執行以下步驟：

1. 在市場活動雲資料庫上建立示例自定義架構。 此步驟未啟用轉移。

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   ![](../assets/do-not-localize/glass.png) 瞭解有關在中建立自定義架構的詳細資訊 [此頁](create-schema.md)。

1. 保存並更新資料庫結構。  [了解更多](update-database-structure.md)

1. 通過添加 **autoStg=&quot;true&quot;** 的下界。

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. 保存修改。 新的臨時架構可用，它是初始架構的本地副本。

   ![](assets/staging-mechanism.png)

1. 更新資料庫結構。 將在市場活動本地資料庫上建立臨時表。
