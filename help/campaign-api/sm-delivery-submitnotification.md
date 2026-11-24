---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

從情境建立並提交通知。

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## 參數

**scenarioName**&#x200B;範本的內部名稱

**目標**&#x200B;傳遞目標母體取代情境中的母體

## 傳回值

**notificationId**&#x200B;通知識別碼

## 備註

警告：此API的建置目的並非管理大量資料或即時運作。 其開發每分鐘最多可處理數個呼叫。 SubmitNotification會在傳遞分析期間封鎖執行緒。 這可能需要幾秒鐘的時間。 「target」引數會指定傳遞目標。 它會覆寫範本中指定的目標。 若要傳遞到資料庫中的目標，目標元素將使用下列語法：

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

若要傳遞到檔案中的目標：

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

您可以明確定義目標（實際上是使用作為目標的檔案內容）：

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

也可以使用屬性「\_keepTemplateTarget」將目標定義在範本中

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## 功能

**結構描述：** [nms:delivery](s-nms-delivery.md)

**靜態：**

是
