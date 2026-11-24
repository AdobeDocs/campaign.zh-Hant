---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 1%
---
# LinkListChoice

選擇一個或多個實體。

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**dblClickAction — 字串**&#x200B;按兩下要開啟的表單名稱。

**font-size - integer**&#x200B;變更字型大小。

**標籤 — 字串**&#x200B;關聯的標籤。

**multiSelection — 布林值**&#x200B;授權多個選取專案

**nolabel — 布林值**&#x200B;隱藏關聯的標籤。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

**序列化 — 布林值**&#x200B;儲存使用者組態中的最後一個選取專案。wu

**xpath-link — 字串**&#x200B;清單的連結。

## 備註

範例：

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
