---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%
---
# getdatvalue

傳回指定XPath所參考之節點的日期+小時型別值。

```text
getDateValue (xpath)
```

## 參數

**xpath**&#x200B;路徑。

## 傳回值

符合參考節點值的Date型別物件。

## 備註

XPath的語法只接受XPath語言子集。 如果路徑格式錯誤或值不是有效日期，則會引發例外狀況。

## 功能

**類別的方法：** [DOMElement](c-domelement.md)

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
