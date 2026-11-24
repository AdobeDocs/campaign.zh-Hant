---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

啟用產生公用資源存取URL

```text
getImageUrl (ID|internal name)
```

## 參數

公用資源的&#x200B;**ID\|內部名稱**&#x200B;識別碼或資源的內部名稱。

## 傳回值

傳回公用資源存取網址。

## 備註

資源必須發佈在前端伺服器上。 範例：

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
```

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
