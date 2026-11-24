---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

自動產生用於網路追蹤的JavaScript標籤。

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## 參數

**要求** HttpServletRequest物件

**tagid**&#x200B;代表個人化tagid名稱的字元字串。 如果空白，函式會根據路徑名稱產生標籤。

**資料夾**&#x200B;代表資料夾內部名稱的字元字串。 如果空白，標籤會在預設目錄中建立，即「網頁追蹤標籤」。

## 傳回值

字元字串，其中包含要納入的JavaScript程式碼。

## 備註

產生的標籤會根據網頁應用程式的名稱、html頁面、控制項，或更一般而言，如果未輸入標籤則會根據路徑名稱。 最後一個引數會指定標籤目的地資料夾。 若要叫用函式，請將要求物件作為引數傳遞。 請注意&lt;%==的使用，因為函式會產生html程式碼。 範例：

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## 功能

**可用於：**

* JSSP
* WebApp
