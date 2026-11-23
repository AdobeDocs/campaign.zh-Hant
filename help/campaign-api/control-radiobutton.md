---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 2%
---
# RadioButton

選項按鈕可讓您從數個選項中進行選擇。 &lt;input>標籤可用來列舉可能的選項。

![選項按鈕控制項](assets/radio.11bc90a8.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項的邊框樣式（實線、雙線、內縮、外凸、無）。

**checkedValue — 連結至選擇的字串**&#x200B;值。

**font-size - integer**&#x200B;變更字型大小。

**標籤 — 字串**&#x200B;關聯的標籤。

**nolabel — 布林值**&#x200B;隱藏關聯的標籤。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

## 備註

範例：

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
