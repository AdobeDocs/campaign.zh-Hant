---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# 連結編輯

用於編輯連結的控制項。

![LinkEdit控制項](assets/linkedit.7cb7bf14.png)

## 屬性

**backColor — 字串**&#x200B;背景顏色（btnshadow，白色）。

**邊框 — 字串**&#x200B;變更控制項輪廓樣式（實線、雙線、內縮、外凸、無）。

**choiceButton — 布林值**&#x200B;隱藏或顯示選擇按鈕（預設為隱藏）。

**computeStringExpr — 字串**&#x200B;計算欄位運算式。

**computestringKey — 字串**&#x200B;會更新計算字串而非外部索引鍵。

**computeStringAlias — 字串**&#x200B;計算字串別名。

**createMode - string**&#x200B;如果連結不存在（無、內嵌），則以預設編輯模式建立連結。

**externalKey — 布林值**&#x200B;使用外部金鑰。

**font-size - integer**&#x200B;變更字型大小。

**表單 — 字串**&#x200B;強制連結編輯表單。

**標籤 — 字串**&#x200B;關聯的標籤。

**loadEntityOnChange — 布林值**&#x200B;在連結變更時重新載入實體。

**強制 — 布林值**&#x200B;拒絕空值。

**noAutoComplete — 布林值**&#x200B;停用自動完成模式。

**noEdition — 布林值**&#x200B;無法修改連結。

**nolabel — 布林值**&#x200B;隱藏關聯的標籤。

**notifyPathList — 字串**&#x200B;要載入內容的XPath清單（以逗號分隔連結的元素）。

**noTransaction — 布林值**&#x200B;停用交易模式。

**noZoom — 布林值**&#x200B;沒有連結編輯表單。

**orderBy — 專案**&#x200B;選擇排程。

**readOnly — 布林值**&#x200B;強制控制項為唯讀。

**必要 — 布林值**&#x200B;欄位是必要的。

**結構描述 — 連結的結構描述**。

**序列化 — 布林值**&#x200B;儲存使用者設定中的最後一個選取專案。

**sysFilter — 專案**&#x200B;選擇的限制。

**xpathMandatory - string**&#x200B;布林值屬性的路徑，指出連結是否可以空白。

## 備註

範例：

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
