---
solution: Campaign
product: Adobe Campaign
title: 限制PI視圖
description: 瞭解如何限制PI檢視
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---

# 限制PI視圖{#restricting-pii-view}

## 概觀 {#overview}

如果您需要行銷使用者能夠存取資料記錄，但不希望他們看到收件者個人資訊(PI)，例如名字、姓氏或電子郵件地址，請套用下列准則以保護隱私權，並防止一般行銷活動營運商誤用資料。

## 實施{#implementation}

可以應用於任何元素或屬性的特定屬性已添加到方案中，它補充了現有屬性&#x200B;**[!UICONTROL visibleIf]**。 此屬性為：**[!UICONTROL accessibleIf]**。 例如，當包含與當前用戶上下文相關的XTK表達式時，它可以利用&#x200B;**[!UICONTROL HasNamedRight]**&#x200B;或&#x200B;**[!UICONTROL $(login)]**。

您可以找到以下顯示此用法的收件者結構擴展示例：

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

* **[!UICONTROL visibleIf]** :隱藏中繼資料中的欄位，因此無法在架構檢視、欄選取或運算式產生器中存取欄位。但這不會隱藏任何資料，如果欄位名稱是手動輸入在運算式中，值就會顯示。
* **[!UICONTROL accessibleIf]** :隱藏資料（以空值取代資料），以免產生查詢。如果visibleIf為空，則其獲得與&#x200B;**[!UICONTROL accessibleIf]**&#x200B;相同的表達式。

以下是在促銷活動中使用此屬性的後果：

* 控制台中不會使用一般查詢編輯器顯示資料，
* 概述清單和記錄清單（主控台）中不會顯示資料。
* 資料將在詳細檢視中變成唯讀。
* 資料只能在篩選器中使用（這表示使用某些二分法策略，您仍可以猜測值）。
* 使用限制欄位建立的任何運算式也會受到限制：lower(@email)變得和@email一樣可存取。
* 在工作流程中，您可以將受限制的欄新增至目標人口，作為轉場的額外欄，但Adobe Campaign使用者仍無法存取。
* 將目標人口儲存在群組（清單）中時，儲存欄位的特性與資料來源相同。
* 依預設，JS程式碼無法存取資料。

## 建議 {#recommendations}

在每次傳送中，電子郵件地址都會複製到&#x200B;**[!UICONTROL broadLog]**&#x200B;和&#x200B;**[!UICONTROL forecastLog]**&#x200B;表格中：因此，這些欄位也需要受到保護。

以下是實施此功能的日誌表擴展示例：

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
>此限制僅適用於非技術使用者，且不會隔離資料：具有相關權限的技術使用者可以擷取資料。
