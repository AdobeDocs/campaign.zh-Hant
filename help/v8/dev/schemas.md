---
solution: Campaign Classic
product: campaign
title: 使用促銷活動結構描述
description: 結構描述快速入門
translation-type: tm+mt
source-git-commit: f1aed22d04bc0170b533bc088bb1a8e187b44dce
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 4%

---

# 使用結構{#gs-ac-schemas}

並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為&#x200B;**schema**。

方案是與資料庫表關聯的XML文檔。 它定義了資料結構，並描述了表的SQL定義：

* 表的名稱
* 欄位
* 與其他表格的連結

此外，也說明用來儲存資料的XML結構：

* 元素和屬性
* 元素階層
* 元素和屬性類型
* 預設值
* 標籤、說明和其他屬性。

結構使您能夠定義資料庫中的實體。 每個實體都有一個架構。

Adobe Campaign利用資料結構：

* 定義應用程式中資料對象與基礎資料庫表的關聯方式。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

如需深入瞭解促銷活動內建表格及其互動，請參閱[本節](datamodel.md)。

>[!CAUTION]
>
>某些內建促銷活動結構在雲端資料庫上具有關聯的結構。 這些結構描述由&#x200B;**Xxl**&#x200B;命名空間標識，不能修改。

## 結構{#syntax-of-schemas}的語法

架構的根元素為&#x200B;**`<srcschema>`**。 它包含&#x200B;**`<element>`**&#x200B;和&#x200B;**`<attribute>`**&#x200B;子元素。

第一個&#x200B;**`<element>`**&#x200B;子元素與實體的根重合。

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>實體的根元素與架構同名。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;標籤定義實體元素的名稱。 **`<attribute>`** 架構的標籤定義了已連結到的標 **`<element>`** 記中屬性的名稱。

## 方案{#identification-of-a-schema}的標識

資料架構由其名稱及其命名空間標識。

命名空間可讓您依目標區域對一組結構描述進行分組。 例如，**cus**&#x200B;命名空間用於客戶特定的配置(**customers**)。

>[!CAUTION]
>
>作為標準，命名空間的名稱必須簡明扼要，且必須只包含符合XML命名規則的授權字元。
>
>標識符不能以數字字元開頭。

## 保留的命名空間

保留某些名稱空間，以說明操作Adobe Campaign應用程式所需的系統實體。 以下命名空間&#x200B;**不得用於**&#x200B;以識別任何大寫／小寫組合的新模式：

* **xxl**:保留至雲端資料庫結構，
* **xtk**:保留給平台系統資料，
* **nl**:保留給應用程式的整體使用，
* **nms**:保留給傳送（收件者、傳送、追蹤等）,
* **ncm**:保留給內容管理，
* **臨時**:保留給臨時方案。

模式的標識鍵是使用命名空間和名稱以冒號分隔的字串；例如：**nms:recipient**。

## 建立或擴充促銷活動結構{#create-or-extend-schemas}

若要將欄位或其他元素新增至促銷活動中的其中一個核心資料結構，例如收件者表(nms:recipient)，您必須擴充該結構。

：球：有關詳細資訊，請參閱[擴展架構](extend-schema.md)。

若要新增Adobe Campaign不存在的全新資料類型（例如合約表格），您可以直接建立自訂結構。

：球：有關詳細資訊，請參閱[建立新模式](create-schema.md)。

![](assets/schemaextension_1.png)


在建立或擴充架構以開始運作後，最佳實務是依照其在下方顯示的順序定義其XML內容元素。

## 分項清單 {#enumerations}

枚舉首先在模式的主要元素之前定義。 它們可讓您在清單中顯示值，以限制使用者對指定欄位的選擇。

範例:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

在定義欄位時，您接著可以像這樣使用此列舉：

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您也可以使用使用者管理的枚舉（通常在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]**&#x200B;下）來指定指定欄位的值。 這些是有效的全局枚舉，如果您的枚舉可能在您正在使用的特定模式之外使用，則是一個更好的選擇。

## 鍵{#keys}

每個表至少必須有一個鍵，通常通過使用設定為&quot;true&quot;的&#x200B;**@autouuid=true**&#x200B;屬性，在模式的主元素中自動建立該鍵。

主鍵也可以使用&#x200B;**internal**&#x200B;屬性來定義。

範例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此範例中，我們並未讓&#x200B;**@autouuid**&#x200B;屬性建立名為&quot;id&quot;的預設主鍵，而是指定我們自己的&quot;householdId&quot;主鍵。

>[!CAUTION]
>
>建立新模式或在模式擴展期間，需要為整個模式保留相同的主鍵序列值(@pkSequence)。

：球：進一步瞭解[本節](database-mapping.md#management-of-keys)中的鍵。

## 屬性（欄位）{#attributes--fields-}

屬性可讓您定義組成資料物件的欄位。 您可以使用架構版工具列中的&#x200B;**[!UICONTROL Insert]**&#x200B;按鈕，將空的屬性範本拖放到游標所在的XML中。 進一步瞭解[本節](create-schema.md)。

![](assets/schemaextension_2.png)

[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model)部分的`<attribute>`元素部分提供了完整的屬性清單。 以下是一些較常使用的屬性：**@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **標籤a13/>,**@length **,**@name **,**@notNull **,**@required **,** ref **、**@xml **、**@type **。**

:arrow_upper_right:有關每個屬性的詳細資訊，請參閱[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)中的「屬性說明」。

### 範例 {#examples}

定義預設值的示例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

將公用屬性用作欄位範本的範例，也標示為必填欄位：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用&#x200B;**@advanced**&#x200B;屬性隱藏的計算欄位示例：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

XML欄位的示例也儲存在SQL欄位中，該欄位具有&#x200B;**@dataPolicy**&#x200B;屬性。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>雖然大多數屬性都根據1-1基數連結到資料庫的物理欄位，但XML欄位或計算欄位不適用。\
>XML欄位會儲存在表格的備注欄位(「mData」)中。\
>但是，每次啟動查詢時都會動態建立計算欄位，因此它僅存在於應用層中。

## 連結 {#links}

連結是架構中主要元素中的最後一些元素。 它們定義實例中所有不同方案如何彼此關聯。

連結在包含其連結的表的&#x200B;**外鍵**&#x200B;的模式中聲明。

基數有三種類型：1-1、1-N和N-N。預設情況下使用1-N類型。

### 範例 {#examples-1}

收件者表（現成可用方案）和自訂交易表之間1-N連結的範例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自訂架構&quot;Car&quot;（在&quot;cus&quot;命名空間中）與收件者表格之間的1-1連結範例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

收件人表和地址表之間基於電子郵件地址而不是主鍵的外部連接示例：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

這裡，&quot;xpath-dst&quot;對應於目標模式中的主鍵，&quot;xpath-src&quot;對應於源模式中的外鍵。

## 稽核軌跡 {#audit-trail}

您可能想要在結構底部加入一個有用的元素，即追蹤元素（稽核記錄）。

請使用下列範例來包含與建立日期、建立資料的使用者、日期，以及表格中所有資料的上次修改作者相關的欄位：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新資料庫結構 {#updating-the-database-structure}

完成並保存更改後，任何可能影響SQL結構的更改都需要應用到資料庫。 要執行此操作，請使用資料庫更新助理。

![](assets/schemaextension_3.png)

如需詳細資訊，請參閱[本章節](update-database-structure.md)。

>[!NOTE]
>
>如果修改不影響資料庫結構，則只需重新生成結構。 要執行此操作，請選擇要更新的架構，按一下右鍵並選擇&#x200B;**[!UICONTROL Actions > Regenerate selected schemas...]**。

