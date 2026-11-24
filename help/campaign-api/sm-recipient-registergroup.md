---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# 登入群組

將選定的收件者新增至清單

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## 參數

**groupList**&#x200B;清單

**recipientList**&#x200B;收件者清單

**註冊**&#x200B;訂閱/取消訂閱收件者

## 傳回值

無。

## 範例

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## 功能

**結構描述：** [nms:recipient](s-nms-recipient.md)

**靜態：**

是
