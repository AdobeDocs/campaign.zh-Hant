---
title: Campaign資料庫對應
description: Campaign資料庫對應
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# 資料庫對應{#database-mapping}

範例結構描述的SQL對應提供下列XML檔案：

```sql
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

結構描述的根專案不再是&#x200B;**`<srcschema>`**，而是&#x200B;**`<schema>`**。

這會將我們帶到另一種型別的檔案，該檔案是從來源結構描述自動產生的，簡稱為結構描述。 Adobe Campaign應用程式將使用此結構描述。

SQL名稱是根據元素名稱和型別自動決定的。

SQL命名規則如下：

* 表格：串連綱要名稱空間和名稱

  在我們的範例中，資料表的名稱是透過&#x200B;**sqltable**&#x200B;屬性中結構描述的主要元素輸入的：

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* 欄位：前面有根據型別定義之前置詞的元素名稱（&#39;i&#39;代表整數，&#39;d&#39;代表雙精度浮點數，&#39;s&#39;代表字串，&#39;ts&#39;代表日期等）

  欄位名稱是透過每個型別&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`**&#x200B;的&#x200B;**sqlname**&#x200B;屬性輸入的：

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>可以從來源結構描述多載SQL名稱。 若要這麼做，請在相關元素上填入「sqltable」或「sqlname」屬性。

用來建立從擴充綱要產生之表格的SQL命令檔如下：

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL欄位限制如下：

* 數值和日期欄位中沒有null值
* 數值欄位已初始化為0

## XML欄位 {#xml-fields}

依預設，任何型別的&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`**&#x200B;專案都會對應到資料結構描述表格的SQL欄位。 不過，您可以用XML來參照此欄位，而非SQL，這表示資料會儲存在包含所有XML欄位值的表格之備忘錄欄位(「mData」)中。 這些資料的儲存是觀察結構描述結構的XML檔案。

若要在XML中填入欄位，您必須將值為「true」的&#x200B;**xml**&#x200B;屬性新增到相關專案。

**範例**

* 多行註解欄位：

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* HTML格式的資料說明：

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  「html」型別可讓您將HTML內容儲存在CDATA標籤中，並在Adobe Campaign使用者端介面中顯示特殊的HTML編輯檢查。

使用XML欄位可讓您新增欄位，而不需要修改資料庫的實體結構。 另一個優點是，您使用的資源較少（配置給SQL欄位的大小、限制每個表格的欄位數等）。
