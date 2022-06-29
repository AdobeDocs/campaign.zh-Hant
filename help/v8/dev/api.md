---
title: 開始使用 Campaign API
description: 開始使用 Campaign API
feature: API
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 16%

---

# 入門 [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] 附帶一組Javascript函式，您可以使用：

* 在指令碼中 — 在 [!DNL Adobe Campaign] 工作流
* 通過API — 從外部系統

可以使用JavaScript API在Campaign雲資料庫中寫入或從資料庫中讀取：

* 業務特定的API，允許您對每個對象執行操作：交貨、工作流、訂閱等。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target=&quot;_blank&quot;} 深入瞭解。
* 用於查詢資料模型資料的通用資料存取API。 在 [Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target=&quot;_blank&quot;} 深入瞭解。

請注意，在 [企業(FDA)部署](../architecture/enterprise-deployment.md), Campign可以與兩個資料庫配合使用：本地資料庫用於用戶介面即時消息傳遞和單一查詢並通過API進行寫入，雲資料庫用於市場活動執行、報告、資料接收、批處理查詢和工作流執行。

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8對API層的吞吐量(TPS)有限制。 突破限制將導致標準HTTP錯誤(429)。 作為托管Cloud Services用戶，您可以與Adobe聯繫以調整每個API的限制。

## 必要條件

使用前 [!DNL Adobe Campaign] API需要熟悉以下主題：

* JavaScript
* SOAP協定
* [!DNL Adobe Campaign] 資料模型

為了使用API並與 [!DNL Adobe Campaign]，您還必須熟悉您的資料模型。

>[!NOTE]
>您可以生成資料模型的完整說明。 在[本頁](datamodel.md)中瞭解更多。


**相關主題**

* [資料模型最佳實務](datamodel-best-practices.md)
