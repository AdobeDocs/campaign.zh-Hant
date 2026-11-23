---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# 轉寄

無需透過使用者端即可將查詢重新導向至其他頁面。

```text
forward (location)
```

## 參數

**位置**&#x200B;重新導向URL。

## 傳回值

無。

## 備註

轉寄可讓您在將查詢轉移至另一個會產生回應內容的資源之前，先執行初步流程。 在轉接呼叫之前，沒有資料必須作為回應傳回至使用者端，否則將會引發錯誤。

## 功能

**類別的方法：** [HttpServletRequest](c-httpservletrequest.md)

**可用於：**

* JSSP
* WebApp
