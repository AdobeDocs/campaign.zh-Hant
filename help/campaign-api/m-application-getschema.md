---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

傳回與Adobe Campaign結構描述的對應，如果結構描述不存在，則傳回null。

```text
getSchema (name [, checkIfUpdated ])
```

## 參數

**名稱**&#x200B;完整結構描述名稱。

**checkIfUpdated**&#x200B;檢查快取中是否已更新結構描述。 如果結構描述已經在指令碼中執行個體化，則沒有影響。

## 傳回值

結構描述對應（請參閱[Schema](c-schema.md)物件）或方法啟動例外狀況時，沒有與名稱相符的結構描述。

## 備註

在指令碼中具現化的所有結構描述都會保留在記憶體中，直到指令碼結尾為止。 範例：

```javascript
      var schema = application.getSchema("nms:recipient")
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
