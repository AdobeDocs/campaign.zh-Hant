---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

在服務上宣告函式。

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## 參數

**名稱**&#x200B;方法的名稱。 這是JavaScript中公開的名稱，以及SOAP方法的名稱。

**動作** SOAP — 動作引數。

**引數**&#x200B;引數的宣告，以包含依配對分組的字串清單的資料表形式。 第一個字串是引數的名稱，第二個字串對應至型別： \[&quot;name1&quot;、&quot;type1&quot;、&quot;name2&quot;、&quot;type2&quot;、...\]

**回應**&#x200B;傳回值的宣告形式為包含以配對分組的字串清單的資料表：第一個字串是引數的名稱，第二個字串對應到型別： \[&quot;name1&quot;， &quot;type1&quot;， &quot;name2&quot;， &quot;type2&quot;， ...\]

**requestNodeName**&#x200B;字元字串，指定SOAP查詢的XML節點名稱，而非方法名稱。

**responseNodeName**&#x200B;字元字串，指定SOAP回應的XML節點名稱，而不是方法名稱后面接著回應。

## 傳回值

無。

## 備註

支援的型別如下：

* 字串
* 布林值
* 長整數
* 短整數
* 位元組
* 浮點數
* 雙精度浮點數
* 日期
* 時間
* 日期時間
* NLDocument
* NLElement
* NLRawxml
* NLCollection

在服務上宣告方法時，這會變成服務的方法，而且可以直接透過其名稱呼叫方法來叫用。 用於傳入引數的NLRawXML型別會複製整個XML節點以取代引數。 當做傳回型別使用，會包含SOAP回應的完整第一個子元素。 其使用表示SOAP回應只有一個子元素。 用於傳入引數的NLCollection型別會複製所有子元素以取代引數。 傳入引數是變數引數時，此功能會很有用。 當作傳回型別使用，包含整個SOAP回應，因為這是傳回值的根。 發生錯誤時，會引發例外狀況。 如果這是格式正確的SOAP錯誤，則引發的例外狀況會具有soapFault屬性，並包含SOAP錯誤的XML節點。 範例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
```

## 功能

**類別的方法：** [SoapService](c-soapservice.md)

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
