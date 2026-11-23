---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

傳回資料庫的伺服器型別。

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## 參數

**名稱**&#x200B;資料來源的名稱。

**checkIfUpdated**&#x200B;檢查快取中已更新結構描述。 如果指令碼中已例項化結構描述，則沒有影響。

## 傳回值

包含資料庫伺服器型別的文字字串。

## 備註

如果未指定資料來源，預設函式會使用&#39;nms:default&#39;。 資料來源必須存在，否則會引發例外狀況。

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
