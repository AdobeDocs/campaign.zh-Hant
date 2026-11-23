---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# 圖表編輯

此控制項用於編輯圖表，例如工作流程或調查。

![圖表編輯控制項](assets/diagramedit.d750db7e.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**標籤 — 字串**&#x200B;關聯的標籤。

**nolabel — 布林值**&#x200B;將標籤顯示為說明泡泡圖。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

## 備註

工具列可以個人化，此控制項的每個子元素都會比對工具列中的其他按鈕。

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

有關工具列按鈕的詳細資訊，請參閱SubFormButton控制檔案。
