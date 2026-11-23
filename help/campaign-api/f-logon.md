---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# 登入

將指令碼執行內容變更為目前的登入。

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## 參數

**sessionToken**&#x200B;要使用的工作階段權杖。

**登入**&#x200B;要使用的操作員登入。

**密碼**&#x200B;運運算元密碼。 如果目前的登入具有「管理員」許可權，則密碼可以是空字串。

**context**&#x200B;代表登入的物件，由先前登入呼叫傳回。

## 傳回值

傳回符合先前登入的物件。 這可透過將此引數傳遞至登入函式，還原先前的登入。

## 備註

範例：

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
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
