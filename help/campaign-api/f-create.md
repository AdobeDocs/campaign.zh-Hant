---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# 建立

建立與指定結構描述對應的新實體。

```text
create ( [content ])
```

## 參數

**content**&#x200B;與要建立的實體XML對應的選擇性字元字串。

## 傳回值

以JavaScript物件的形式傳回實體。

## 備註

建立不是全域函式，而是結構描述方法。 若要叫用它，您必須以所需的結構描述做為它的字首。 例如：

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

檔案不會自動儲存至資料庫。 您必須在實體上使用⌐⌐[save()](m-entity-save.md)方法。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
