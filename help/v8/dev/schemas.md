---
product: Adobe Campaign
title: 使用Campaign綱要
description: 開始使用結構
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 5%

---

# 使用方案{#gs-ac-schemas}

並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為&#x200B;**schema**。

架構是與資料庫表關聯的XML文檔。 它定義了資料結構並描述了表的SQL定義：

* 表的名稱
* 欄位
* 與其他表的連結

它還描述了用於儲存資料的XML結構：

* 元素和屬性
* 元素階層
* 元素和屬性類型
* 預設值
* 標籤、說明和其他屬性。

結構可讓您定義資料庫中的實體。 每個實體都有結構。

Adobe Campaign採用資料結構：

* 定義應用程式內資料物件與基礎資料庫表的連結方式。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

如需深入了解Campaign內建表格及其互動，請參閱[此區段](datamodel.md)。

>[!CAUTION]
>
>某些內建Campaign結構在雲端資料庫上有相關聯的結構。 這些結構由&#x200B;**Xxl**&#x200B;命名空間識別，不得修改或擴充。

## 架構的語法{#syntax-of-schemas}

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
>實體的根元素與架構的名稱相同。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;標籤定義實體元素的名稱。 **`<attribute>`** 架構的標籤定義了已連結的標 **`<element>`** 簽中的屬性名稱。

## 架構{#identification-of-a-schema}的標識

資料結構以其名稱及其命名空間來識別。

命名空間可讓您依感興趣區域對一組結構進行分組。 例如， **cus**&#x200B;命名空間用於客戶特定配置(**customers**)。

>[!CAUTION]
>
>標準而言，命名空間的名稱必須簡明扼要，並且必鬚根據XML命名規則僅包含授權的字元。
>
>識別碼不得以數字字元開頭。

## 保留的命名空間{#reserved-namespaces}

某些命名空間會保留給Adobe Campaign應用程式運作所需系統實體的說明。 下列命名空間&#x200B;**不得用於**&#x200B;以識別任何大寫/小寫組合的新架構：

* **xxl**:保留給雲資料庫架構
* **xtk**:保留給平台系統資料
* **nl**:保留給應用程式的整體使用
* **nms**:保留給傳送（收件者、傳送、追蹤等）
* **ncm**:保留給內容管理
* **臨時**:保留給臨時方案
* **crm**:保留給CRM連接器整合

架構的識別索引鍵是使用命名空間建立的字串，以及以冒號分隔的名稱；例如：**nms:recipient**。

## 建立或擴充Campaign綱要{#create-or-extend-schemas}

若要將欄位或其他元素新增至Campaign中的其中一個核心資料結構，例如收件者表格(nms:recipient)，您必須擴充該結構。

[!DNL :bulb:] 如需詳細資訊，請參閱 [擴充結構](extend-schema.md)。

若要新增Adobe Campaign中不存在的全新資料類型（例如合約表格），您可以直接建立自訂結構。

[!DNL :bulb:] 如需詳細資訊，請參 [閱建立新結構](create-schema.md)。

![](assets/schemaextension_1.png)


建立或擴充結構以便使用後，最佳實務是依照其XML內容元素在下方的顯示順序來定義其XML內容元素。

## 分項清單 {#enumerations}

先在架構的主要元素之前定義列舉。 它們可讓您在清單中顯示值，以限制使用者對指定欄位的選擇。

範例:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

定義欄位時，您就可以像這樣使用此分項清單：

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您也可以使用使用者管理的列舉（通常位於&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]**&#x200B;下）來指定指定欄位的值。 這些實際上是全局枚舉，如果您的枚舉可能在您正在使用的特定架構之外使用，則可作為更好的選擇。

## 金鑰 {#keys}

每個表至少必須有一個鍵，且通常會使用設為&quot;true&quot;的&#x200B;**@autouuid=true**&#x200B;屬性，在架構的主要元素中自動建立該鍵。

也可以使用&#x200B;**internal**&#x200B;屬性來定義主鍵。

範例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此範例中，我們會指定自己的「househouldId」主要金鑰，而不是讓&#x200B;**@autouuid**&#x200B;屬性建立名為「id」的預設主要金鑰。

>[!CAUTION]
>
>在建立新架構或架構擴充期間，您需要為整個架構保留相同的主鍵序列值(@pkSequence)。

[!DNL :bulb:] 在本小節中深入了 [解索引鍵](database-mapping.md#management-of-keys)。

## 屬性（欄位）{#attributes--fields-}

屬性可讓您定義組成資料物件的欄位。 您可以使用方案版工具欄中的&#x200B;**[!UICONTROL Insert]**&#x200B;按鈕，將空屬性模板放置到游標所在的XML中。 進一步了解[本節](create-schema.md)。

![](assets/schemaextension_2.png)

[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model)的`<attribute>`元素區段中提供完整的屬性清單。 以下是一些最常用的屬性：**@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, ****@required **,**@ref **,**@xml **,**@type **。**

[!DNL :arrow_upper_right:] 如需每個屬性的詳細資訊，請參閱 [Campaign Classicv7檔案中的屬性說明](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)。

### 範例 {#examples}

定義預設值的範例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

將通用屬性作為欄位範本的範例，也標示為強制：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用&#x200B;**@advanced**&#x200B;屬性隱藏的計算欄位範例：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

SQL欄位中也儲存有XML欄位的示例，該欄位具有&#x200B;**@dataPolicy**&#x200B;屬性。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>雖然大多數屬性都根據1-1基數連結到資料庫的物理欄位，但XML欄位或計算欄位的情況並非如此。\
>XML欄位儲存在表的備注欄位(「mData」)中。\
>但是，每次啟動查詢時都會動態建立計算欄位，因此它僅存在於應用層中。

## 連結 {#links}

連結是結構之主要元素中的最後一些元素。 它們定義您執行個體中所有不同結構彼此的關聯方式。

連結在包含連結表&#x200B;**外鍵**&#x200B;的架構中聲明。

基數類型有三種：1-1、1-N和N-N。預設會使用1-N類型。

### 範例 {#examples-1}

收件者表格（現成可用結構）與自訂交易表格之間1-N連結的範例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自訂結構「Car」（在「cus」命名空間中）與收件者表格之間1-1連結的範例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

根據電子郵件地址而非主鍵在收件人表和地址表之間進行外部聯接的示例：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

其中，「xpath-dst」對應至目標架構中的主索引鍵，而「xpath-src」對應至來源架構中的外鍵。

## 稽核軌跡 {#audit-trail}

您可能想在結構底部加入的實用元素之一，是追蹤元素（稽核軌跡）。

請使用以下範例來包含與建立日期、建立資料的使用者、日期，以及表格中所有資料的上次修改作者相關的欄位：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新資料庫結構 {#updating-the-database-structure}

完成並保存更改後，需要將任何可能影響SQL結構的更改應用到資料庫。 要執行此操作，請使用資料庫更新助理。

![](assets/schemaextension_3.png)

如需詳細資訊，請參閱[本章節](update-database-structure.md)。

>[!NOTE]
>
>當修改不影響資料庫結構時，您只需重新產生結構即可。 要執行此操作，請選擇要更新的架構，按一下右鍵並選擇&#x200B;**[!UICONTROL Actions > Regenerate selected schemas...]** 。

