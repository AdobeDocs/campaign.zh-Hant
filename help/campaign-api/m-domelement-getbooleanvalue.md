---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getbooleanvalue

傳回給定XPath所參考的布林節點值。

```text
getBooleanValue (xpath)
```

## 參數

**xpath**&#x200B;路徑。

## 傳回值

如果參考節點的文字值為「true」或「1」，則為true，則為false或「0」。

## 備註

XPath的語法只接受XPath語言子集。 值測試不區分大小寫。 如果路徑格式錯誤或值不是有效的布林值，則會引發例外狀況。

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
