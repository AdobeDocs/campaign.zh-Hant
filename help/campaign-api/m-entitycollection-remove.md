---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 20%
---
# 移除

從集合中刪除實體。

```text
remove (index|object)
```

## 參數

**index\|object**&#x200B;要刪除的實體或實體本身的索引。

## 傳回值

無。

## 備註

範例：

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
delivery.save()
```

## 功能

**類別的方法：** [EntityCollection](c-entitycollection.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
