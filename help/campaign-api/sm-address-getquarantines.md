---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

檢索最新的隔離和隔離退出。

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## 參數

**startDate**&#x200B;擷取自此日期以來修改的隔離。 當為空時，會使用指標值。

**pointerName**&#x200B;擷取自從此指標之後修改的隔離（選擇性）。

**quarantineCount**&#x200B;要擷取的隔離區數上限，前提是隔離區沒有在同一秒內更新。

**callerDate**&#x200B;呼叫者參考日期。 可讓您修改隔離日期參考（選用）。

## 傳回值

**結果**&#x200B;輸出檔案，隔離區清單。

**nextDate**&#x200B;第一個未擷取隔離的日期（嚴格高於startDate）。

**擁有更多**&#x200B;如果是，則仍有隔離區可供擷取。

## 功能

**結構描述：** [nms:address](s-nms-address.md)

**靜態：**

是
