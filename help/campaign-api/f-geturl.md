---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

從URL復原文字內容。

```text
getUrl (url [, timeout ])
```

## 參數

**url**&#x200B;要復原的頁面位址。

**逾時**&#x200B;連線逾時。 如果無法在指定的延遲內建立連線，則會引發錯誤並中斷指令碼。

## 傳回值

包含文字頁面的字元字串。

## 備註

傳回字串的編碼是回應(Content-Type)指定的編碼。 如果下載期間發生錯誤或傳回碼不是200 （確定），則會引發錯誤並中斷正在執行的指令碼。 範例：

```javascript
      var content = getUrl("http://www.google.com/index.html")
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
