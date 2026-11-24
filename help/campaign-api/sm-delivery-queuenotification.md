---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# 佇列通知

請求將參照傳遞範本的通知排入佇列。

```text
QueueNotification ( String scenarioName, XML target )
```

## 參數

**scenarioName**&#x200B;範本的內部名稱

**目標**&#x200B;傳遞目標母體

## 傳回值

無。

## 備註

此API只能用於網頁應用程式/線上調查的內容中。 與SubmitNotification不同，QueueNotification使用專用執行緒來處理排入佇列的通知。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
