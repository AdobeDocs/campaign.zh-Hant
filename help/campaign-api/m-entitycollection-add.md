---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# 新增

將新實體新增至集合。

```text
add ( [index ], xml)
```

## 參數

**index**&#x200B;將在此索引點新增實體。 如果未指定此引數，實體將會附加至清單的結尾。

**xml**&#x200B;要插入XML表單的實體。

## 傳回值

已建立的元素。

## 備註

下列範例顯示兩種將新要素加入集合的不同方式。 第一個解決方案會將元素的完整定義傳遞給add()方法，第二個解決方案則會傳遞和空的&lt;attachment/>元素，然後以正常方式指派屬性。

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

這兩個解決方案相同，但第二個解決方案可讓您使用與屬性型別相對應的JavaScript型別，而第一個解決方案僅支援字串。

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
