---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

允許使用 Post 4.00 格式，檢索由遠端重新導向和網路追蹤伺服器產生的追蹤記錄。

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## 參數

**執行個體**&#x200B;簡短識別碼

執行傳遞之客戶的&#x200B;**dbId**&#x200B;資料庫識別碼

應該從其中擷取記錄檔的&#x200B;**指標**&#x200B;識別碼（序列化int64）。

**logCount**&#x200B;要為要求擷取的記錄數（0表示預設值），回應傳回的記錄數。

## 傳回值

應該從其中擷取記錄檔的&#x200B;**指標**&#x200B;識別碼（序列化int64）。

**logCount**&#x200B;要為要求擷取的記錄數（0表示預設值），回應傳回的記錄數。

已擷取&#x200B;**個記錄檔**&#x200B;個記錄檔

記錄擷取要求時伺服器的&#x200B;**srvDate** GMT時間

## 功能

**結構描述：** [nms:remoteTracking](s-nms-remotetracking.md)

**靜態：**

是
