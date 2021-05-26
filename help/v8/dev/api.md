---
solution: Campaign v8
product: Adobe Campaign
title: 開始使用 Campaign API
description: 開始使用 Campaign API
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 4%

---

# 開始使用[!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] 隨附一組您可使用的JavaScript函式：

* 在指令碼中 — 在[!DNL Adobe Campaign]工作流程中
* 透過API — 從外部系統

您可以使用Javascript API在Campaign雲端資料庫中寫入或從資料庫讀取：

* 可讓您對每個物件採取動作的業務專屬API:傳遞、工作流程、訂閱等。 進一步了解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)。
* 一般資料會存取API以查詢資料模型資料。 進一步了解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)。

Campaign v8可與兩個資料庫搭配使用：用於使用者介面即時訊息傳送和統一查詢及透過API寫入的本機資料庫，以及用於行銷活動執行、報告、資料擷取、批次查詢及工作流程執行的雲端資料庫。

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8會限制API層的吞吐量(TPS)。突破限制會導致標準HTTP錯誤(429)。 身為「受管Cloud Services」使用者，您可以聯絡Adobe以調整每個API的限制。


## 必要條件

使用[!DNL Adobe Campaign] API之前，您必須熟悉下列主題：

* Javascript
* SOAP協定
* [!DNL Adobe Campaign] 資料模型

若要使用API並與[!DNL Adobe Campaign]互動，您也需要熟悉資料模型。

>[!NOTE]
>您可以產生資料模型的完整說明。 深入了解[本頁面](datamodel.md)。

## [!DNL Campaign] API中繼機制

使用[!DNL Campaign]雲資料庫時，由於效能（延遲和並行），不建議使用blast統一呼叫。 總是首選批操作。 為保證API的最佳效能，Campaign會持續在本機資料庫層級處理API呼叫。

[!DNL :bulb:] [本頁面詳細說明API中繼機制](staging.md)

## 新API

新的API可用於管理[!DNL Campaign]本地資料庫和雲資料庫之間的資料同步。 此外，也推出新機制，在本機資料庫層級處理API呼叫，以避免延遲並提升整體效能

[!DNL :bulb:] [本頁詳細說明新API](new-apis.md)

**相關主題**

* [資料模型最佳實務](datamodel-best-practices.md)
