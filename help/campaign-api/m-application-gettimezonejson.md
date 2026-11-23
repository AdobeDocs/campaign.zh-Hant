---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

傳回字元字串，此字元是時間差異清單的JSON表示法，與UTC時間及其開始日期的時區比較，是UNIX期間。

```text
getTimezoneJson ( [timezone ])
```

## 參數

**時區**&#x200B;您需要傳回與UTC時差清單的時區名稱。 每次差異都會連結至適用的開始日期，直到下一個開始日期。 如果未傳回值，則使用預設運運算元時區。

## 傳回值

傳回字元字串，此字元字串是依據日期套用之時間差異的JSON表示法。 傳回的JSON字串會在{startDate， offset}對的表格中評估。 傳回的字元字串格式如下：

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate是開始套用延時的Posix時間。
* offset是與UTC的時間差異值（以毫秒為單位）。 例如UTC+02:00等於7200000。

## 備註

透過應用程式例項呼叫getTimezoneJson。

```javascript
var tzList = eval(application.getTimezoneJson());
```

## 功能

**類別的方法：** [應用程式](c-application.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
