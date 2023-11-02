---
title: 開始使用 Campaign API
description: 開始使用 Campaign API
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 8%

---

# 開始使用 [!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign] 隨附一組Javascript函式，您可使用：

* 在指令碼中 — 在 [!DNL Adobe Campaign] 工作流程
* 透過API — 來自外部系統

您可以使用JavaScript API在Campaign雲端資料庫中寫入或讀取資料庫：

* 業務特定的API可讓您對每個物件執行動作：傳送、工作流程、訂閱等。 進一步瞭解 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* 用於查詢資料模型資料的一般資料存取API。 進一步瞭解 [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

請注意，在其 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，Campaign可與兩個資料庫搭配使用：本機資料庫，用於使用者介面即時傳送訊息並透過API統一查詢及寫入，以及雲端資料庫，用於行銷活動執行、報告、資料擷取、批次查詢及工作流程執行。

>[!CAUTION]
>
>* 從Campaign v8.5.1開始，Campaign v8的驗證程式已變更。 技術操作員必須使用AdobeIdentity Management系統(IMS)來連線至Campaign。 瞭解如何移轉您現有的技術帳戶，於 [此技術檔案](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8包含我們API層的輸送量(TPS)限制。 超過上限會導致標準HTTP錯誤(429)。 作為「受管理的Cloud Service」使用者，您可以聯絡Adobe以調整每個API的節流。
> 

## 必要條件 {#ac-api-prerequisites}

使用前 [!DNL Adobe Campaign] API時，您必須熟悉下列主題：

* JavaScript
* SOAP通訊協定
* [!DNL Adobe Campaign] 資料模型

為了使用API並與 [!DNL Adobe Campaign]時，您也必須熟悉您的資料模型。

>[!NOTE]
>您可以產生資料模型的完整說明。 在[本頁](datamodel.md)中瞭解更多。


**相關主題**

* [資料模型最佳實務](datamodel-best-practices.md)
