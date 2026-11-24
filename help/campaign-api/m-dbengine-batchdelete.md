---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

依封包刪除表格的記錄。

```text
batchDelete (table, pk [, where ])
```

## 參數

**資料表**&#x200B;資料表的SQL名稱。

**pk**&#x200B;用作主索引鍵的欄位名稱。

**其中** SQL記錄篩選條件。

## 傳回值

無。

## 備註

範例：

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

運運算元需要&#39;sql&#39;許可權才能使用此函式，否則會發生例外狀況。

## 功能

**類別的方法：** [DBEngine](c-dbengine.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
