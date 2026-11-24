---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

傳回資料庫伺服器的新連線。

```text
getConnection ()
```

## 參數

無。

## 傳回值

與資料庫伺服器的[連線](c-dbengine.md)。

## 備註

可以使用[dispose](m-dbengine-dispose.md)方法，在指令碼執行結束之前釋放連線。

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
