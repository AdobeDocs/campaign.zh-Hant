---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# SubFormLink

開啟子表單的連結。

![SubFormLink控制項](assets/urlbutton.d1cf6f42.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**discardReadOnly — 字串**&#x200B;防止將「唯讀」屬性傳播至子表單。

**font-size - integer**&#x200B;變更字型大小。

**img — 字串**&#x200B;相關影像。

**標籤 — 字串**&#x200B;按鈕標籤。

**nolabel — 字串**&#x200B;可讓您將控制項與標籤欄對齊。

**prebuildSubForm — 字串**&#x200B;在建立控制項時初始化子表單。 此選項預設為啟用，但可以停用以加速初始顯示。

## 備註

範例：

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
