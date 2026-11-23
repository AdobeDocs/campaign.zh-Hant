---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

載入元件清單，以進行相依性關係的預先處理 (個人化區塊、選項、其他指令碼物件等)。

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## 參數

**ids**&#x200B;以逗號分隔的元件識別碼清單（例如：&#39;option\|NmsServer\_URL\|text，includeView\|UnsubscriptionLink\|html&#39;）。

## 傳回值

**素材**&#x200B;傳回內容為「素材」元素。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

否

**常數：**

是

僅&#x200B;**機碼：**

否
