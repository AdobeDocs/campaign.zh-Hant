---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# 載入

> 警告：
>
> 透過檔案API的存取權僅限於&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的暫存資料夾。

載入並傳回與指定結構描述和索引鍵對應的實體。

```text
load (key)
```

## 參數

**key**&#x200B;與實體索引鍵對應的字元字串。

## 傳回值

以JavaScript物件的形式傳回實體。

## 備註

載入不是全域函式，而是結構描述方法。 若要叫用它，您必須以所需的結構描述做為它的字首。 例如：

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

這個物件的屬性和子屬性可以隨意修改。 與[get()](f-get.md)方法不同，檔案不會自動儲存在資料庫中，您必須叫用物件上的[save()](m-entity-save.md)方法。 如果在資料庫中找不到該實體，則為錯誤且指令碼會中斷。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
