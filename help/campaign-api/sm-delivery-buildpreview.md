---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 34%
---
# 建置預覽

建立要傳遞的內容預覽或是輸出檔案的某一行的預覽 (在外部模式下)。

```text
[ XML preview, XML queryResult ] = delivery.BuildPreview ( XML params ) const
```

## 參數

**引數**&#x200B;收件者篩選條件(@filter = &#39;@id = 5673&#39;)，內容識別碼(@content = &#39;html&#39;， &#39;text&#39;， &#39;sms&#39;， &#39;webContent1&#39;， &#39;outputFile&#39;...)，@targetPart = 1345686...

## 傳回值

**預覽**&#x200B;傳回產生的預覽的所有引數

**queryResult**&#x200B;傳回載入的資料，以計算預覽。

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

否

**常數：**

是

僅&#x200B;**機碼：**

否
