---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# 訂閱

建立或更新收件者的資訊服務訂閱

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## 參數

**serviceName**&#x200B;資訊服務名稱清單（以逗號分隔）

**收件者**&#x200B;要註冊並可選擇性建立的收件者

**建立**&#x200B;如果收件者不存在，則建立收件者

## 傳回值

無。

## 範例

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## 功能

**結構描述：** [nms:subscription](s-nms-subscription.md)

**靜態：**

是
