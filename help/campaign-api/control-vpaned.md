---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%
---
# 已預覽

水準排列數個容器。

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

每個子元素都必須是一個容器。 由於width-percent屬性，每個子容器都可以指定他們要使用的總寬度的百分比。 範例：

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
