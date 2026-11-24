---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# 處置

將連線從連結到它的所有資源中釋放。

```text
dispose ()
```

## 參數

無。

## 傳回值

無。

## 備註

使用[application.getConnection()](m-application-getconnection.md)方法建立的連線會在指令碼結尾自動釋放。 呼叫此方法對於具有較長壽命的指令碼非常有用。

## 功能

**類別的方法：** [DBEngine](c-dbengine.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
