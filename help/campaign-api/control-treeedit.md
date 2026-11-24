---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# TreeEdit

控制以檢視及編輯分組在不同類別中的各種值。

![TreeEdit控制項](assets/treeedit.253f1374.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**可編輯 — 字串**&#x200B;授權修改（預設為true）。

**font-size - integer**&#x200B;變更字型大小。

**標籤 — 字串**&#x200B;關聯的標籤。

**noImage — 字串**&#x200B;隱藏清單中元素的影像。

**nolabel — 布林值**&#x200B;隱藏關聯的標籤。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

## 備註

子元素的屬性

* visibleIf：顯示或隱藏元素的XTK條件。
* label：元素的標籤。
* exprLabel：運算式形式的元素標籤。
* xpath：元素的XPath。
* img：元素的影像。

輸入子元素的屬性

* 可編輯：可編輯的值。 預設值繼承自根元素。

容器子元素的屬性

* 已摺疊： true\|false顯示或隱藏子元素。

範例：

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
