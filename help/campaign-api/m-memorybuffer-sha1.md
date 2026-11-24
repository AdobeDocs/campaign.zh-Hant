---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

計算MemoryBuffer內容的SHA-1簽名。

```text
sha1 ()
```

## 參數

無。

## 傳回值

字元字串，即SHA-1簽名的十六進位表示。

## 備註

範例：

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## 功能

**類別的方法：** [MemoryBuffer](c-memorybuffer.md)

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
