---
title: 開始使用Campaign FDASnowflake部署
description: 開始使用Campaign FDASnowflake部署
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 部署{#gs-fda-snowflake}

在 [!DNL Snowflake] FDA （預設）部署， [!DNL Adobe Campaign] v8已連線至 [!DNL Snowflake] 以透過存取資料 [同盟資料存取](../connect/fda.md) 功能：您可以存取及處理儲存在 [!DNL Snowflake] 資料庫而不變更Adobe Campaign資料的結構。

## 好處{#fda-benefits}

此部署模式具備下列優點：

* **儲存與效能**
您可以將歷史資料移至 [!DNL Snowflake] 然後將相依性降低為Adobe Campaign ID限制。 此架構也會減少您對PostgreSQL儲存和效能限制的相依性。 由於Campaign資料庫中儲存的資料較少，因此效能會提高，而維護工作的執行速度也會加快。

* **資料模型延伸與資料管理**
您可以在中建立表格 [!DNL Snowflake] 並將它們連結至Adobe Campaign，例如，使用保留期內的封存資料，或執行具有傑出效能的分段程式。

   此架構也可讓您使用資料管理工作流程功能： [!DNL Snowflake]. 只有彙總和臨時表格會移至Campaign，以用於個人化和傳遞目的。


## 架構{#fda-archi}

透過此部署模型，Adobe Campaign使用者可將其資料擴充至 [!DNL Snowflake] 並運用單一整合資料平台的優點，即時提供強大的行銷活動資料分析。 它提供單一、統一且易用的資料分析平台，讓使用者能從資料中釋放巨大價值。 雲端資料平台不需要管理，因為它可無限擴充，以支援Adobe Campaign的任何行銷資料量。

伺服器與處理序之間的一般通訊會根據下列結構描述執行：

![](assets/fda-architecture.png)

PostgreSQL是主要資料庫，而Snowflake是次要資料庫。 您可以擴充資料模型，並將資料儲存在Snowflake上。 接著，您可以對具有傑出效能的大型資料集執行ETL、細分和報告。
