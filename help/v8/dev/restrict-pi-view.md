---
title: 限制 PI 檢視
description: 瞭解如何限制PI視圖
feature: PI, Privacy
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# 限制 PI 檢視{#restricting-pii-view}

## 概覽 {#overview}

如果您需要市場營銷用戶能夠訪問資料記錄，但不希望他們看到收件人個人資訊(PI)，例如名、姓或電子郵件地址，請應用以下准則來保護隱私並防止常規市場活動操作員濫用資料。

## 實作 {#implementation}

可應用於任何元素或屬性的特定屬性已添加到方案中，它補充了現有屬性 **[!UICONTROL visibleIf]**。 此屬性為： **[!UICONTROL accessibleIf]**。 當包含與當前用戶上下文相關的XTK表達式時，它可以利用 **[!UICONTROL HasNamedRight]** 或 **[!UICONTROL $(login)]**，例如

您可以找到以下顯示此用法的收件人架構擴展示例：

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

主要屬性有：

* **[!UICONTROL visibleIf]** :從元資料中隱藏欄位，因此在架構視圖、列選擇或表達式生成器中無法訪問這些欄位。 但這不會隱藏任何資料，如果欄位名稱是在表達式中手動輸入的，則值將顯示。
* **[!UICONTROL accessibleIf]** :隱藏資料（用空值替換它），使其無法生成查詢。 如果visibleIf為空，則獲取與 **[!UICONTROL accessibleIf]**。

以下是在市場活動中使用此屬性的後果：

* 在控制台中，不會使用通用查詢編輯器顯示資料，
* 資料在概述清單和記錄清單（控制台）中不可見。
* 資料將在詳細視圖中變為只讀。
* 資料只能在篩選器內使用（這意味著使用某些二分法策略，您仍可以猜測值）。
* 使用受限欄位生成的任何表達式也會受到限制：低(@email)與可訪問@email。
* 在工作流中，您可以將受限制列作為過渡的額外列添加到目標人口中，但Adobe Campaign用戶仍無法訪問該列。
* 當將目標群體儲存在組（清單）中時，所儲存欄位的特性與資料源相同。
* 預設情況下，JS代碼無法訪問資料。

## 建議 {#recommendations}

在每個傳遞中，電子郵件地址都複製到 **[!UICONTROL broadLog]** 和 **[!UICONTROL forecastLog]** 表：因此，這些欄位也需要保護。

下面是日誌表擴展的示例，用於實現此功能：

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>此限制僅適用於非技術用戶，不會隔離資料：具有相關權限的技術用戶可以檢索資料。
