---
title: 使用queryDef查詢資料庫
description: 瞭解如何使用queryDef和NLWS方法來查詢Campaign資料庫
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 1%

---

# 使用queryDef查詢資料庫 {#query-database-api}

[!DNL Adobe Campaign]提供強大的JavaScript方法，以使用`queryDef`和`NLWS`物件與資料庫互動。 這些以SOAP為基礎的方法可讓您使用JSON、XML或SQL載入、建立、更新和查詢資料。

>[!NOTE]
>
>本檔案說明以程式設計方式查詢資料庫的資料導向API。 若為REST API，請參閱[開始使用REST API](api/get-started-apis.md)。 若要建立視覺查詢，請參考[使用查詢編輯器](../start/query-editor.md)。

## 什麼是NLWS？ {#what-is-nlws}

`NLWS` (Neolane Web Services)是全域JavaScript物件，用來存取[!DNL Adobe Campaign]的SOAP型API方法。 結構描述是`NLWS`物件的屬性，可讓您以程式設計方式與Campaign實體互動。

根據[Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}，「結構描述是&#39;NLWS&#39;全域物件。」 存取結構描述方法的語法遵循以下模式：

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**範例：**

* `NLWS.nmsRecipient` — 收件者結構描述(`nms:recipient`)的存取方法
* `NLWS.nmsDelivery` — 傳遞結構描述(`nms:delivery`)的存取方法
* `NLWS.xtkQueryDef` — 存取查詢資料庫的queryDef方法

常見的API方法包括：

* `load(id)` — 依實體識別碼載入實體。 [了解更多](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html){target="_blank"}
* `create(data)` — 建立新實體
* `save()` — 儲存對實體的變更

**官方檔案中的範例：**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**替代語法：**&#x200B;若為回溯相容性，您也可能會在某些檔案中看到小寫的名稱空間語法（例如，`nms.recipient.create()`、`xtk.queryDef.create()`）。 兩種語法都有效，但`NLWS`是官方Campaign JSAPI參考中記錄的標準。

## 先決條件 {#prerequisites}

在使用queryDef和NLWS方法之前，您應該先熟悉：

* JavaScript
* [!DNL Adobe Campaign]資料模型和結構描述
* 用於導覽結構描述元素的XPath運算式

**瞭解Campaign資料模型：**

Adobe Campaign隨附預先定義的資料模型，其中包含連結在雲端資料庫中的表格。 基本結構包括：

* **收件者資料表** (`nmsRecipient`) — 儲存行銷設定檔的主資料表
* **傳遞資料表** (`nmsDelivery`) — 以執行傳遞的引數儲存傳遞動作和範本
* **記錄資料表** — 儲存執行記錄檔：
   * `nmsBroadLogRcp` — 傳送給收件者的所有訊息的傳遞記錄
   * `nmsTrackingLogRcp` — 追蹤收件者回應的記錄（開啟、點按）
* **技術資料表** — 儲存系統資料，例如運運算元(`xtkGroup`)、工作階段(`xtkSessionInfo`)、工作流程(`xtkWorkflow`)

若要存取Campaign介面中的結構描述說明，請瀏覽至&#x200B;**管理>設定>資料結構描述**，選取資源，然後按一下&#x200B;**檔案**&#x200B;索引標籤。

## 實體結構描述方法 {#entity-schema-methods}

[!DNL Adobe Campaign] （例如`nms:recipient`、`nms:delivery`）中的每個結構描述都包含可透過`NLWS`物件存取的方法。 這些方法提供了與資料庫實體互動的便利方式。

### 靜態方法 {#static-methods}

靜態SOAP方法可透過在代表結構描述的物件上叫用方法來存取。 例如，`NLWS.xtkWorkflow.PostEvent()`會叫用靜態方法。

### 非靜態方法 {#non-static-methods}

若要使用非靜態SOAP方法，您必須先使用對應結構描述上的`load`或`create`方法擷取實體。 在[Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}中瞭解更多。

### 載入、儲存及建立實體 {#load-save-create}

**依ID載入實體並更新它：**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**使用JSON建立收件者：**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**使用XML建立收件者：**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## QueryDef概述 {#querydef-overview}

`xtk:queryDef`結構描述提供建立和執行資料庫查詢的方法。 您可以使用`NLWS.xtkQueryDef.create()`來建立具有JSON或XML語法的查詢。

**可用的作業：**

* `select` — 擷取多個記錄
* `get` — 擷取單一記錄(SQL `LIMIT 1`)
* `getIfExists` — 擷取單一記錄，如果找不到，則傳回null
* `count` — 計算符合條件的記錄

在[Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}中進一步瞭解queryDef方法。

## 使用JSON查詢 {#query-json}

使用`NLWS.xtkQueryDef.create()`以JSON語法建置查詢。 `get`作業會擷取單一記錄(SQL `LIMIT 1`)，而`select`會擷取多個記錄。

**取得單一收件者：**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**使用`getIfExists`以避免例外狀況：**

如果記錄可能不存在，請使用`operation: "getIfExists"`而非`get`以避免例外狀況：

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## 選取多個記錄 {#select-multiple}

使用`select`作業擷取多個記錄。 您可以新增條件、順序和限制。

**具有篩選和排序的查詢工作流程：**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**使用XML語法的查詢傳遞：**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**結果限制：**&#x200B;行銷活動會自動限制查詢結果以防止記憶體問題：
>* 預設限制因內容而異（通常為200至10,000筆記錄）
>* 使用`lineCount`明確設定結果數目上限
>* 對於大型資料集（超過1000筆記錄），請使用工作流程而不是queryDef。 工作流程的設計宗旨是有效率地處理數百萬列。

深入瞭解[ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"}和[查詢最佳實務](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}。

## 查詢工作流程轉變資料 {#workflow-transition-data}

在工作流程中使用JavaScript活動時，您可以使用`vars.targetSchema`和`vars.tableName`來查詢傳入轉變的資料。

**從工作流程轉換查詢收件者資料：**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>請一律使用引數化的查詢，字串為`$(sz)`，整數為`$(l)`，以防止SQL插入漏洞。 在[Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}中瞭解更多。

## 計算記錄 {#count-records}

使用具有別名的`Count(@id)`來計算記錄。

**計算執行中的假設：**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**包含多個條件的計數：**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 值的分佈 {#distribution-values}

取得特定欄位的值分佈，用於分析資料模式。

**國家/地區代碼的分佈：**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## 使用分析查詢分項清單 {#analyze-enumerations}

`analyze`選項會傳回列舉值的好記名稱。 Campaign也將使用「Name」和「Label」尾碼來傳回字串值和標籤，而不只是數值。

**具有列舉分析的查詢傳遞對應：**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

深入瞭解[分析選項](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}。

## 分頁 {#pagination}

使用`lineCount`和`startLine`在大型結果集中分頁。

**擷取頁面中的記錄：**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**分頁需要orderBy：**&#x200B;若沒有`orderBy`子句，無法保證查詢結果的順序一致。 後續呼叫可能會傳回不同頁面或重複記錄。 使用分頁時一律包括`orderBy`。

深入瞭解[分頁](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}。

## 動態查詢建構 {#dynamic-queries}

以程式設計方式附加條件，以動態方式建立查詢。

**將條件附加至現有查詢：**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**在回圈中建置select和where子句：**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 進階queryDef方法 {#advanced-methods}

在`ExecuteQuery()`之外，queryDef為進階使用案例提供數種專門的方法。

### BuildQuery — 產生SQL而不執行 {#build-query}

使用`BuildQuery()`產生SQL陳述式而不執行它。 這對於偵錯、記錄或將查詢傳遞至外部系統非常有用。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

深入瞭解[BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}。

### BuildQueryEx — 取得具有格式字串的SQL {#build-query-ex}

`BuildQueryEx()`會傳回SQL查詢和與`sqlSelect()`函式相容的格式字串。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

深入瞭解[BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}。

### SelectAll — 新增要選取的所有欄位 {#select-all}

`SelectAll()`方法會自動將結構描述中的所有欄位新增到select子句中，讓您不會手動列出每個欄位。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

深入瞭解[全選](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}。

### 更新 — 整批更新記錄 {#mass-update}

`Update()`方法可讓您對符合查詢條件的記錄執行大量更新，而不需個別載入每個記錄。

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>整批更新會影響所有符合where子句的記錄。 一律先使用選取查詢測試您的where條件，以確認哪些記錄將受到影響。

深入瞭解[更新](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}。

### GetInstanceFromModel — 查詢範本執行個體 {#get-instance-from-model}

使用`GetInstanceFromModel()`從範本建立的執行個體擷取資料。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

深入瞭解[GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}。

## 批次作業 {#batch-operations}

批次處理多個記錄以提高效能。

**批次更新傳遞標籤：**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## 原始SQL執行 {#raw-sql}

對於複雜的作業，您可以直接執行原始SQL。

**執行引數化SQL：**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

使用sqlSelect的&#x200B;**查詢：**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>使用原始SQL時：
>
>* 一律驗證並處理使用者輸入
>* 使用`$(sz)`、`$(l)`、`$(dt)`等引數化的查詢。
>* 請注意[FFDA部署](../architecture/enterprise-deployment.md)中本機和雲端資料庫之間的差異

## 最佳實務 {#best-practices}

使用queryDef和NLWS方法時：

* **針對大型資料集使用工作流程** - QueryDef並非針對大量資料處理而設計。 針對擁有超過1,000筆記錄的資料集，請使用可有效處理數百萬列的工作流程。 在[Campaign SDK檔案](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}中進一步瞭解
* **使用引數化查詢** — 一律使用具有`$(sz)`的繫結引數(`$(l)`， `sqlExec`)以防止SQL插入
* **設定明確限制** — 使用`lineCount`控制結果大小。 行銷活動的預設限制依內容而異（200到10,000筆記錄）
* **搭配分頁使用orderBy** — 使用`orderBy`和`startLine`時一律包含`lineCount`子句，以確保分頁一致
* **使用getIfExists** — 在記錄可能不存在時使用`operation: "getIfExists"`以避免例外狀況
* **使用分析列舉** — 新增`analyze: true`以選取節點，以取得好記的列舉名稱和標籤
* **最佳化查詢** — 新增適當的`where`條件以限制結果集
* **批次處理** — 以批次處理多個記錄以避免記憶體問題和逾時
* **FFDA感知度** — 在[企業(FFDA)部署](../architecture/enterprise-deployment.md)中，請注意[!DNL Campaign]可搭配兩個資料庫使用



## 實際使用案例 {#use-cases}

### 偵錯並記錄查詢 {#debug-queries}

使用`BuildQuery()`在執行前檢查產生的SQL：

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### 使用SelectAll複製記錄 {#duplicate-record}

複製記錄時使用`SelectAll()`複製所有欄位：

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### 大量更新前驗證 {#validate-mass-update}

在執行整批更新之前，一律預覽受影響的記錄：

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## 查詢定義語法參考 {#querydef-reference}

`queryDef`物件的完整結構：

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## 相關主題 {#related-topics}

* [開始使用Campaign API](api.md)
* [Campaign JavaScript SDK — 查詢API](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [queryDef API參考](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
* [使用結構描述](schemas.md)
* [使用查詢編輯器](../start/query-editor.md)

