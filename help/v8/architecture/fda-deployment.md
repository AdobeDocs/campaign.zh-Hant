---
title: 開始使用Campaign FDA部署
description: 開始使用Campaign FDA部署
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: ee3dfd63-9a21-4961-9f24-ea3385284a21
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 0%

---

# [!DNL Campaign] FDA部署{#gs-fda}

在其Campaign FDA （預設）部署中，[!DNL Adobe Campaign] v8可以連線至[!DNL Snowflake]，以透過[同盟資料存取](../connect/fda.md)功能存取資料：您接著可以存取及處理儲存在[!DNL Snowflake]資料庫中的外部資料和資訊，而不需要變更Adobe Campaign資料的結構。

>[!NOTE]
>
>在此部署模型中，[!DNL Snowflake]次要資料庫僅在請求時可用。 若要使用[!DNL Snowflake]更新您的部署，請聯絡您的Adobe轉換經理。
>

## 好處{#fda-benefits}

此部署模型具備下列優點：

* **儲存和效能**
您可以將歷史資料移至[!DNL Snowflake]，然後將相依性減少至Adobe Campaign ID的上限。 此架構也會減少您對PostgreSQL儲存體的相依性，並限制效能。 Campaign資料庫中儲存的資料較少，因此效能會提高，而執行維護工作的速度也會加快。

* **資料模型延伸與資料管理**
您可以在[!DNL Snowflake]中建立表格，並將它們連結至Adobe Campaign，例如在保留期間使用封存的資料，或執行具有傑出效能的分段程式。

  此架構也可讓您在[!DNL Snowflake]中使用資料管理工作流程功能。 只有彙總和臨時表格會移至Campaign，以用於個人化和傳遞目的。


## 架構{#fda-archi}

透過此部署模型，Adobe Campaign使用者可將其資料延伸至[!DNL Snowflake]，並利用單一整合資料平台的優勢，即時獲得強大的行銷活動資料見解。 它提供單一、統一且簡單易用的資料分析平台，讓使用者能充分運用其資料，發揮深層價值。 雲端資料平台不需要管理，因為它可無限擴充，以支援Adobe Campaign的任何行銷資料量。

伺服器與處理序之間的一般通訊會根據以下結構描述執行：

![](assets/fda-architecture.png)

PostgreSQL是主要資料庫，Snowflake可作為次要資料庫使用。 您可以擴充資料模型，並將資料儲存在Snowflake上。 接著，您可以利用出色的效能，對大型資料集執行ETL、細分和報告。
