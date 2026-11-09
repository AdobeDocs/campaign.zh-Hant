---
product: campaign
title: 設定線上調查
description: 瞭解如何設定線上調查
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: 2ac66c0844ec361de9a1658f666c190fcfac8ffa
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%
---
# 設定線上調查{#configuring-surveys}

>[!AVAILABILITY]
>
>調查不適用於[Campaign FFDA部署](../../architecture/enterprise-deployment.md)。



## 調查屬性 {#survey-properties}

線上調查是完全可設定和自訂的，可滿足您的需求。 必須在屬性視窗中輸入引數。

可用的引數在[此檔案](../web/defining-web-forms-properties.md)中有詳細說明。

![](assets/s_ncs_admin_survey_properties_general.png)

## 調查資料儲存 {#survey-data-storage}

依預設，Web表單欄位會儲存在收件者表格中。 若要使用其他表格，請在&#x200B;**[!UICONTROL Document type]**&#x200B;欄位中選取它。 **[!UICONTROL Zoom]**&#x200B;圖示可讓您檢視所選表格的內容。

使用者所提供的調查問卷的回答未儲存在欄位中（但儲存在區域變數中），這些回答儲存在&#x200B;**調查問卷的回答**&#x200B;表格中。 您可以根據&#x200B;**[!UICONTROL Library]**&#x200B;欄位變更使用的結構描述。 此欄位僅適用於&#x200B;**調查**。
