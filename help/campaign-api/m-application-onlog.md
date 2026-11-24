---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

針對寫入日誌的訊息新增或刪除攔截函式

```text
onLog ( [function ])
```

## 參數

**函式**&#x200B;要新增的攔截函式。 若省略此引數，則會刪除最近新增的函式。

## 傳回值

無。

## 備註

系統會先呼叫最近新增的函式。 函式接受和物件搭配以下屬性做為引數：

* 型別（數字） — 訊息型別（0=錯誤，1=警告，2=資訊，3=狀態，4=詳細）
* 代碼（數字） — 錯誤代碼（如果不是錯誤則為0）
* 物件（字串） — 連結至訊息的物件（未使用）
* 訊息（字串） — 訊息

函式必須傳回布林值。 值true會防止任何後續的攔截函式收到訊息。 此函式受到防止重新進入的保護：它不會攔截它寫給日誌本身的訊息。 範例：

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
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
