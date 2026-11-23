---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

將字元字串轉換為XML格式。

```text
escapeXmlStr (value)
```

## 參數

**值**&#x200B;要轉換的字元字串。

## 傳回值

轉換後的字元字串。

## 備註

函式會將&amp;、&lt;、>和\\」字元轉換為對應的逸出序列：

* &amp;amp；
* &lt; &lt;
* &#x200B;> >
* &quot; &quot;

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
