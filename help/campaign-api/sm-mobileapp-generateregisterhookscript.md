---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

產生要在「appSubscriptionRcp」的「註冊」事件期間呼叫的延伸指令碼。

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## 參數

**additionalXmlNodes** XML節點包含其他引數與目標對應欄位之間的連結。

## 傳回值

**JSScriptStr** JS指令碼，可讓您將其他引數連結到目標對應中的欄位。

## 功能

**結構描述：** [nms:mobileApp](s-nms-mobileapp.md)

**靜態：**

是
