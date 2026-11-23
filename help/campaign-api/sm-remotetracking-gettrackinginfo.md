---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

允許遠端重新導向伺服器下載有關傳遞動作的資訊。

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## 參數

**執行個體**&#x200B;執行個體名稱

執行傳遞之客戶的&#x200B;**dbId**&#x200B;資料庫識別碼

**deliveryId**&#x200B;傳遞識別碼。

## 傳回值

**檔案**&#x200B;包含此傳遞的追蹤資訊的檔案

## 功能

**結構描述：** [nms:remoteTracking](s-nms-remotetracking.md)

**靜態：**

是
