---
solution: Campaign Classic
product: campaign
title: 擴充促銷活動結構
description: 瞭解如何擴充促銷活動結構描述
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# 擴展模式{#extend-schemas}

本文介紹了如何配置擴展模式，以擴展Adobe Campaign資料庫的概念資料模型。

：球：如需深入瞭解促銷活動內建表格及其互動，請參閱[本頁](datamodel.md)。

並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為&#x200B;**schema**。

方案是與資料庫表關聯的XML文檔。 它定義了資料結構，並描述了表的SQL定義：

* 表的名稱
* 欄位
* 與其他表格的連結

此外，也說明用來儲存資料的XML結構：

* 元素和屬性
* 元素階層
* 元素和屬性類型
* 預設值
* 標籤、說明和其他屬性。

結構使您能夠定義資料庫中的實體。 每個實體都有一個架構。

## 結構{#syntax-of-schemas}的語法

架構的根元素為&#x200B;**`<srcschema>`**。 它包含&#x200B;**`<element>`**&#x200B;和&#x200B;**`<attribute>`**&#x200B;子元素。

第一個&#x200B;**`<element>`**&#x200B;子元素與實體的根重合。

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>實體的根元素與架構同名。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;標籤定義實體元素的名稱。 **`<attribute>`** 架構的標籤定義了已連結到的標 **`<element>`** 記中屬性的名稱。

## 方案{#identification-of-a-schema}的標識

資料架構由其名稱及其命名空間標識。

命名空間可讓您依目標區域對一組結構描述進行分組。 例如，**cus**&#x200B;命名空間用於客戶特定的配置(**customers**)。

>[!CAUTION]
>
>作為標準，命名空間的名稱必須簡明扼要，且必須只包含符合XML命名規則的授權字元。
>
>標識符不能以數字字元開頭。

某些名稱空間保留用於說明操作Adobe Campaign應用程式所需的系統實體：

* **xxl**:關於雲資料庫架構，
* **xtk**:平台系統資料，
* **nl**:關於應用程式的整體使用，
* **nms**:傳送（收件者、傳送、追蹤等）,
* **ncm**:內容管理，
* **臨時**:為臨時方案保留。

模式的標識鍵是使用命名空間和名稱以冒號分隔的字串；例如：**nms:recipient**。
