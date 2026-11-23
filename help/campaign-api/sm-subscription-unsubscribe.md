---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# 取消訂閱

從資訊服務取消訂閱收件者

```text
Unsubscribe ( String serviceName, XML recipient )
```

## 參數

**serviceName**&#x200B;資訊服務名稱清單（以逗號分隔）

**收件者**&#x200B;收件者

## 傳回值

無。

## 範例

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## 功能

**結構描述：** [nms:subscription](s-nms-subscription.md)

**靜態：**

是
