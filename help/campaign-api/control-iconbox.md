---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 3%
---
# 圖示方塊

可啟用多頁選擇的圖示清單。

![Iconbox控制項](assets/iconbox.05daa4bf.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**名稱 — 字串**&#x200B;容器識別碼。

**左內邊距 — 整數**&#x200B;容器左邊的空間（畫素）。

**右內距 — 整數**&#x200B;容器右側的空格（以畫素為單位）。

**padding-top — 容器上方的整數**&#x200B;空間（畫素）。

**下內邊距 — 整數**&#x200B;容器下方的空間（以畫素為單位）。

**內距 — 容器周圍的整數**&#x200B;畫素。

**readOnly — 布林值**&#x200B;強制控制項及其所有子系為唯讀。

## 備註

每個容器子元素代表一個頁面。 範例：

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
