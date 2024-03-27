---
title: Campaign資料庫中的金鑰管理
description: 瞭解Adobe Campaign結構描述中的金鑰管理
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 金鑰管理 {#management-of-keys}

每個與資料結構描述關聯的表格必須至少有一個索引鍵來識別表格中的記錄。

從資料結構描述的主要元素中宣告索引鍵。

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

當金鑰是結構描述中第一個要填入的金鑰，或金鑰包含 `internal` 屬性設為「true」。

索引鍵可參考表格中的一或多個欄位。

**範例**：

* 將金鑰新增至電子郵件地址和城市：

  ```sql
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

  ```sql
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

  ```sql
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

  ```sql
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

## 主索引鍵 — 識別碼{#primary-key}

在的內容中 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，Adobe Campaign表格的主要索引鍵為 **通用唯一ID (UUID)** 由資料庫引擎自動產生。 在整個資料庫中，索引鍵值是唯一的。 索引鍵的內容會在插入記錄時自動產生。

**範例**

在以下範例中，我們在來源結構描述中宣告增量金鑰：

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

產生的結構描述：

```sql
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
