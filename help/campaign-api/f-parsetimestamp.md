---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 9%
---
# parseTimeStamp

將包含根據ISO 8601標準的簡化版本所制定之日期的字元字串轉換為日期型別物件。

```text
parseTimeStamp (aString)
```

## 參數

**aString**&#x200B;日期為ISO 8601格式的字元字串。

## 傳回值

符合日期集引數的Date型別物件。

## 備註

語法如下：

```javascript
              date
              time[time-zone]
            
```

或

```javascript
              dateTtime[time-zone]
            
```

日期必須具有以下格式：

```javascript
YYYY-MM-DD
```

基於相容性的理由，也接受以下格式：

```javascript
YYYY/MM/DD
```

時間必須具有以下格式：

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

時區（如果已指定）必須具有以下格式：

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

若未指定時區，日期將會轉換為目前時區（視內容而定）。 範例：

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

如果日期格式無效，則會引發例外狀況。

## 功能

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
