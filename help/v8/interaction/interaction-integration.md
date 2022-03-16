---
product: campaign
title: 在網頁中添加優惠
description: 瞭解如何在網頁中添加優惠
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 213a10fea36b3b08c1dd8525084d212e191b2fc7
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 0%

---

# 在網頁中添加優惠{#add-an-offer-in-web}

要在網頁中調用Offer引擎，請將對JavaScript代碼的調用直接插入該頁。 此呼叫返回目標元素中的聘用內容。

調用URL的指令碼如下所示：

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

「」**環境**&quot;參數接收專用於匿名交互的活動環境的內部名稱。

要提供優惠，我們需要在Adobe Campaign建立一個環境和優惠空間，然後配置HTML頁。

以下使用案例詳細介紹了通過JavaScript整合服務的可能選項。

## 選項1:HTML模式 {#html-mode}

### 提交匿名報價 {#presenting-an-anonymous-offer}

**步驟1:準備優惠引擎**

1. 開啟Adobe Campaign介面並準備匿名環境。
1. 建立連結到匿名環境的聘用空間。
1. 建立連結至聘用空間的聘用及其表示法。

**步驟2:更新HTML頁的內容**

「HTML」頁必須包含具有@id屬性的元素，該元素的值為所建立的提供空間的內部名稱(「i_internal name space」)。 此優惠將通過Interaction插入到此元素中。

在本例中，@id屬性將接收「i_SPC12」值，其中「SPC12」是先前建立的提供空間的內部名稱：

```
<div id="i_SPC12"></div>
```

在本例中，調用指令碼的URL如下（「OE3」是即時環境的內部名稱）:

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>的 `<script>` 標籤不能是自閉。

此靜態調用將自動生成包含提供引擎所需的所有參數的動態調用。

此行為允許您在同一頁上使用多個提供空間，以便通過對提供引擎的一次調用進行管理。

**第3步：在HTML頁中顯示結果**

優惠表示法的內容由優惠引擎返回到HTML頁：

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

### 提交已確定的服務 {#presenting-an-identified-offer}

要向已識別的聯繫人提供要約，該過程與詳細的過程類似 [此部分](#presenting-an-anonymous-offer)。

在網頁內容中，您需要添加以下指令碼，這些指令碼將在呼叫服務引擎期間標識聯繫人：

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. 轉到網頁將調用的服務空間，按一下 **[!UICONTROL Advanced parameters]** 並添加一個或多個標識密鑰。

   ![](assets/interaction_htmlmode_001.png)

   在本示例中，標識鍵是複合的，因為它既基於電子郵件又基於收件人名稱。

1. 在網頁顯示過程中，指令碼評估允許您將收件人ID傳遞到提供引擎。 如果ID是複合的，則按與高級設定中使用的相同順序顯示鍵，並由 |。

   在以下示例中，該聯繫人已登錄到該網站，並在呼叫「優惠」引擎時被識別，這要歸功於他們的電子郵件和姓名。

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### 使用HTML呈現功能 {#using-an-html-rendering-function}

要自動生成HTML提供表示法，可以使用渲染函式。

1. 轉到服務空間，然後按一下 **[!UICONTROL Edit functions]** 的子菜單。
1. 選取 **[!UICONTROL Overload the HTML rendering function]**。
1. 轉到 **[!UICONTROL HTML rendering]** 頁籤，並插入與為聘用空間中的聘用內容定義的欄位匹配的變數。

   ![](assets/interaction_htmlmode_002.png)

   在此示例中，優惠以網頁中的標題的形式顯示，由可點擊影像和與優惠內容中定義的欄位相匹配的標題組成。

## 選項2:XML模式 {#xml-mode}

### 提供優惠 {#presenting-an-offer}

活動 **交互** 模組用於將XML節點返回到HTML頁，該頁調用「提供」引擎。 該XML節點可通過在客戶端開發的函式進行處理。

對服務引擎的調用如下所示：

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* 「」**環境**&quot;參數接收即時環境的內部名稱。

* 「」**可**&quot;參數接收將讀取包含（回調）命題的引擎返回的XML節點的函式的名稱。 此參數是可選的。

* 「」**t**&quot;參數接收目標的值，僅用於已標識的交互。 此參數也可與 **交互目標** 變數。 此參數是可選的。

* 「」**c**&quot;參數接收類別的內部名稱清單。 此參數是可選的。

* 「」**第**&quot;參數接收主題清單。 此參數是可選的。

* 「」**格**&quot;參數將全局（上下文）調用資料接收到整個頁面。 此參數是可選的。

返回的XML節點如下所示：

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

下面的使用案例詳細說明了在Adobe Campaign中執行的啟用XML模式的配置，然後在HTML頁中顯示對引擎的調用結果。

1. **建立環境和提供空間**

   有關建立環境的詳細資訊，請參閱 [此頁](interaction-env.md)。

   有關建立聘用空間的詳細資訊，請參閱 [此頁](interaction-offer-spaces.md)。

1. **擴展提供架構以添加新欄位**

   此架構將定義以下欄位：標題2和價格。

   示例中架構的名稱為 **定制：優惠**

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
   >每個元素需要定義兩次。 CDATA(&quot;_jst&quot;)類型元素可以包含個性化欄位。
   >
   >不要忘記更新資料庫結構。

   您可以擴展提供方案以在批處理和統一模式下以及以任何格式(文本、HTML和XML)添加新欄位。

1. **擴展聘用公式以編輯新欄位和修改現有欄位**

   編輯 **優惠(nsm)** 的下界。

   在「視圖」部分，插入包含以下內容的兩個新欄位：

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

   注釋掉目標URL欄位：

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >( `<input>`)表單必須指向在建立的架構中定義的CDATA類型元素。

   在「聘用表示」表單中的呈現如下所示：

   ![](assets/interaction_xmlmode_form.png)

   的 **[!UICONTROL Title 2]** 和 **[!UICONTROL Price]** 已添加欄位， **[!UICONTROL Destination URL]** 欄位不再顯示。

1. **建立優惠方案**

   有關建立優惠的詳細資訊，請參閱 [此頁](interaction-offer.md)。

   在以下使用情形中，要約的輸入方式如下：

   ![](assets/interaction_xmlmode_offer.png)

1. **批准聘用**

   批准聘用或讓他人批准聘用，然後在最後一步建立的聘用空間上將其激活，以便在連結的即時環境中可用。

1. **引擎調用和HTML頁上的結果**

   在HTML頁中調用「優惠」引擎如下所示：

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   「」的值&#x200B;**環境**&quot;參數是即時環境的內部名稱。

   「」的值&#x200B;**可**&quot;參數是需要解釋引擎返回的XML節點的函式的名稱。 在本例中，調用的up函式開啟一個模式窗口(alert()函式)。

   提供引擎返回的XML節點如下所示：

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

### 使用呈現函式 {#using-a-rendering-function-}

可以使用XML呈現功能來建立提供演示文稿。 此函式將修改在調用提供引擎期間返回到HTML頁的XML節點。

1. 轉到服務空間，然後按一下 **[!UICONTROL Edit functions]** 的子菜單。
1. 選取 **[!UICONTROL Overload the XML rendering function]**。
1. 轉到 **[!UICONTROL XML rendering]** 的子菜單。

   該函式可以如下所示：

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## 設定SOAP整合

為服務管理提供的SOAP Web服務與Adobe Campaign通常使用的服務不同。 您可以通過上一節中介紹的交互URL訪問它們，並讓您為給定聯繫人演示或更新優惠。

### 提供建議 {#offer-proposition}

要獲得通過SOAP提供的建議，請添加 **nms：命題#建議** 命令後跟以下參數：

* **目標ID**:收件人的主鍵（可以是複合鍵）。
* **最大計數**:指定聯繫人的要約建議數。
* **上下文**:允許您在空間架構中添加上下文資訊。 如果使用的架構是 **nms：交互**。 **`<empty>`** 應添加。
* **類別**:指定聘用必須屬於的類別/類別。
* **主題**:指定要約必須屬於的主題。
* **UU**:Adobe Campaign永久cookie的值(「uuid230」)。
* **無**:Adobe Campaign會話cookie(「nlid」)的值。
* **無道**:使用&quot;true&quot;值停用建議插入。

>[!NOTE]
>
>的 **目標ID** 和 **最大計數** 設定是強制的。 其他則是可選的。

響應查詢，SOAP服務將返回以下參數：

* **交互ID**:交互的ID。
* **命題**:XML元素，包含命題清單，每個命題都有自己的ID和HTML表示。

### 提供更新 {#offer-update}

添加 **nms:interaction#UpdateStatus** 命令，然後是這些參數：

* **命題**:一串字元，它包含在提供建議期間作為輸出給出的建議ID。 請參閱 [提供建議](#offer-proposition)。
* **狀態**:字串類型，它指定聘用的新狀態。 可能的值列在 **命題狀態** 枚舉，在 **nms：公用** 架構。 例如，現成，數字3與 **已接受** 狀態。
* **上下文**:XML元素，用於在空間架構中添加上下文資訊。 如果使用的架構是 **nms：交互**。 **`<empty>`** 應添加。

### 使用SOAP調用的示例 {#example-using-a-soap-call}

以下是SOAP調用的代碼示例：

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
