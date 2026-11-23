---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# 節點值

節點值。 該值取決於節點的型別。

```text
nodeValue
```

## 備註

此屬性可使用讀取和寫入許可權來存取。 擷取主旨行，並將其新增至工作流程中查詢活動的其他資料中的範例：

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

從工作流程中的擴充活動中擷取主旨明細行的範例：

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## 功能

類別的&#x200B;**屬性：** [DOMNode](c-domnode.md)

**唯讀：**

是

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
