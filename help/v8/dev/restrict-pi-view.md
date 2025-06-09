---
title: 限制 PI 檢視
description: 瞭解如何限制PI檢視
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 8ff207246bea1f476b37b1d4f2c79498362e7481
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# 限制 PI 檢視{#restricting-pii-view}

## 概觀 {#overview}

如果您希望行銷使用者能夠存取資料記錄，但不希望他們看到收件者個人資訊(PI) （例如名字、姓氏或電子郵件地址），請套用以下准則來保護隱私權，並防止資料被一般行銷活動操作員濫用。

## 實施 {#implementation}

可套用至任何元素或屬性的特定屬性已新增至結構描述，它補充了現有的屬性&#x200B;**[!UICONTROL visibleIf]**。 此屬性是： **[!UICONTROL accessibleIf]**。 當包含與目前使用者內容相關的XTK運算式時，它可以利用&#x200B;**[!UICONTROL HasNamedRight]**&#x200B;或&#x200B;**[!UICONTROL $(login)]**，例如。

您可以找到收件者綱要擴充功能的範例，此範例顯示以下用法：

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

主要屬性為：

* **[!UICONTROL visibleIf]**：隱藏中繼資料中的欄位，因此無法在結構描述檢視、資料行選取範圍或運算式產生器中存取這些欄位。 但這不會隱藏任何資料，如果手動在運算式中輸入欄位名稱，則會顯示值。
* **[!UICONTROL accessibleIf]**：隱藏產生的查詢中的資料（以空白值取代）。 如果visibleIf空白，則會取得與&#x200B;**[!UICONTROL accessibleIf]**&#x200B;相同的運算式。

在Campaign中使用此屬性的後果如下：

* 將不會使用主控台中的一般查詢編輯器顯示資料。
* 資料不會顯示在概述清單和記錄清單（主控台）中。
* 詳細檢視中的資料將變成唯讀。
* 資料只能在篩選器中使用（這表示使用某些二分法策略，您仍然可以猜測值）。
* 任何使用受限制欄位建立的運算式也會受到限制： lower(@email)會變得像@email一樣可供存取。
* 在工作流程中，您可以將受限制的欄新增至目標母體，作為轉變的額外欄，但Adobe Campaign使用者仍無法存取。
* 將目標母體儲存在群組（清單）中時，所儲存欄位的特性與資料來源相同。
* 依預設，JS程式碼無法存取資料。

>[!IMPORTANT]
>
>在關鍵引數（例如複合索引鍵中的引數）上使用&#x200B;**accessibleIf**&#x200B;屬性可能會導致使用者因隱藏資料而無法讀取資料的錯誤。 這可能會導致查詢失敗或意外的行為。 確保基本引數可供存取，以避免中斷。

## 建議 {#recommendations}

在每次傳遞中，電子郵件地址都會複製到&#x200B;**[!UICONTROL broadLog]**&#x200B;和&#x200B;**[!UICONTROL forecastLog]**&#x200B;資料表中：因此，這些欄位也需要受到保護。

以下為實作此專案的記錄表擴充功能範例：

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
>此限制僅適用於非技術使用者，不會隔離資料：具有相關許可權的技術使用者可以擷取資料。
