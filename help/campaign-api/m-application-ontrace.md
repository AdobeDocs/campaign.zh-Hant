---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

新增或刪除追蹤訊息攔截函式。

```text
onTrace ( [function ])
```

## 參數

**函式**&#x200B;要新增的攔截函式。 若省略此引數，則會刪除最近新增的函式。

## 傳回值

無。

## 備註

函式接受和物件搭配以下屬性做為引數：

* 重力（字串） — 訊息嚴重性（「錯誤」、「警告」、「資訊」、「狀態」、「詳細」）
* 型別（字串） — 訊息型別（「記錄」、「wdbc」等）
* 訊息（字串） — 訊息

函式受到防止重新進入的保護：它不會攔截它自己建立的追蹤訊息。 範例：

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
