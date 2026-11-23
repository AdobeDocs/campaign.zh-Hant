---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

啟用根據公用資源產生HTML &lt;img>標籤。

```text
generateImgTag (ID)
```

## 參數

**ID**&#x200B;公用資源識別碼

## 傳回值

傳回HTML &lt;img>標籤，其中包含公用資源定義中所包含影像的屬性。

## 備註

資源必須發佈在前端伺服器上。 範例：

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
