---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

轉換字元字串以將其插入URL中。

```text
escapeUrl (value)
```

## 參數

**值**&#x200B;要轉換的字元字串。

## 傳回值

轉換後的字元字串。

## 備註

函式會將$-\_.\！\*&#39;()，？/：@&amp;=以外的非英數字元轉換為對應的十六進位值。 函式符合RFC1738規格，且僅允許您編碼ISO — 拉丁字元。 若要編碼UTF-8字元，請使用encodeURIComponent() JavaScript函式。 範例：

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
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
