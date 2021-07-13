---
product: Adobe Campaign
title: 開始使用 Campaign API
description: 開始使用 Campaign API
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 12%

---

# 開始使用[!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] 隨附一組您可使用的JavaScript函式：

* 在指令碼中 — 在[!DNL Adobe Campaign]工作流程中
* 透過API — 從外部系統

您可以使用JavaScript API在Campaign雲端資料庫中寫入或從資料庫讀取：

* 可讓您對每個物件採取動作的業務專屬API:傳遞、工作流程、訂閱等。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)深入瞭解。
* 查詢資料模型資料的一般資料存取API。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)深入瞭解。

Campaign v8可與兩個資料庫搭配使用：用於使用者介面即時訊息傳送和統一查詢及透過API寫入的本機資料庫，以及用於行銷活動執行、報告、資料擷取、批次查詢及工作流程執行的雲端資料庫。

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8會限制API層的吞吐量(TPS)。突破限制會導致標準HTTP錯誤(429)。 身為「受管Cloud Services」使用者，您可以聯絡Adobe以調整每個API的限制。


## 先決條件

使用[!DNL Adobe Campaign] API之前，您必須熟悉下列主題：

* JavaScript
* SOAP協定
* [!DNL Adobe Campaign] 資料模型

若要使用API並與[!DNL Adobe Campaign]互動，您也必須熟悉您的資料模型。

>[!NOTE]
>您可以產生資料模型的完整說明。 在[本頁](datamodel.md)中瞭解更多。

## [!DNL Campaign] API 準備機制

使用[!DNL Campaign]雲資料庫時，由於效能（延遲和並行），不建議使用blast統一呼叫。 總是首選批操作。 為保證API的最佳效能，Campaign會持續在本機資料庫層級處理API呼叫。

??[本頁](staging.md)中詳細說明了API預備機制

## 新 API

新的API可用於管理[!DNL Campaign]本地資料庫和雲資料庫之間的資料同步。 此外，也推出新機制，在本機資料庫層級處理API呼叫，以避免延遲並提升整體效能。

??[本頁](new-apis.md)詳細說明新API

**相關主題**

* [資料模型最佳實務](datamodel-best-practices.md)
