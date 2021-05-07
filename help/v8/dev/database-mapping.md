---
solution: Campaign
product: Adobe Campaign
title: 促銷活動資料庫對應
description: 促銷活動資料庫對應
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 0%

---

# 資料庫對應{#database-mapping}

我們示例模式的SQL映射提供了以下XML文檔：

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## 說明 {#description}

架構的根元素不再是&#x200B;**`<srcschema>`**，而是&#x200B;**`<schema>`**。

這會帶我們到另一種類型的文檔，它自動從源模式生成，簡稱為模式。 此模式將由Adobe Campaign應用程式使用。

SQL名稱會根據元素名稱和類型自動確定。

SQL命名規則如下：

* 表格：架構名稱空間和名稱的級聯

   在我們的示例中，表的名稱是通過&#x200B;**sqltable**&#x200B;屬性中模式的主元素輸入的：

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* 欄位：元素的名稱，前面加上根據類型定義的首碼（&#39;i&#39;代表整數，&#39;d&#39;代表雙重，&#39;s&#39;代表字串，&#39;ts&#39;代表日期等）

   通過&#x200B;**sqlname**&#x200B;屬性輸入欄位名稱，用於鍵入每個&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`** :

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>SQL名稱可以從源方案過載。 要執行此操作，請在相關元素上填充「sqltable」或「sqlname」屬性。

建立從擴展模式生成的表的SQL指令碼如下：

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL欄位約束如下：

* 數值和日期欄位中沒有空值，
* 數字欄位會初始化為0。

## XML欄位{#xml-fields}

預設情況下，所有鍵入的&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`**&#x200B;元素都映射到資料模式表的SQL欄位。 但是，您可以在XML中引用此欄位，而不是SQL，這表示資料儲存在包含所有XML欄位值的表的備注欄位(「mData」)中。 這些資料的儲存是一份XML檔案，可觀察架構結構。

若要在XML中填入欄位，您必須將&#x200B;**xml**&#x200B;屬性與值&quot;true&quot;新增至相關元素。

**範例**:以下是兩個XML欄位使用範例。

* 多行注釋欄位：

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* HTML格式的資料說明：

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   「html」類型可讓您將HTML內容儲存在CDATA標籤中，並在Adobe Campaign客戶端介面中顯示特殊的HTML編輯檢查。

使用XML欄位可以添加欄位，而無需修改資料庫的物理結構。 另一個優勢是，您使用的資源較少（分配給SQL欄位的大小、每個表的欄位數限制等）。

## 金鑰管理{#management-of-keys}

表必須至少有一個用於標識表中記錄的鍵。

從資料模式的主元素中聲明密鑰。

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

鍵符合下列規則：

* 鍵可以引用表中的一個或多個欄位。
* 如果鍵是要填充的模式中的第一個，或者它包含&#x200B;**internal**&#x200B;屬性，且值為&quot;true&quot;，則該鍵稱為「primary」（或「priority」）。

**範例**:

* 將密鑰添加到電子郵件地址和城市：

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="email">
         <keyfield xpath="@email"/> 
         <keyfield xpath="location/@city"/> 
       </key>
   
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
       <element name="location" label="Location">
         <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
       </element>
     </element>
   </srcSchema>
   ```

   生成的架構：

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
       <keyfield xpath="@email"/>      
       <keyfield xpath="location/@city"/>    
      </key>    
   
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
      <element label="Location" name="location">      
        <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
      </element>  
     </element>
   </schema>
   ```

* 在&quot;id&quot;名稱欄位中新增主要或內部金鑰：

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="id" internal="true">
         <keyfield xpath="@id"/> 
       </key>
   
       <key name="email">
         <keyfield xpath="@email"/> 
       </key>
   
       <attribute name="id" type="long" label="Identifier"/>
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
     </element>
   </srcSchema>
   ```

   生成的架構：

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
       <key name="email">      
         <keyfield xpath="@email"/>    
       </key>  
   
       <key internal="true" name="id">      
        <keyfield xpath="@id"/>    
       </key>    
   
       <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
       <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
     </element>
   </schema>
   ```

### 主鍵——標識符

Adobe Campaign表的主鍵是由資料庫引擎自動生成的&#x200B;**通用唯一ID(UUID)**。 索引鍵值在整個資料庫中是唯一的。 密鑰的內容在插入記錄時自動產生。

**範例**

在源模式中聲明增量密鑰：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient" autouuid="true">
  ...
  </element>
</srcSchema>
```

生成的架構：

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

除了索引鍵的定義外，還在擴充架構中新增了名為&quot;id&quot;的數值欄位，以包含自動產生的主索引鍵。

>[!CAUTION]
>
>建立表時，將自動插入主鍵設定為0的記錄。 此記錄用於避免對卷表無效的外部連接。 預設情況下，所有外鍵都以值0初始化，以便在未填充資料項時，始終可以在連接時返回結果。

## 連結：表{#links--relation-between-tables}之間的關係

連結描述了一個表和另一個表之間的關聯。

各種關聯類型（稱為「基數」）如下：

* 基數1-1:源表的一個實例最多可以具有目標表的一個相應實例。
* 基數1-N:源表的一個出現次數可以具有多個目標表的相應出現次數，但目標表的一個出現次數最多可以具有源表的一個對應出現次數。
* 基數N-N:源表的一個實例可以具有多個目標表的相應實例，反之亦然。

在介面中，您可透過其圖示，輕鬆區分不同類型的關係。

對於與促銷活動表／資料庫的連接關係：

* ![](assets/do-not-localize/join_with_campaign11.png) :基數1-1。例如，在收件者與目前訂單之間。 接收者一次只能與當前訂單表的一個事件相關。
* ![](assets/do-not-localize/externaljoin11.png) :基數1-1，外部連接。例如，在收件者與其國家之間。 收件者只能與表國家／地區的一個事件相關聯。 不會儲存國家／地區表格的內容。
* ![](assets/do-not-localize/join_with_campaign1n.png) :基數1-N。例如，在收件者和訂閱表格之間。收件者可以與預訂表上的幾個實例相關。

對於使用同盟資料庫訪問的連接關係：

* ![](assets/do-not-localize/join_fda_11.png) :基數1-1
* ![](assets/do-not-localize/join_fda_1m.png) :基數1-N

：球：有關FDA表的詳細資訊，請參閱[Federated Data Access](../connect/fda.md)。

必須在包含通過主元素連結的表的外鍵的架構中聲明連結：

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

連結遵循下列規則：

* 在&#x200B;**link**-type **`<element>`**&#x200B;上輸入連結的定義，其屬性如下：

   * **名稱**:源表中連結的名稱，
   * **目標**:目標方案的名稱、
   * **標籤**:連結標籤，
   * **revLink** （可選）:目標架構的反向連結名稱（預設會自動推斷）,
   * **完整性** （可選）:源表的出現與目標表的出現的參照完整性。可能的值如下：

      * **define**:如果源實例不再被目標實例引用，則可刪除該源實例，
      * **正常**:刪除源實例將初始化指向目標實例（預設模式）的連結的鍵，此類型的完整性將初始化所有外鍵，
      * **擁有**:刪除源事件會導致刪除目標事件，
      * **下載**:與 **own** （刪除時）相同，或複製發生次數（複製時）,
      * **中性**:什麼都不做。
   * **revIntegrity** （可選）:目標架構上的完整性（預設情況下為「正常」，為可選）,
   * **revCardinality** （可選）:值&quot;single&quot;會填入1-1（預設為1-N）的基數。
   * **externalJoin** （可選）:強制外連接
   * **revExternalJoin** （可選）:將外連接強制在反向連接上


* 連結將源表中的一個或多個欄位引用到目標表。 組成連接（`<join>`元素）的欄位無需填充，因為預設情況下，這些欄位會使用目標模式的內部鍵自動推導。
* 連結由兩個半連結組成，其中第一個連結從源模式聲明，第二個連結在目標模式的擴展模式中自動建立。
* 如果添加了&#x200B;**externalJoin**&#x200B;屬性，且值為&quot;true&quot;（在PostgreSQL中受支援），則連接可以是外部連接。

>[!NOTE]
>
>連結是在架構結尾宣告的元素。

### 範例1 {#example-1}

1-N與&quot;cus:company&quot;模式表的關係：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

生成的架構：

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

連結定義由組成連接的欄位補充，即目標模式中具有其XPath(&quot;@id&quot;)的主鍵，以及模式中具有其XPath(&quot;@company-id&quot;)的外鍵。

外鍵會自動添加到使用與目標表中的關聯欄位相同特徵的元素中，並使用以下命名約定：目標架構的名稱，後面接著關聯欄位的名稱（我們範例中的「company-id」）。

目標的擴展模式(&quot;cus:company&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany" autouuid="true"> 
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

已新增「cus:recipient」表格的反向連結，並包含下列參數：

* **名稱**:自動從源模式的名稱推斷（可強制使用源模式上連結定義中的&quot;revLink&quot;屬性）
* **revLink**:反向連結的名稱
* **目標**:連結結構（「cus:recipient」結構）的索引鍵
* **未綁定**:連結會宣告為1-N基數的收集元素（依預設）
* **完整性**:預設情況下，&quot;define&quot;（可強制使用源架構上連結定義中的&quot;revIntegrity&quot;屬性）。

### 範例2 {#example-2}

在此示例中，我們將聲明指向&quot;nms:address&quot;模式表的鏈路。 該連接是外部連接，並顯式填入了收件人的電子郵件地址和連結表的「@address」欄位(「nms:address」)。

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

### 範例3 {#example-3}

與&quot;cus:extension&quot;模式表的1-1關係：

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### 範例5 {#example-4}

連結至資料夾（&quot;xtk:folder&quot;結構）:

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

預設值返回在&quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;函式中輸入的第一個合格參數類型檔案的標識符。

### 範例5 {#example-5}

在此範例中，我們希望在連結（「company」 to &quot;cus:company&quot;結構）上建立一個索引鍵，其中包含&#x200B;**xlink**&#x200B;屬性和(&quot;email&quot;)表格的欄位：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

生成的架構：

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

「companyEmail」名稱鍵的定義已與「company」連結的外鍵延伸。
