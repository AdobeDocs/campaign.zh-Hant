---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection （類別）

代表實體的集合。

此類物件無法直接具現化。 您必須使用create()、get()或load()方法。

集合的元素可以使用`for`或`for each`列舉。 此範例顯示連結至傳遞動作的檔案分項清單。

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## 方法

| 方法 | 說明 |
| --- | --- |
| [新增](m-entitycollection-add.md) | 將新實體新增至集合。 |
| [移除](m-entitycollection-remove.md) | 從集合中刪除實體。 |
| [removeAll](m-entitycollection-removeall.md) | 從集合中刪除所有實體。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [長度](p-entitycollection-length.md) | 傳回集合的實體編號。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
