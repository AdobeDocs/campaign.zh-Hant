---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

傳回資料庫伺服器的目前日期。

```text
getCurrentDate ()
```

## 參數

無。

## 傳回值

資料庫伺服器的目前日期。

## 備註

範例：

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

有關formatDate()函式的詳細資訊，請參閱[formatDate(date， format)](f-formatdate.md)

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
