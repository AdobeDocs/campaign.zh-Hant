---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 7%
---
# setOption

變更選項表格中選項的值。

```text
setOption (name, value, description )
```

## 參數

**名稱**&#x200B;選項的名稱。

**值**&#x200B;選項的值。

**description**&#x200B;說明的值（選擇性）。

## 傳回值

無。

## 備註

不同的資料型別為：

* 文字，
* 整數，
* 浮點數，
* 日期+時間，
* longtext

請注意，無法從API建立longText和整數型別。

對於這兩種型別，您首先需要從主控台建立選項，然後透過setOption API管理值。

**範例：**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

如果您想要刪除說明，則必須使用空白說明(setOption(name，value，&quot;))呼叫API。

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
