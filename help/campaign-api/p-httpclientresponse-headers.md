---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# 標頭

依名稱分組的HTTP回應標頭清單。

```text
headers
```

## 備註

每個標題屬性都攜帶有標題的名稱和表格的值，該值匹配每個具有此名稱的標題。 此函式不同於[標頭](p-httpclientresponse-header.md)，因為它傳回的是值表，而不是指定名稱的唯一值。 這對於可能出現多次的標頭非常有用，例如Accept-Language或Set-Cookie。 如果HTTP回應沒有使用此名稱的標頭，此函式會傳回空白表格。 範例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

標頭屬性不可專案化。 屬性名稱不區分大小寫。

## 功能

類別的&#x200B;**屬性：** [HttpClientResponse](c-httpclientresponse.md)

**唯讀：**

是

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
