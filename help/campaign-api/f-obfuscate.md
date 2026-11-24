---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# 模糊化

將整數模糊化為字元字串。 呼叫[取消模糊化](f-unobfuscate.md)即可復原原始值。

```text
obfuscate (value [, size ] [, version ])
```

## 參數

**value**&#x200B;要模糊化的整數。

**size**&#x200B;因模糊化而產生的字串大小。 介於6到10之間的整數。 根據預設，為6。

**版本**&#x200B;要套用的模糊化版本。 預設為0。

## 傳回值

代表模糊化整數的字元字串。

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
