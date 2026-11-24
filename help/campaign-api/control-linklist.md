---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%
---
# 連結清單

編輯集合的控制項。

![LinkList控制](assets/linklist.8b71bb0e.png)

## 屬性

**addButton — 布林值**&#x200B;顯示新增按鈕。 只有在啟用hideEditButtons選項時，此選項才有效。

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**dblClickAction — 字串**&#x200B;按兩下要開啟的表單名稱。

**delButton — 布林值**&#x200B;顯示刪除按鈕。 此選項只有在啟用hideEditButtons按鈕時才有效。

**enumImage - string**&#x200B;用來顯示每行影像的系統列舉名稱。

**font-size - integer**&#x200B;變更字型大小。

**表單 — 用於連結編輯的字串**&#x200B;表單。

**hideEditButtons — 布林值**&#x200B;隱藏新增、刪除和編輯按鈕。

**img — 字串**&#x200B;影像。

**標籤 — 字串**&#x200B;關聯的標籤。

**nolabel — 布林值**&#x200B;控制項前面沒有標籤。

**noToolbar — 布林值**&#x200B;隱藏工具列。

**orderBy — 專案**&#x200B;清單排程。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

**sysFilter — 專案**&#x200B;清單篩選。

**toobarAlign — 字串**&#x200B;水準\|垂直。

**toobarCaption — 工具列中顯示**&#x200B;標籤。

**xpath-link — 字串**&#x200B;清單的連結（請參閱群組的範例）。

**xpathIndex — 字串**&#x200B;選取範圍索引將儲存在此路徑所指定的位置。

**xpathLinkEdit — 要編輯的字串**&#x200B;連結（請參閱群組範例）。

**縮放 — 布林值**&#x200B;授權連結編輯。

## 備註

範例：

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
