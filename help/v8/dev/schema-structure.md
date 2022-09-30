---
title: 促銷活動結構
description: 行銷活動綱要結構
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 1%

---

# 方案結構{#schema-structure}

的基本結構 `<srcschema>` 如下所示：

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

資料架構的XML文檔必須包含 **`<srcschema>`** 根元素與 **名稱** 和 **命名空間** 屬性來填入結構名稱及其命名空間。

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

讓我們使用以下XML內容來說明資料架構的結構：

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

與其對應的資料結構：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## 說明 {#description}

架構的進入點是其主要元素。 很容易識別，因為其名稱與結構相同，且應為根元素的子項。 內容的說明以此元素開頭。

在我們的範例中，主要元素以下列行表示：

```
<element name="recipient">
```

元素 **`<attribute>`** 和 **`<element>`** 後面的主要元素允許您定義XML結構中資料項的位置和名稱。

在我們的範例結構中，以下是：

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

必須遵守下列規則：

* 每個 **`<element>`** 和 **`<attribute>`** 必須透過 **名稱** 屬性。

   >[!CAUTION]
   >
   >元素的名稱應簡明扼要，最好是英文，並且僅包括符合XML命名規則的授權字元。

* 僅 **`<element>`** 可包含的元素 **`<attribute>`** 元素和 **`<element>`** 元素。
* 安 **`<attribute>`** 元素在 **`<element>`**.
* 使用 **`<elements>`** 建議使用多行資料字串。

## 資料類型 {#data-types}

資料類型是透過 **type** 屬性 **`<attribute>`** 和 **`<element>`** 元素。

如需詳細清單，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

未填入此屬性時， **字串** 為預設資料類型，除非元素包含子元素。 若有，則僅用於以階層式結構化元素(**`<location>`** 元素)。

結構支援下列資料類型：

* **字串**:字串。 範例：名字、城鎮等。

   可以透過 **length** 屬性（選用，預設值「255」）。

* **布林值**:布林欄位。 可能的值範例：true/false、0/1、yes/no等。
* **位元組**, **short**, **long**:整數（1個位元組、2個位元組、4個位元組）。 範例：年齡、帳號、點數等。
* **兩次**:雙精度浮點數。 範例：價格、費率等。
* **日期**, **日期時間**:日期和日期+時間。 範例：出生日期、購買日期等。
* **datetimenotz**:日期+時間（不含時區資料）。
* **時間盤**:持續時間。 範例：資歷。
* **備忘錄**:長文本欄位（多行）。 範例：說明、注釋等。
* **uid**:&quot;uniqueidentifier&quot;欄位

   >[!NOTE]
   >
   >若要包含 **uid** 欄位中，必須新增&quot;newuuid()&quot;函式並以其預設值完成。

以下是輸入類型的範例結構：

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## 屬性 {#properties}

此 **`<elements>`** 和 **`<attributes>`** 資料結構的元素可以透過各種屬性來擴充。 您可以填入標籤以說明目前的元素。

### 標籤和說明 {#labels-and-descriptions}

* 此 **標籤** 屬性可讓您輸入簡短說明。

   >[!NOTE]
   >
   >標籤與實例的當前語言相關聯。

   **範例**:

   ```
   <attribute name="email" type="string" length="80" label="Email"/>
   ```

   您可從Adobe Campaign用戶端主控台輸入表單中查看標籤：

   ![](assets/schema_label.png)

* 此 **desc** 屬性可讓您輸入詳細說明。

   您可從Adobe Campaign用戶端主控台主視窗狀態列的輸入表單中查看說明。

   >[!NOTE]
   >
   >說明與例項的目前語言相關聯。

   **範例**:

   ```
   <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
   ```

### 預設值 {#default-values}

此 **預設** 屬性可讓您定義在內容建立時傳回預設值的運算式。

該值必須是與XPath語言相容的表達式。 如需詳細資訊，請參閱[本章節](#reference-with-xpath)。

**範例**:

* 當前日期： **default=&quot;GetDate()&quot;**
* 計數器： **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

   在此範例中，預設值是使用字串的串連來建構，並呼叫 **CounterValue** 函式（具有自由計數器名稱）。 每次插入時，傳回的數字會增加一。

   >[!NOTE]
   >
   >在Adobe Campaign用戶端主控台中， **[!UICONTROL Administration>Counters]** 節點用於管理計數器。

若要將預設值連結至欄位，您可以使用 `<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>` :可讓您在建立實體時，以預設值預先填入欄位。 該值將不是預設SQL值。

`<sqldefault>` :可讓您在建立欄位時有新增值。 此值將作為SQL結果顯示。 在結構更新期間，只有新記錄會受此值影響。

### 分項清單 {#enumerations}

#### 自由枚舉 {#free-enumeration}

此 **userEnum** 屬性可讓您定義免費分項清單，以記住和顯示透過此欄位輸入的值。 語法如下：

**userEnum=&quot;枚舉的名稱&quot;**

可以自由選擇給枚舉的名稱並與其他欄位共用。

這些值會顯示在輸入表單的下拉式清單中：

![](assets/schema_user_enum.png)

>[!NOTE]
>
>在Adobe Campaign用戶端主控台中， **[!UICONTROL Administration > Enumerations]** 節點用於管理枚舉。

#### 設定枚舉 {#set-enumeration}

此 **列舉** 屬性可讓您定義預先知道可能值清單時所使用的固定分項清單。

此 **列舉** 屬性是指在主要元素外的架構中填入的分項清單類別的定義。

列舉可讓使用者從下拉式清單中選取值，而非在一般輸入欄位中輸入值：

![](assets/schema_enum.png)

資料結構中的列舉聲明範例：

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

分項清單會透過 **`<enumeration>`** 元素。

枚舉屬性如下：

* **baseType**:與值關聯的資料類型，
* **標籤**:枚舉的描述，
* **名稱**:枚舉的名稱，
* **預設**:枚舉的預設值。

分項清單會在 **`<value>`** 元素（具有下列屬性）:

* **名稱**:內部儲存的值名稱，
* **標籤**:標籤。

#### dbenum枚舉 {#dbenum-enumeration}

* 此 **貝努姆** 屬性可讓您定義其屬性與 **列舉** 屬性。

   不過， **名稱** 屬性不會在內部儲存值，而會儲存程式碼，讓您在不修改其架構的情況下擴充相關表格。

   這些值是透過 **[!UICONTROL Administration>Enumerations]** 節點。

   例如，此分項清單用於指定促銷活動的性質。

   ![](assets/schema_dbenum.png)

### 範例 {#example}

以下是已填入屬性的範例結構：

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## 集合 {#collections}

集合是具有相同名稱和相同階層層級的元素清單。

此 **未綁定** 屬性的值為「true」，可讓您填入集合元素。

**範例**:定義 **`<group>`** 結構中的集合元素。

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

對XML內容進行投影：

```
<group label="Group1"/>
<group label="Group2"/>
```

## 使用XPath引用 {#reference-with-xpath}

Adobe Campaign中使用XPath語言來參考屬於資料架構的元素或屬性。

XPath是一種語法，用於在XML文檔的樹中查找節點。

元素由其名稱指定，屬性由名稱指定，名稱前面加上字元「@」。

**範例**:

* **@email**:選擇電子郵件，
* **位置/@city**:選取 **`<location>`** 元素
* **../@email**:從當前元素的父元素中選擇電子郵件地址
* **群組`[1]/@label`**:選擇「label」屬性，該屬性是第一個的子項 **`<group>`** 集合元素
* **群組`[@label='test1']`**:選擇「label」屬性，該屬性是 **`<group>`** 元素和包含「test1」值

>[!NOTE]
>
>當路徑跨過子元素時，會添加附加約束。 在此情況下，下列運算式必須放置在方括弧之間：
>
>* **位置/@city** 無效；請使用 **`[location/@city]`**
>* **`[@email]`** 和 **@email** 等於
>


您也可以定義複雜的運算式，例如下列運算：

* **@gender+1**:在 **性別** 屬性，
* **@email + &#39;(&#39;+@created+&#39;)&#39;**:通過取用添加到建立日期（括弧之間）的電子郵件地址的值（對於字串類型，以引號括住常數）來構建字串。

已在運算式中新增高階函式，以豐富此語言的潛力。

您可以透過Adobe Campaign用戶端主控台中的任何運算式編輯器來存取可用函式清單：

![](assets/schema_function.png)

**範例**:

* **GetDate()**:傳回目前日期
* **年(@created)**:傳回「已建立」屬性中包含的日期年份。
* **GetEmailDomain(@email)**:返回電子郵件地址的域。

## 透過計算字串建立字串 {#building-a-string-via-the-compute-string}

A **計算字串** 是XPath表達式，用於構造表示與架構關聯的表中的記錄的字串。 **計算字串** 主要用於圖形介面，以顯示所選記錄的標籤。

此 **計算字串** 是透過 **`<compute-string>`** 元素。 安 **expr** 屬性包含XPath表達式，用於計算顯示。

**範例**:收件者表格的計算字串。

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

收件者的計算字串結果： **Doe John(john.doe@aol.com)**

>[!NOTE]
>
>如果架構不包含計算字串，預設情況下會填入計算字串，其中包含該架構的主鍵值。
