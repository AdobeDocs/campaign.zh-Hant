---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 7%
---
# get

載入並傳回與指定結構描述和索引鍵對應的實體。

```text
get ( [key or content ])
```

## 參數

**索引鍵或內容**&#x200B;與XML內容實體索引鍵對應的字元字串，用以建立或起始新實體。

## 傳回值

以JavaScript物件的形式傳回實體。

## 備註

get不是全域函式，而是結構描述方法。 若要叫用它，您必須以所需的結構描述做為它的字首。 例如：

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

這個物件的屬性和子屬性可以隨意修改。 如果修改檔案，當指令碼完成執行時，檔案會自動儲存在資料庫中。 如果這不是建立作業，且實體尚未在資料庫中，則會發生錯誤，且指令碼會中斷。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
