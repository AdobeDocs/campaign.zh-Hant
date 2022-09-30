---
title: 開始部署Campaign FDASnowflake
description: 開始部署Campaign FDASnowflake
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

在 [!DNL Snowflake] FDA（預設）部署， [!DNL Adobe Campaign] v8連接到 [!DNL Snowflake] 存取資料的方式 [同盟資料存取](../connect/fda.md) 功能：您可以存取及處理儲存在 [!DNL Snowflake] 資料庫，而不變更Adobe Campaign資料的結構。

## 好處{#fda-benefits}

此部署模型具有以下優點：

* **儲存和效能**
您可以將歷史資料移至 [!DNL Snowflake] 然後減少對Adobe Campaign ID的相依性限制。 此體系結構還降低了您對PostgreSQL儲存和效能限制的依賴性。 由於Campaign資料庫中儲存的資料較少，因此效能更好，維護任務的執行速度也更快。

* **資料模型擴充功能與資料管理**
您可以在 [!DNL Snowflake] 並將它們連結至Adobe Campaign，例如在保留期間使用封存的資料，或執行效能優異的區段程式。

   此架構也可讓您在 [!DNL Snowflake]. 只有匯總和臨時表格會移至Campaign，以利個人化和傳送。


## 架構{#fda-archi}

透過此部署模型，Adobe Campaign使用者可將其資料擴充至 [!DNL Snowflake] 並運用單一整合資料平台的優點，即時提供強大的行銷活動資料深入分析。 它提供單一、統一且簡單易用的資料分析平台，讓使用者能夠從資料中充分挖掘深層價值。 雲端資料平台可無限擴充，以支援來自Adobe Campaign的任何行銷資料量，因此不需要管理。

伺服器和進程之間的一般通信根據以下模式執行：

![](assets/fda-architecture.png)

PostgreSQL是主資料庫，Snowflake是次資料庫。 您可以擴充資料模型，並將資料儲存在Snowflake上。 隨後，您可以對效能卓越的大型資料集運行ETL、細分和報告。
