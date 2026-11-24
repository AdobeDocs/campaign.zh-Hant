---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

在執行例項上發佈交易式訊息。 如果發佈成功，則傳回true，否則傳回false。

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## 參數

要部署的傳遞的&#x200B;**deliveryId** ID

**localPublish**&#x200B;僅發佈在控制執行個體上？

## 傳回值

**isSuccess**&#x200B;發佈完成

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
