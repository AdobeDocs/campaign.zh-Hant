---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 3%
---
# 代碼編輯

用於編輯原始程式碼的控制項。

![CodeEdit控制項](assets/codeedit.8a744c8b.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**contentType - string**&#x200B;原始程式碼的語言，用於語法色彩和其他連結至語言的選項。 支援下列語言：

* 預設
* xml
* dtd
* xsl
* html
* txt
* JavaScript
* sql

編輯與nlclient.exe位於相同目錄中的editor.cfg檔案，也可以新增其他語言。

**font-size - integer**&#x200B;變更字型大小。

**標籤 — 字串**&#x200B;關聯的標籤。

**nolabel — 布林值**&#x200B;隱藏關聯的標籤。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

**工具 — 布林值**&#x200B;顯示或隱藏工具列。

**toolbarAlign — 字串**&#x200B;工具列位置：水平或垂直。

## 備註

範例：

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
