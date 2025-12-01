---
title: 開始使用Campaign API
description: 開始使用Campaign API
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 75e0069ccd4e23dbf64b9052fd81817e438b333e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 11%

---

# 開始使用[!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign]隨附了一組Javascript函式，您可以：

* 在指令碼中 — 在[!DNL Adobe Campaign]工作流程中
* 透過API — 來自外部系統

>[!NOTE]
>
>根據您的部署模式，您也可以將REST API與Campaign v8搭配使用。 [了解更多](../dev/api/get-started-apis.md)。

您可以使用[Campaign JavaScript API](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=zh-Hant){target="_blank"}在Campaign雲端資料庫中寫入或從資料庫讀取：

* 業務特定的API可讓您對每個物件執行動作：傳送、工作流程、訂閱等。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=zh-Hant){target="_blank"}中進一步瞭解。
* 使用`queryDef`和`NLWS`物件查詢資料模型資料的一般資料存取API。 深入瞭解[使用queryDef](query-api.md)查詢資料庫。

請注意，在其[企業(FFDA)部署](../architecture/enterprise-deployment.md)中，Campaign可與兩個資料庫搭配使用：本機資料庫，用於使用者介面即時傳送訊息並透過API統一查詢及寫入，以及雲端資料庫，用於行銷活動執行、報告、資料擷取、批次查詢及工作流程執行。

>[!CAUTION]
>
>* 從Campaign v8.5.1開始，Campaign v8的驗證程式已變更。 技術操作員必須使用Adobe Identity Management System (IMS)來連線至Campaign。 透過[此技術說明](../../technotes/upgrades/ims-migration.md)了解如何移轉您現有的技術帳戶。
>
>* [!DNL Adobe Campaign] v8包含我們API層的輸送量(TPS)限制。 超過上限會導致標準HTTP錯誤(429)。 身為受管理的Cloud Services使用者，您可以聯絡Adobe以調整每個API的節流。
> 

## 先決條件 {#ac-api-prerequisites}

使用[!DNL Adobe Campaign] API前，您必須熟悉下列主題：

* JavaScript
* SOAP通訊協定
* [!DNL Adobe Campaign]資料模型

若要使用API並與[!DNL Adobe Campaign]互動，您也必須熟悉您的資料模型。

>[!NOTE]
>您可以產生資料模型的完整說明。 在[本頁](datamodel.md)中瞭解更多。


**相關主題**

<!-- * [Query the database with queryDef](query-api.md)-->
* [資料模型最佳實務](datamodel-best-practices.md)
* [Campaign JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=zh-Hant){target="_blank"}
