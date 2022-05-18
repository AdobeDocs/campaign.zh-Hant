---
title: 使用市場活動架構
description: 開始使用架構
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 5%

---

# 使用方案{#gs-ac-schemas}

並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為 **架構**。

模式是與資料庫表關聯的XML文檔。 它定義了資料結構並描述了表的SQL定義：

* 表的名稱
* 欄位
* 與其他表的連結

還介紹了用於儲存資料的XML結構：

* 元素和屬性
* 元素層次
* 元素和屬性類型
* 預設值
* 標籤、說明和其他屬性。

方案使您能夠在資料庫中定義實體。 每個實體都有一個架構。

Adobe Campaign使用資料架構：

* 定義應用程式內的資料對象如何與基礎資料庫表關聯。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

要更好地瞭解活動內置表及其交互作用，請參閱 [此部分](datamodel.md)。

>[!CAUTION]
>
>某些內置市場活動架構在雲資料庫上具有關聯架構。 這些架構由 **xxl** 命名空間，不得修改或擴展。

## 架構語法 {#syntax-of-schemas}

架構的根元素為 **`<srcschema>`**。 它包含 **`<element>`** 和 **`<attribute>`** 子元素。

第一個 **`<element>`** 子元素與實體的根重合。

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

的 **`<element>`** 標籤定義實體元素的名稱。 **`<attribute>`** 模式的標籤定義 **`<element>`** 已連結到的標籤。

## 模式的標識 {#identification-of-a-schema}

資料架構由其名稱和命名空間標識。

使用命名空間可以按感興趣區域對一組架構進行分組。 例如， **番** 命名空間用於客戶特定的配置(**客戶**)。

>[!CAUTION]
>
>作為標準，命名空間的名稱必須簡潔，並且必須只包含根據XML命名規則授權的字元。
>
>標識符不能以數字字元開頭。

## 保留的命名空間 {#reserved-namespaces}

某些命名空間保留用於描述操作Adobe Campaign應用程式所需的系統實體。 以下命名空間 **不得使用** 以任何大小寫組合標識新架構：

* **xxl**:保留給雲資料庫架構
* **xtk**:保留給平台系統資料
* **n**:保留給應用程式的整體使用
* **nms**:預留給交貨（收件人、交貨、跟蹤等）
* **ncm**:保留到內容管理
* **溫度**:保留到臨時架構
* **crm**:保留到CRM連接器整合

架構的標識鍵是使用命名空間和名稱以冒號分隔的字串；例如： **nms：收件人**。

## 建立或擴展市場活動架構 {#create-or-extend-schemas}

要將欄位或其他元素添加到市場活動中的核心資料方案之一，如收件人表(nms:recipient)，必須擴展該方案。

![](../assets/do-not-localize/glass.png) 有關此內容的詳細資訊，請參閱 [擴展架構](extend-schema.md)。

要添加Adobe Campaign中不存在的全新類型的資料（例如，合同表），可以直接建立自定義架構。

![](../assets/do-not-localize/glass.png) 有關此內容的詳細資訊，請參閱 [建立新架構](create-schema.md)。

![](assets/schemaextension_1.png)


在建立或擴展了要使用的架構後，最佳做法是按如下所示的順序定義其XML內容元素。

## 分項清單 {#enumerations}

先在架構的主元素之前定義枚舉。 它們允許您在清單中顯示值，以限制用戶對給定欄位的選擇。

範例:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

在定義欄位時，您可以像這樣使用此枚舉：

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您還可以使用用戶管理的枚舉(通常在 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** )指定給定欄位的值。 這些實際上是全局枚舉，如果枚舉可能在您正在使用的特定架構之外使用，則是一個更好的選擇。

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

## 鍵 {#keys}

每個表必須至少有一個鍵，並且通常使用 **奧托普** 屬性集 **真**。

此外，在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，使用 **@autouuid** 並將其設定為 **真**。

還可以使用 **內部** 屬性。

範例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此示例中，不讓 **@autopk** 或 **@autouuid** 屬性建立名為「id」的預設主鍵，我們將指定自己的「householdId」主鍵。

>[!CAUTION]
>
>建立新架構或在架構擴展期間，需要為整個架構保留相同的主鍵序列值(@pkSequence)。

![](../assets/do-not-localize/glass.png) 瞭解有關中的鍵的詳細資訊 [此部分](database-mapping.md#management-of-keys)。

## 屬性（欄位） {#attributes--fields-}

屬性允許您定義構成資料對象的欄位。 您可以使用 **[!UICONTROL Insert]** 按鈕，將空屬性模板拖放到游標所在的XML中。 瞭解詳情 [此部分](create-schema.md)。

![](assets/schemaextension_2.png)

屬性的完整清單可在 `<attribute>` 元素節 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model)。 以下是一些更常用的屬性： **@advanced**。 **@dataPolicy**。 **@default**。 **@desc**。 **@enum**。 **@expr**。 **@label**。 **@length**。 **@name**。 **@notNull**。 **@required**。 **@ref**。 **@xml**。 **@type**。

![](../assets/do-not-localize/book.png) 有關每個屬性的詳細資訊，請參閱中的「屬性」說明 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)。

### 範例 {#examples}

定義預設值的示例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

將公共屬性用作模板的示例，該模板也標籤為必需：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用 **@advanced** 屬性：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

XML欄位的示例也儲存在SQL欄位中， **@dataPolicy** 屬性。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>雖然大多數屬性都根據1-1基數連結到資料庫的物理欄位，但XML欄位或計算欄位的情況並非如此。\
>XML欄位儲存在表的備注欄位(「mData」)中。\
>但是，每次啟動查詢時都動態地建立計算欄位，因此它只存在於應用層中。

## 連結 {#links}

連結是架構主元素中最後的一些元素。 它們定義實例中所有不同架構之間的關聯方式。

連結在包含 **外鍵** 連結的表。

基數有三種類型：1-1、1-N和N-N預設使用的是1-N類型。

### 範例 {#examples-1}

收件人表（現成模式）和自定義事務表之間1-N連結的示例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自定義架構「Car」（在「cus」命名空間中）與收件人表之間1-1連結的示例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

基於電子郵件地址而不是主鍵的收件人表和地址表之間的外部聯接示例：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

此處，&quot;xpath-dst&quot;對應於目標架構中的主鍵，而&quot;xpath-src&quot;對應於源架構中的外鍵。

## 稽核軌跡 {#audit-trail}

您可能希望在架構底部包括的一個有用元素是跟蹤元素（審計跟蹤）。

使用下面的示例可以包括與建立日期、建立資料的用戶、日期以及表中所有資料上次修改的作者相關的欄位：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新資料庫結構 {#updating-the-database-structure}

完成並保存更改後，需要將可能影響SQL結構的任何更改應用到資料庫。 為此，請使用資料庫更新助手。

![](assets/schemaextension_3.png)

如需詳細資訊，請參閱[本章節](update-database-structure.md)。

>[!NOTE]
>
>當修改不影響資料庫結構時，只需重新生成模式。 為此，請選擇要更新的架構，按一下右鍵並選擇 **[!UICONTROL Actions > Regenerate selected schemas...]** 。
