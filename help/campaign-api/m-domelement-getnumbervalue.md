---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%
---
# getNumberValue

傳回給定XPath參考的數位節點值。

```text
getNumberValue (xpath)
```

## 參數

**xpath**&#x200B;路徑。

## 傳回值

數位值會對應到參照的節點。

## 備註

XPath的語法只接受XPath語言子集。 如果路徑格式錯誤或值不是有效的數字，則會引發例外狀況。

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
