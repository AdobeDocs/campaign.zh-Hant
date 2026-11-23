---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

測試是否已安裝套件。

```text
hasPackage (name)
```

## 參數

**名稱**&#x200B;封裝的完整名稱。

## 傳回值

如果已安裝套件，則為真。

## 備註

範例：

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

## 功能

**類別的方法：** [應用程式](c-application.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
