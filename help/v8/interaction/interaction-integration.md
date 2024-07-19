---
product: campaign
title: 在網頁中新增優惠方案
description: 瞭解如何在網頁中新增優惠方案
feature: Interaction, Offers
role: User, Admin
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 0%

---

# 在網頁中新增優惠方案{#add-an-offer-in-web}

若要在網頁中呼叫優惠方案引擎，請直接在頁面中插入對JavaScript程式碼的呼叫。 此呼叫會傳回目標元素中的選件內容。

指令碼呼叫URL看起來像這樣：

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

「**env**」引數會收到匿名互動專屬之即時環境的內部名稱。

若要呈現優惠方案，我們需要在Adobe Campaign中建立環境和優惠方案空間，然後設定HTML頁面。

下列使用案例詳細說明透過JavaScript整合優惠方案的可能選項。

## 選項1：HTML模式 {#html-mode}

### 提供匿名優惠 {#presenting-an-anonymous-offer}

**步驟1：準備優惠方案引擎**

1. 開啟Adobe Campaign介面並準備匿名環境。
1. 建立連結至匿名環境的優惠方案空間。
1. 建立連結至優惠方案空間的優惠方案及其表現。

**步驟2：更新HTML頁面的內容**

HTML頁面必須包含具有@id屬性的元素，且元素屬性具有已建立選件空間（「i_internal名稱空間」）的內部名稱值。 選件會由Interaction插入此元素。

在我們的範例中，@id屬性會收到「i_SPC12」值，其中「SPC12」是先前建立之優惠空間的內部名稱：

```
<div id="i_SPC12"></div>
```

在我們的範例中，呼叫指令碼的URL如下（「OE3」是即時環境的內部名稱）：

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>`<script>`標籤不能為自我結束。

此靜態呼叫會自動產生動態呼叫，其中包含優惠方案引擎所需的所有引數。

此行為可讓您在同一個頁面上使用數個優惠方案空間，以便透過對優惠方案引擎的單一呼叫來管理。

**步驟3：在HTML頁面**&#x200B;中顯示結果

優惠方案引擎會將優惠方案表示的內容傳回HTML頁面：

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### 呈現已識別的優惠 {#presenting-an-identified-offer}

若要將優惠方案呈現給已識別的連絡人，程式與本區段](#presenting-an-anonymous-offer)中詳細的[類似。

在網頁內容中，您需要新增下列指令碼，以在呼叫優惠方案引擎期間識別聯絡人：

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. 移至網頁將呼叫的優惠方案空間，按一下&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;並新增一或多個識別鍵。

   ![](assets/interaction_htmlmode_001.png)

   在此範例中，識別索引鍵是複合的，因為它同時以電子郵件和收件者名稱為基礎。

1. 在網頁顯示期間，指令碼評估可讓您將收件者ID傳遞至優惠方案引擎。 如果ID是複合的，則鍵會以與進階設定相同的順序顯示，並以分隔 |.

   在以下範例中，聯絡人已登入網站，並在致電優惠方案引擎時被識別，這要歸功於他們的電子郵件和名稱。

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### 使用HTML演算函式 {#using-an-html-rendering-function}

若要自動產生HTML選件表示，您可以使用演算功能。

1. 前往優惠方案空間並按一下&#x200B;**[!UICONTROL Edit functions]**&#x200B;連結。
1. 選取 **[!UICONTROL Overload the HTML rendering function]**。
1. 移至&#x200B;**[!UICONTROL HTML rendering]**&#x200B;標籤，並在優惠方案空間插入符合為優惠方案內容定義欄位的變數。

   ![](assets/interaction_htmlmode_002.png)

   在此範例中，優惠方案會以橫幅的形式顯示在網頁中，且由可點按的影像以及符合優惠方案內容中定義欄位的標題所組成。

## 選項2：XML模式 {#xml-mode}

### 呈現優惠方案 {#presenting-an-offer}

行銷活動&#x200B;**互動**&#x200B;模組可讓您將XML節點傳回呼叫優惠方案引擎的HTML頁面。 此XML節點可由要在客戶端開發的函式來處理。

對優惠方案引擎的呼叫看起來像這樣：

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* 「**env**」引數會接收即時環境的內部名稱。

* &#39;&#39;**cb**&#39;&#39;引數會接收將讀取包含（回撥）主張的引擎傳回之XML節點的函式名稱。 此引數為選用。

* 「**t**」引數只接收已識別互動的目標值。 此引數也可以與&#x200B;**interactionTarget**&#x200B;變數一起傳遞。 此引數為選用。

* 「**c**」引數會收到類別的內部名稱清單。 此引數為選用。

* 「**th**」引數會接收主題清單。 此引數為選用。

* 「**gctx**」引數會接收整個頁面的呼叫資料全域（內容）。 此引數為選用。

傳回的XML節點如下所示：

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

以下使用案例詳細說明要在Adobe Campaign中執行的設定以啟用XML模式，然後在HTML頁面中顯示呼叫引擎的結果。

1. **建立環境和優惠方案空間**

   有關建立環境的詳細資訊，請參閱[此頁面](interaction-env.md)。

   如需建立優惠方案空間的詳細資訊，請參閱[此頁面](interaction-offer-spaces.md)。

1. **擴充優惠方案結構描述以新增欄位**

   此結構描述將定義下列欄位：標題編號2和價格。

   範例中的結構描述名稱為&#x200B;**cus：offer**

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >每個元素需要定義兩次。 CDATA (&quot;_jst&quot;)型別元素可包含個人化欄位。
   >
   >別忘了更新資料庫結構。

   您可以擴充優惠方案結構，以批次和單一模式及任何格式(文字、HTML和XML)新增欄位。

1. **擴充優惠方案公式以編輯新欄位並修改現有欄位**

   編輯&#x200B;**選件(nsm)**&#x200B;輸入表單。

   在「檢視」區段中，插入兩個含有以下內容的新欄位：

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   註解目的地URL欄位：

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >(`<input>`)表單的欄位必須指向已建立結構描述中定義的CDATA型別元素。

   優惠方案宣告表單中的轉譯如下所示：

   ![](assets/interaction_xmlmode_form.png)

   已新增&#x200B;**[!UICONTROL Title 2]**&#x200B;及&#x200B;**[!UICONTROL Price]**&#x200B;欄位，且不再顯示&#x200B;**[!UICONTROL Destination URL]**&#x200B;欄位。

1. **建立優惠方案**

   如需建立優惠方案的詳細資訊，請參閱[此頁面](interaction-offer.md)。

   在下列使用案例中，輸入選件的方式如下：

   ![](assets/interaction_xmlmode_offer.png)

1. **核准優惠方案**

   核准優惠或由其他人核准，然後在最後一個步驟建立的優惠方案空間上啟用它，以便在連結的即時環境中可用。

1. 在HTML頁面&#x200B;**上執行**&#x200B;引擎呼叫和結果

   在HTML頁面中呼叫優惠方案引擎看起來像這樣：

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   「**env**」引數的值是即時環境的內部名稱。

   「**cb**」引數的值是需要解譯引擎傳回之XML節點的函式名稱。 在我們的範例中，呼叫的函式會開啟一個模型視窗(alert()函式)。

   選件引擎傳回的XML節點如下所示：

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### 使用演算函式 {#using-a-rendering-function-}

您可以使用XML演算函式來建立優惠方案簡報。 此函式將修改在呼叫優惠方案引擎期間傳回至HTML頁面的XML節點。

1. 前往優惠方案空間並按一下&#x200B;**[!UICONTROL Edit functions]**&#x200B;連結。
1. 選取 **[!UICONTROL Overload the XML rendering function]**。
1. 移至&#x200B;**[!UICONTROL XML rendering]**&#x200B;索引標籤並插入所需的函式。

   函式看起來可能像這樣：

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## 設定SOAP整合

為Offer Management提供的SOAP Web服務與Adobe Campaign中通常使用的服務不同。 可透過上一節所述的互動URL存取優惠方案，並讓您提供或更新指定聯絡人的優惠方案。

### 優惠方案主張 {#offer-proposition}

對於透過SOAP的優惠方案主張，請新增&#x200B;**nms：proposition#Propose**&#x200B;命令，後面接著下列引數：

* **targetId**：收件者的主索引鍵（可以是複合索引鍵）。
* **maxCount**：指定連絡人的優惠方案主張數目。
* **內容**：可讓您在空間結構描述中新增內容資訊。 如果使用的結構描述是&#x200B;**nms：interaction**，則應新增&#x200B;**`<empty>`**。
* **類別**：指定優惠必須屬於的類別。
* **主題**：指定選件必須屬於的主題。
* **uuid**： Adobe Campaign永久cookie的值(「uuid230」)。
* **nli**： Adobe Campaign工作階段Cookie的值(「nlid」)。
* **noProp**：使用「true」值停用提案插入。

>[!NOTE]
>
>**targetId**&#x200B;和&#x200B;**maxCount**&#x200B;設定是強制性的。 其他則是選擇性的。

為回應查詢，SOAP服務將傳回下列引數：

* **interactionId**：互動識別碼。
* **主張**： XML元素，包含主張清單，每個都具有自己的ID和HTML表示。

### 優惠更新 {#offer-update}

將&#x200B;**nms：interaction#UpdateStatus**&#x200B;命令新增至URL，後面接著這些引數：

* **主張**：字元字串，它包含在優惠方案主張期間作為輸出提供的主張ID。 請參閱[優惠方案主張](#offer-proposition)。
* **狀態**：字串型別，它指定選件的新狀態。 可能的值列在&#x200B;**nms：common**&#x200B;結構描述的&#x200B;**propositionStatus**&#x200B;列舉中。 例如，數字3是現成可用的，對應至&#x200B;**已接受**&#x200B;狀態。
* **context**： XML元素，可讓您在空間結構描述中新增內容資訊。 如果使用的結構描述是&#x200B;**nms：interaction**，則應新增&#x200B;**`<empty>`**。

### 使用SOAP呼叫的範例 {#example-using-a-soap-call}

以下是SOAP呼叫的程式碼範例：

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
