---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# 清單

記憶體清單。

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**可編輯 — 布林值**&#x200B;授權編輯清單。

**font-size - integer**&#x200B;變更字型大小。

**表單 — 字串**&#x200B;編輯表單。

**img — 字串**&#x200B;每行的影像。

**標籤 — 字串**&#x200B;關聯的標籤。

**nolabel — 布林值**&#x200B;沒有標籤。

**notitle — 布林值**&#x200B;不顯示欄標題。

**noToolbar — 布林值**&#x200B;隱藏工具列。

**已排序 — 布林值**&#x200B;授權清單排程。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

**toobarAlign — 字串**&#x200B;水準\|垂直。

**toobarCaption — 工具列中顯示**&#x200B;標籤。

**縮放 — 布林值**&#x200B;顯示編輯表單。

**zoomOnAdd — 布林值**&#x200B;新增行時開啟表單。

**xpathIndex - xpath**&#x200B;選取範圍的索引將儲存在此路徑所指定的位置。

**xpathSelection - xpath**&#x200B;要儲存XPATH路徑以到達所選元素的節點。

## 備註

範例1：

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

範例2：

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
