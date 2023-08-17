---
title: Campaign資料庫對應
description: Campaign資料庫對應
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 0%

---

# 資料庫對應{#database-mapping}

範例結構描述的SQL對應提供下列XML檔案：

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

結構描述的根元素已不存在 **`<srcschema>`**，但 **`<schema>`**.

這會將我們帶到另一種型別的檔案，該檔案是從來源結構描述自動產生的，簡稱為結構描述。 Adobe Campaign應用程式將使用此結構描述。

SQL名稱是根據元素名稱和型別自動決定的。

SQL命名規則如下：

* 表格：串連綱要名稱空間和名稱

  在我們的範例中，表格的名稱是透過以下結構描述的主要元素輸入： **sqltable** 屬性：

  ```
  <element name="recipient" sqltable="CusRecipient">
  ```

* 欄位：前面有根據型別定義之前置詞的元素名稱（&#39;i&#39;代表整數，&#39;d&#39;代表雙精度浮點數，&#39;s&#39;代表字串，&#39;ts&#39;代表日期等）

  欄位名稱是透過 **sqlname** 每個型別的屬性 **`<attribute>`** 和 **`<element>`**：

  ```
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>可以從來源結構描述多載SQL名稱。 若要這麼做，請在相關元素上填入「sqltable」或「sqlname」屬性。

用來建立從擴充綱要產生之表格的SQL命令檔如下：

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL欄位限制如下：

* 數值和日期欄位中沒有null值，
* 數值欄位會初始化為0。

## XML欄位 {#xml-fields}

依預設，任何輸入的 **`<attribute>`** 和 **`<element>`** 元素對應至資料結構描述表格的SQL欄位。 不過，您可以用XML來參照此欄位，而非SQL，這表示資料會儲存在包含所有XML欄位值的表格之備忘錄欄位(「mData」)中。 這些資料的儲存是觀察結構描述結構的XML檔案。

若要以XML填入欄位，您必須新增 **xml** 對相關元素具有「true」值的屬性。

**範例**：以下是兩個XML欄位使用範例。

* 多行註解欄位：

  ```
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* HTML格式的資料說明：

  ```
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  「html」型別可讓您將HTML內容儲存在CDATA標籤中，並在Adobe Campaign使用者端介面中顯示特殊的HTML編輯檢查。

使用XML欄位可讓您新增欄位，而不需要修改資料庫的實體結構。 另一個優點是，您使用的資源較少（配置給SQL欄位的大小、限制每個表格的欄位數等）。

## 金鑰管理 {#management-of-keys}

表格必須至少有一個索引鍵用於識別表格中的記錄。

從資料結構描述的主要元素中宣告索引鍵。

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

金鑰遵循下列規則：

* 索引鍵可參考表格中的一或多個欄位。
* 當索引鍵是結構描述中第一個要填入的索引鍵，或如果索引鍵包含 **內部** 值為「true」的屬性。

**範例**:

* 將金鑰新增至電子郵件地址和城市：

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

  產生的結構描述：

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

* 在「id」名稱欄位中新增主要或內部索引鍵：

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

  產生的結構描述：

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

### 主索引鍵 — 識別碼{#primary-key}

在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，Adobe Campaign表格的主要索引鍵為 **通用唯一ID (UUID)** 由資料庫引擎自動產生。 在整個資料庫中，索引鍵值是唯一的。 索引鍵的內容會在插入記錄時自動產生。

**範例**

在來源結構描述中宣告增量金鑰：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

產生的結構描述：

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

除了索引鍵的定義外，名為「id」的數值欄位已新增至擴充架構，以包含自動產生的主要索引鍵。

>[!CAUTION]
>
>主鍵設為0的記錄會在建立表格時自動插入。 此記錄用於避免外部聯結，這些外部聯結在磁碟區表格上無效。 依預設，所有外部索引鍵都是以值0初始化，如此一來，當資料專案未填入時，就可以在聯結上傳回結果。

## 連結：表格之間的關係 {#links--relation-between-tables}

連結說明一個表格與另一個表格之間的關聯。

各種關聯（稱為「基數」）型別如下：

* 基數1-1：來源表格的一個執行個體最多可以具有目標表格的一個對應執行個體。
* 基數1-N：來源表格的一個出現次數可以具有多個目標表格的對應出現次數，但目標表格的一個出現次數最多可以具有來源表格的一個對應出現次數。
* 基數N-N：來源表格的一個出現次數可以具有多個目標表格的對應出現次數，反之亦然。

在介面中，您可以透過圖示輕鬆區分不同型別的關係。

對於與Campaign資料表/資料庫的聯結關係：

* ![](assets/do-not-localize/join_with_campaign11.png) ：基數1-1。 例如，在收件者和目前訂單之間。 收件者一次只能與目前訂單表格的一個執行個體相關。
* ![](assets/do-not-localize/externaljoin11.png) ：基數1-1、外部聯結。 例如，在收件者與其國家/地區之間。 收件者只能與表格國家/地區的一個執行個體相關。 將不會儲存國家表格的內容。
* ![](assets/do-not-localize/join_with_campaign1n.png) ：基數1-N。例如，在收件者和訂閱表格之間。 收件者可與訂閱表格上的數個專案建立關聯。

對於使用同盟資料庫存取的聯結關係：

* ![](assets/do-not-localize/join_fda_11.png) ：基數1-1
* ![](assets/do-not-localize/join_fda_1m.png) ：基數1-N

![](../assets/do-not-localize/glass.png) 如需FDA表格的詳細資訊，請參閱 [同盟資料存取](../connect/fda.md).

在包含透過主要元素連結之表格外部索引鍵的結構描述中，必須宣告連結：

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

連結遵循下列規則：

* 連結的定義輸入於 **連結**-type **`<element>`** 具有下列屬性：

   * **名稱**：來源表格中的連結名稱，
   * **目標**：目標結構描述的名稱，
   * **標籤**：連結的標籤，
   * **revLink** （選用）：來自目標架構的反向連結名稱（預設會自動衍生），
   * **完整性** （選擇性）：來源表格出現位置與目標表格出現位置的參照完整性。 可能的值如下：

      * **定義**：如果來源發生次數不再由目標發生次數參考，則可能會刪除該來源發生次數，
      * **一般**：刪除來源出現位置會初始化指向目標出現位置的連結索引鍵（預設模式），此型別的完整性會初始化所有外來索引鍵，
      * **擁有**：刪除來源出現位置會導致目標出現位置刪除，
      * **owncopy**：與 **擁有** （若為刪除）或重複發生次數（若為重複），
      * **中立**：不會執行任何動作。

   * **revIntegrity** （選擇性）：目標綱要上的完整性（選擇性，預設為「一般」），
   * **revCardinality** （選用）：值為「single」時，會將型別1-1 （預設為1-N）填入基數。
   * **externalJoin** （選用）：強制外部聯結
   * **revExternalJoin** （選用）：強制反向連結上的外部聯結

* 連結會參照來源表格到目的地表格的一或多個欄位。 構成聯結的欄位( `<join>`  元素)，因為預設會使用目標結構描述的內部索引鍵自動推斷。
* 連結由兩個半連結組成，其中第一個是從來源綱要宣告，第二個是在目標綱要的延伸綱要中自動建立。
* 連線可以是外部連線，如果 **externalJoin** 加入屬性，值為「true」（PostgreSQL支援）。

>[!NOTE]
>
>連結是在結構描述結尾宣告的元素。

### 範例1 {#example-1}

與「cus：company」結構描述表格相關的1-N：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

產生的結構描述：

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

組成聯結的欄位可補充連結定義，也就是在目的地結構描述中主索引鍵及其XPath (「@id」)，在結構描述中主索引鍵及其XPath (「@company-id」)。

外部索引鍵會自動新增至與目的地表格中相關欄位使用相同特性的元素中，並遵循下列命名慣例：目標結構描述名稱后面接著相關欄位名稱（範例中為「company-id」）。

目標(「cus：company」)的延伸結構描述：

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany"  autopk="true" autouuid="true"> 
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

已新增指向「cus：recipient」表格的反向連結，其中包含下列引數：

* **名稱**：自動從來源結構描述的名稱衍生（可在來源結構描述的連結定義中使用「revLink」屬性強制執行）
* **revLink**：反向連結的名稱
* **目標**：連結綱要的索引鍵（「cus：recipient」綱要）
* **未繫結**：連結會宣告為1-N基數的收集要素（依預設）
* **完整性**：預設為「定義」（可在來源架構上的連結定義中使用「revIntegrity」屬性強制執行）。

請注意 `autouuid="true"`引數適用於的上下文 [企業(FFDA)部署](../architecture/enterprise-deployment.md) 僅限。

### 範例2 {#example-2}

在此範例中，我們將宣告指向「nms：address」架構表格的連結。 此聯結是外部聯結，並明確填入收件者的電子郵件地址和連結表格(「nms：address」)的「@address」欄位。

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

與「cus：extension」綱要表格的1-1關係：

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### 範例4 {#example-4}

連結至資料夾（「xtk：folder」架構）：

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

預設值會傳回在「DefaultFolder(&#39;nmsFolder&#39;)」函式中輸入的第一個合格引數型別檔案的識別碼。

### 範例5 {#example-5}

在此範例中，我們希望透過在連結（「company」到「cus：company」架構）上建立索引鍵 **xlink** （「電子郵件」）表格的屬性和欄位：

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

產生的結構描述：

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

「companyEmail」名稱金鑰的定義已擴充為「company」連結的外部金鑰。
