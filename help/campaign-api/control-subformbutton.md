---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%
---
# SubFormButton

開啟子表單的按鈕。

![SubFormButton控制項](assets/button.f0aea09a.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**discardReadOnly — 字串**&#x200B;防止將「唯讀」屬性傳播至子表單。

**font-size - integer**&#x200B;變更字型大小。

**img — 字串**&#x200B;相關影像。

**標籤 — 按鈕的字串**&#x200B;標籤。

**nolabel — 字串**&#x200B;可讓您對齊標籤欄上的控制項。

**prebuildSubForm — 字串**&#x200B;會在建立控制項時初始化子表單。 此選項預設為啟用，但可以停用以加速初始顯示。

**必要 — 布林值**&#x200B;欄位是必要的。

## 備註

範例：

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
