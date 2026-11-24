---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

測試運運算元是否有特定的已命名許可權。

```text
hasRight (name)
```

## 參數

**名稱**&#x200B;正確名稱。

## 傳回值

如果運運算元有此許可權，則為True。

## 備註

範例：

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## 功能

**類別的方法：** [CurrentOperator](c-currentoperator.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
