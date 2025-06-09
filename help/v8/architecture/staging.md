---
title: Campaign API準備機制
description: Campaign API準備機制
feature: Configuration, API, FFDA
role: Developer
level: Intermediate
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 9d500f185a9e706b6558135978c4f8c79d92d0d4
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---

# Campaign API準備機制

在[企業(FFDA)部署](enterprise-deployment.md)的內容中，不建議在效能（延遲和並行）方面引發單一呼叫。 除非您傳送的磁碟量極低，否則必須使用批次作業&#x200B;**&#x200B;**。 為了改善效能，內嵌API會重新導向至本機資料庫。

根據預設，某些內建方案會啟用行銷活動準備功能。 我們也可以在任何自訂結構描述上將其啟用。 簡述暫存機制：

* 資料結構描述結構會複製到本機中繼資料表中
* 專用於資料擷取的新API會直接流入本機中繼表格。 [了解更多](new-apis.md)
* 排程的工作流程每小時會觸發一次，並將資料同步回雲端資料庫。 [了解更多](replication.md)

部分內建結構依預設會分段，例如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classic v7 API仍可使用，但無法從此新的準備機制受益： API呼叫直接流向雲端資料庫。 Adobe建議儘可能使用新的準備機制，以減少Campaign Cloud資料庫的整體壓力和延遲。

>[!CAUTION]
>
>* 透過此新機制，頻道選擇、訂閱、取消訂閱或行動註冊的資料同步現在是&#x200B;**非同步**。
>
>* 中繼僅適用於儲存在雲端資料庫上的結構描述。 請勿在復寫的結構描述上啟用暫存。 請勿在本機結構描述上啟用分段。 不要在已暫存綱要上啟用暫存
>

## 實施步驟 {#implement-staging}

若要在特定表格上實作Campaign準備機制，請遵循下列步驟：

1. 在Campaign Cloud資料庫上建立範例自訂結構描述。 此步驟未啟用任何分段。

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

   在[此頁面](../dev/create-schema.md)中進一步瞭解自訂結構描述建立。

1. 儲存並更新資料庫結構。  [了解更多](../dev/update-database-structure.md)

1. 透過新增&#x200B;**autoStg=&quot;true&quot;**&#x200B;引數，在結構描述定義中啟用暫存機制。

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

1. 儲存修改。 有新的分段結構描述可供使用，這是初始結構描述的本機副本。

   ![](assets/staging-mechanism.png)

1. 更新資料庫結構。 將在Campaign本機資料庫上建立臨時資料表。
