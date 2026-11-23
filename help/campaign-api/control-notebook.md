---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# 筆記本

要顯示數個頁面的索引標籤清單。

![筆記本控制項](assets/notebook.3b531a46.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**名稱 — 字串**&#x200B;容器識別碼。

**左內邊距 — 整數**&#x200B;容器左邊的空間（畫素）。

**右內距 — 整數**&#x200B;容器右側的空格（以畫素為單位）。

**padding-top — 容器上方的整數**&#x200B;空間（畫素）。

**下內邊距 — 整數**&#x200B;容器下方的空間（以畫素為單位）。

**內距 — 容器周圍的整數**&#x200B;畫素。

**readOnly — 布林值**&#x200B;強制控制項及其所有子系為唯讀。

**樣式 — 字串**&#x200B;平坦\|向下\|向上（預設）。

## 備註

每個子元素代表一個頁面。 範例：

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
