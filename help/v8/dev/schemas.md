---
title: 使用Campaign綱要
description: 開始使用結構描述
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 5%

---

# 使用方案{#gs-ac-schemas}

並以 XML 描述了應用程式中資料的實體和邏輯結構。它會遵循Adobe Campaign特有的語法，稱為 **綱要**.

綱要是與資料庫表格相關聯的XML檔案。 它定義資料結構，並描述表格的SQL定義：

* 資料表的名稱
* 欄位
* 與其他表格的連結

它也說明用來儲存資料的XML結構：

* 元素和屬性
* 元素階層
* 元素和屬性型別
* 預設值
* 標籤、說明和其他屬性。

結構描述可讓您定義資料庫中的實體。 每個實體都有一個結構描述。

Adobe Campaign採用資料結構描述來：

* 定義應用程式內的資料物件如何繫結至基礎資料庫表格。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

如需Campaign內建表格及其互動的詳細資訊，請參閱 [本節](datamodel.md).

>[!CAUTION]
>
>某些內建的Campaign結構描述在雲端資料庫上具有相關聯的結構描述。 這些結構描述的識別方式為 **Xxl** 名稱空間和不可修改或擴充。

## 結構描述的語法 {#syntax-of-schemas}

結構描述的根元素為 **`<srcschema>`**. 它包含 **`<element>`** 和 **`<attribute>`** 子元素。

第一個 **`<element>`** 子元素與實體的根一致。

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

此 **`<element>`** 標籤定義實體元素的名稱。 **`<attribute>`** 架構的標籤會定義 **`<element>`** 連結至的標籤。

## 結構描述的識別 {#identification-of-a-schema}

資料結構會以其名稱和名稱空間來識別。

名稱空間可讓您依感興趣的區域來分組一組結構描述。 例如， **cus** 名稱空間用於客戶特定的設定(**客戶**)。

>[!CAUTION]
>
>作為標準，名稱空間的名稱必須簡潔，而且根據XML命名規則，只能包含授權字元。
>
>識別碼不能以數字字元開頭。

## 保留的名稱空間 {#reserved-namespaces}

某些名稱空間是保留的，用於說明Adobe Campaign應用程式運作所需的系統實體。 以下名稱空間 **不得使用** 若要識別任何大寫/小寫組合中的新結構描述：

* **xxl**：保留給雲端資料庫結構
* **xtk**：保留給平台系統資料
* **nl**：保留給應用程式的整體使用
* **nms**：保留給傳遞（收件者、傳遞、追蹤等）
* **ncm**：保留給內容管理
* **temp**：保留給臨時結構描述
* **crm**：保留給CRM聯結器整合

結構描述的識別索引鍵是使用名稱空間和以冒號分隔的名稱建置的字串；例如： **nms：recipient**.

## 建立或擴充Campaign綱要 {#create-or-extend-schemas}

若要將欄位或其他元素新增至Campaign的其中一個核心資料結構，例如收件者表格(nms：recipient)，您必須擴充該結構。

![](../assets/do-not-localize/glass.png) 有關詳細資訊，請參閱 [擴充綱要](extend-schema.md).

若要新增Adobe Campaign中不存在的全新資料型別（例如合約表格），您可以直接建立自訂結構描述。

![](../assets/do-not-localize/glass.png) 有關詳細資訊，請參閱 [建立新結構描述](create-schema.md).

![](assets/schemaextension_1.png)


建立或擴充要使用的結構描述後，最佳實務便是以其XML內容元素在下方出現的順序來定義該元素。

## 分項清單 {#enumerations}

列舉會先於結構描述的主要元素之前定義。 它們可讓您在清單中顯示值，以限制使用者對指定欄位擁有的選擇。

範例:

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
>您也可以使用使用者管理的分項清單(通常位於 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** )來指定指定欄位的值。 這些實際上是全域分項清單，如果您的分項清單可能用於您正在使用的特定結構描述之外，那麼這是更好的選擇。

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

## 金鑰 {#keys}

每個資料表都必須至少有一個索引鍵，且通常會使用，在結構描述的主要元素中自動建立該資料表。 **autopk** 屬性設定為 **true**.

此外，在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，使用 **@autouuid** 並將其設定為 **true**.

主索引鍵也可使用定義 **內部** 屬性。

範例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此範例中，不要讓 **@autopk** 或 **@autouuid** 屬性會建立名為「id」的預設主索引鍵，我們指定自己的「householdId」主索引鍵。

>[!CAUTION]
>
>建立新結構描述或在結構描述擴充期間，您需要為整個結構描述保留相同的主要索引鍵序列值(@pkSequence)。

![](../assets/do-not-localize/glass.png) 進一步瞭解中的金鑰 [本節](database-mapping.md#management-of-keys).

## 屬性（欄位） {#attributes--fields-}

屬性可讓您定義組成資料物件的欄位。 您可以使用 **[!UICONTROL Insert]** 結構描述版本工具列中的按鈕，將空白屬性範本拖放至游標所在的XML中。 在[本章節](create-schema.md)了解更多資訊。

![](assets/schemaextension_2.png)

完整的屬性清單可在 `<attribute>` 中的元素區段 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html#content-model). 以下是一些較常用的屬性： **@advanced**， **@dataPolicy**， **@default**， **@desc**， **@enum**， **@expr**， **@label**， **@length**， **@name**， **@notNull**， **@required**， **@ref**， **@xml**， **@type**.

![](../assets/do-not-localize/book.png) 如需每個屬性的詳細資訊，請參閱下列連結中的「屬性」說明： [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

### 範例 {#examples}

定義預設值的範例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

將通用屬性作為標示為必要欄位的範本的範例：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用隱藏的計算欄位範例 **@advanced** 屬性：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

XML欄位範例也儲存在SQL欄位中，而且具有 **@dataPolicy** 屬性。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>雖然大多數屬性是根據1-1基數連結到資料庫的實體欄位，但XML欄位或計算欄位則不是這種情況。\
>XML欄位會儲存在表格的備忘錄欄位(「mData」)中。\
>不過，計算欄位會在每次啟動查詢時動態建立，因此只存在於應用程式層中。

## 連結 {#links}

連結是結構描述中主要元素的最後幾個元素。 它們定義執行個體中所有不同的結構描述如何彼此關聯。

在包含下列專案的結構描述中宣告連結： **外部索引鍵** 連結至的表格中。

基數有三種型別：1-1、1-N和N-N。這是預設使用的1-N型別。

### 範例 {#examples-1}

收件者表格（現成可用的綱要）和自訂交易表格之間的1-N連結範例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自訂結構「Car」（位於「cus」名稱空間）與收件者表格之間的1-1連結範例：

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

結構描述底部可能想要包含一個有用元素，即追蹤元素（稽核軌跡）。

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
>修改不會影響資料庫結構時，您只需要重新產生結構描述即可。 要執行此操作，請選取要更新的結構描述，按一下滑鼠右鍵並選擇 **[!UICONTROL Actions > Regenerate selected schemas...]**.
