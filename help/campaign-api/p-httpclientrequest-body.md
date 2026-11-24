---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# 內文

HTTP查詢的正文。

```text
body
```

## 備註

指派給查詢內文的物件處理方式如下：

* 未定義、null、函式：不會視為可傳送的元素，HTTP查詢的主體是空的。
* 數字、布林值、字串、XML、物件：已根據toString方法變更為字元字串，並根據HTTP標頭Content-type進行編碼。
* [MemoryBuffer](c-memorybuffer.md)：內容已複製到查詢內文中，未作變更。

範例：

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## 功能

類別的&#x200B;**屬性：** [HttpClientRequest](c-httpclientrequest.md)

**唯讀：**

否

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
