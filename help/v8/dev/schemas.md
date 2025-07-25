---
title: 使用Campaign綱要
description: 開始使用結構描述
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 5%

---

# 使用結構描述{#gs-ac-schemas}

並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為&#x200B;**結構描述**。

綱要是與資料庫表格相關聯的XML檔案。 它會定義資料結構，並描述表格的SQL定義：

* 資料表的名稱
* 欄位
* 與其他表格的連結

它也會說明用來儲存資料的XML結構：

* 元素和屬性
* 元素的階層
* 元素和屬性型別
* 預設值
* 標籤、說明和其他屬性。

結構描述可讓您定義資料庫中的實體。 每個實體都有一個結構描述。

Adobe Campaign採用資料結構描述來：

* 定義應用程式內的資料物件如何繫結至基礎資料庫表格。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

如需深入瞭解Campaign內建表格及其互動，請參閱[本節](datamodel.md)。

>[!CAUTION]
>
>某些內建的Campaign方案在雲端資料庫上有關聯的方案。 這些結構描述由&#x200B;**Xxl**&#x200B;名稱空間識別，不得修改或延伸。

## 結構描述的語法 {#syntax-of-schemas}

結構描述的根專案是&#x200B;**`<srcschema>`**。 它包含&#x200B;**`<element>`**&#x200B;和&#x200B;**`<attribute>`**&#x200B;個子元素。

第一個&#x200B;**`<element>`**&#x200B;子元素與實體的根一致。

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
>實體的根元素與結構描述同名。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;標籤定義實體元素的名稱。 結構描述的&#x200B;**`<attribute>`**&#x200B;標籤會定義這些標籤所連結到&#x200B;**`<element>`**&#x200B;標籤中的屬性名稱。

## 結構描述的識別 {#identification-of-a-schema}

資料結構是以其名稱和名稱空間來識別。

名稱空間可讓您依感興趣的區域來分組一組結構描述。 例如，**cus**&#x200B;名稱空間是用於客戶特定的組態（**客戶**）。

>[!CAUTION]
>
>作為標準，名稱空間的名稱必須簡潔，而且根據XML命名規則，只能包含授權字元。
>
>識別碼不能以數字字元開頭。

## 保留的名稱空間 {#reserved-namespaces}

系統會保留某些名稱空間，以說明Adobe Campaign應用程式運作所需的系統實體。 下列名稱空間&#x200B;**不可在任何大寫/小寫組合中使用**&#x200B;來識別新的結構描述：

* **xxl**：保留給雲端資料庫結構描述
* **xtk**：保留給平台系統資料
* **nl**：保留給應用程式的整體使用
* **nms**：保留給傳遞（收件者、傳遞、追蹤等）
* **ncm**：保留給內容管理
* **temp**：保留給暫存的結構描述
* **crm**：保留給CRM聯結器整合

結構描述的識別索引鍵是使用名稱空間和名稱建置的字串，以冒號分隔；例如： **nms：recipient**。

## 建立或擴充Campaign綱要 {#create-or-extend-schemas}

若要將欄位或其他元素新增至Campaign的其中一個核心資料結構，例如收件者表格(nms：recipient)，您必須擴充該結構。

如需詳細資訊，請參閱[擴充結構描述](extend-schema.md)。

若要新增Adobe Campaign中不存在的全新資料型別（例如合約表格），您可以直接建立自訂結構描述。

如需詳細資訊，請參閱[建立新的結構描述](create-schema.md)。

![](assets/schemaextension_1.png)


當您建立或擴充要使用的結構描述後，最佳實務便是以其XML內容元素在下面出現的順序來定義其XML內容元素。

## 分項清單 {#enumerations}

分項清單會先定義，在結構描述的主要元素之前。 它們可讓您在清單中顯示值，以限制使用者在指定欄位中的選擇。

範例：

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

定義欄位時，您可以使用此分項清單，如下所示：

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您也可以使用使用者管理的列舉（通常在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]**&#x200B;下）來指定指定欄位的值。 這些實際上是全域分項清單，如果您可在您使用的特定結構描述之外使用分項清單，這是較好的選擇。

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## 索引鍵 {#keys}

每個資料表都必須至少有一個索引鍵，而且通常是使用設定為&#x200B;**true**&#x200B;的&#x200B;**autopk**&#x200B;屬性，在結構描述的主要元素中自動建立它。

此外，在[企業(FFDA)部署](../architecture/enterprise-deployment.md)的內容中，使用&#x200B;**@autouuid**&#x200B;並將其設定為&#x200B;**true**。

主索引鍵也可以使用&#x200B;**internal**&#x200B;屬性來定義。

範例：

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此範例中，我們不是讓&#x200B;**@autopk**&#x200B;或&#x200B;**@autouuid**&#x200B;屬性建立名為「id」的預設主索引鍵，而是指定我們自己的「householdId」主索引鍵。

>[!CAUTION]
>
>建立新結構描述或在結構描述擴充期間，您需要為整個結構描述保留相同的主要索引鍵序列值(@pkSequence)。

在[本節](database-mapping.md#management-of-keys)中進一步瞭解金鑰。

## 屬性（欄位） {#attributes--fields-}

屬性可讓您定義組成資料物件的欄位。 您可以使用結構描述版本工具列中的&#x200B;**[!UICONTROL Insert]**&#x200B;按鈕，將空的屬性範本拖放到游標所在的XML中。 若要了解更多資訊，請參閱[此區段](create-schema.md)。

![](assets/schemaextension_2.png)

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=zh-Hant#content-model){target="_blank"}的`<attribute>`元素區段中，提供完整的屬性清單。 以下是一些較常用的屬性： **@advanced**、**@dataPolicy**、**@default**、**@desc**、**@enum**、**@expr**、**@label**、**@length**、**@name**、**@notNull**、**@required**、**@ref**、**@xml**、**@type**。

如需每個屬性的詳細資訊，請參閱[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=zh-Hant#configuring-campaign-classic){target="_blank"}中的屬性說明。

### 範例 {#examples}

定義預設值的範例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

針對也標籤為必要欄位使用通用屬性作為範本的範例：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用&#x200B;**@advanced**&#x200B;屬性隱藏的計算欄位範例：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

同樣儲存在SQL欄位中且具有&#x200B;**@dataPolicy**&#x200B;屬性的XML欄位範例。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>雖然大多數屬性都是根據1-1基數連結到資料庫的實體欄位，但XML欄位或計算欄位則不是這種情況。\
>XML欄位儲存在表格的備忘錄欄位(「mData」)中。\
>但是，計算欄位在每次查詢啟動時都會動態建立，因此只存在於應用程式層中。

## 連結 {#links}

連結是結構描述中主要元素的最後幾個元素。 它們定義您執行個體中所有不同的結構描述如何相互關聯。

在包含連結連結之資料表的&#x200B;**外部索引鍵**&#x200B;的結構描述中宣告連結。

基數有三種型別：1-1、1-N和N-N。這是預設使用的1-N型別。

### 範例 {#examples-1}

收件者表格（現成可用的綱要）與自訂交易表格之間的1-N連結範例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自訂方案「Car」（位於「cus」名稱空間）與收件者表格之間的1-1連結範例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

收件者表格和位址表格之間的外部聯結範例（根據電子郵件地址而非主索引鍵）：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

此處「xpath-dst」對應於目標架構中的主索引鍵，「xpath-src」對應於來源架構中的外部索引鍵。

## 稽核軌跡 {#audit-trail}

架構底部可能想要包含一個實用元素，即追蹤元素（稽核軌跡）。

使用下列範例來包含與建立日期、建立資料的使用者、日期和表格中所有資料的上次修改作者相關的欄位：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新資料庫結構 {#updating-the-database-structure}

完成並儲存變更後，任何可能影響SQL結構的變更都必須套用至資料庫。 要執行此操作，請使用資料庫更新輔助程式。

![](assets/schemaextension_3.png)

如需詳細資訊，請參閱[本章節](update-database-structure.md)。

>[!NOTE]
>
>當修改不會影響資料庫結構時，您只需要重新產生結構描述。 若要這麼做，請選取要更新的結構描述，按一下滑鼠右鍵並選擇&#x200B;**[!UICONTROL Actions > Regenerate selected schemas...]**。
