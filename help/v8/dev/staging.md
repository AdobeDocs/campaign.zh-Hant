---
solution: Campaign v8
product: Adobe Campaign
title: 促銷活動API測試機制
description: 促銷活動API測試機制
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 3%

---

# 促銷活動API測試機制

若使用Campaign Cloud資料庫，由於效能（延遲和並行），不建議使用blast統一呼叫。 總是首選批操作。 為保證API的最佳效能，Campaign會持續在本機資料庫層級處理API呼叫。

促銷活動中繼機制適用於內建和自訂表格，並具備下列優點：

* 資料架構結構在本地臨時表中複製
* 用於擷取的新API會直接流入測試表格。 [了解更多](new-apis.md)
* 排程的工作流程每小時會觸發一次，並將資料同步回雲端資料庫。 [了解更多](../config/replication.md)。

某些內建結構預設會分段，例如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classicv7 API仍可供使用，但無法受益於此新的測試機制：API呼叫會直接流至雲端資料庫。 Adobe建議盡可能使用新的測試機制，以降低Campaign Cloud資料庫的整體壓力和延遲。

>[!CAUTION]
>
>透過這種新機制，訂閱、取消訂閱或行動註冊的資料同步現在為&#x200B;**非同步**。


## 實施步驟{#implement-staging}

若要在特定表格上實作Campaign測試機制，請遵循下列步驟：

1. 在Campaign Cloud資料庫上建立範例自訂結構。 此步驟未啟用測試。

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

   ：燈泡：進一步了解在[此頁面](create-schema.md)中建立自訂架構。

1. 保存和更新資料庫結構。  [了解更多](update-database-structure.md)

1. 新增&#x200B;**autoStg=&quot;true&quot;**&#x200B;參數，以在架構定義中啟用預備機制。

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

1. 儲存修改。 有新的中繼架構可用，此為初始架構的本機副本。

   ![](assets/staging-mechanism.png)

1. 更新資料庫結構。 中繼表格將建立在Campaign本機資料庫上。
