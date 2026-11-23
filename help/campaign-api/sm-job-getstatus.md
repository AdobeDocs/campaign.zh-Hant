---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

取得工作處理進度資訊。 警告：此API不保證會傳回唯一記錄專案清單（呼叫者必須使用其ID刪除重複專案）。

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## 參數

**id**&#x200B;工作識別碼

**lastLogId**&#x200B;上一個呼叫中傳回之最後一個記錄專案的識別碼

**maxLogCount**&#x200B;要傳送的記錄專案數目上限

## 傳回值

**狀態**&#x200B;工作狀態

**returnLogs**&#x200B;日誌訊息

**屬性**&#x200B;屬性（進度……）

## 功能

**結構描述：** [xtk:job](s-xtk-job.md)

**靜態：**

是
