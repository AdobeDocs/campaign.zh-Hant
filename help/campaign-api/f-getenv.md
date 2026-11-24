---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# getEnv

>[!WARNING]
>
>此函式適用於內部部署環境。

>[!NOTE]
>
>您可以將&#x200B;**XtkSecurity\_Disable\_GetSetEnv**&#x200B;選項傳遞給&#x200B;**true**&#x200B;以停用此函式。

傳迴環境變數的值。

```text
getEnv (name [, default ])
```

## 參數

**名稱**&#x200B;變數的名稱。

**預設**&#x200B;找不到環境變數時要使用的預設值。

## 傳回值

變數的值。

## 功能

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
