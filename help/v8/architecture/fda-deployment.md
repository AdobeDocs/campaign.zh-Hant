---
title: 開始部署營銷活動FDASnowflake
description: 開始部署營銷活動FDASnowflake
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 部署{#gs-fda-snowflake}

在 [!DNL Snowflake] FDA（預設）部署， [!DNL Adobe Campaign] v8連接到 [!DNL Snowflake] 訪問資料 [聯合資料存取](../connect/fda.md) 功能：您可以訪問和處理儲存在您的 [!DNL Snowflake] 資料庫，不改變Adobe Campaign資料的結構。

## 好處{#fda-benefits}

此部署模型具有以下優點：

* **儲存和效能**
您可以將歷史資料移動到 [!DNL Snowflake] 然後減少對Adobe CampaignID限制的依賴。 此體系結構還降低了對PostgreSQL儲存和效能限制的依賴性。 由於市場活動資料庫中儲存的資料較少，因此效能更好，維護任務的執行速度更快。

* **資料模型擴展和資料管理**
可以在 [!DNL Snowflake] 並將它們連結到Adobe Campaign，例如，在保留期內使用歸檔資料，或運行效能優異的分段流程。

   此體系結構還允許您在 [!DNL Snowflake]。 只有匯總和臨時表才會移至市場活動，以便個性化和交付。


## 架構{#fda-archi}

使用此部署模型，Adobe Campaign用戶可以將其資料擴展到 [!DNL Snowflake] 並利用單個整合資料平台的優勢，即時獲得強大的營銷活動資料洞察力。 它為用戶提供一個單一、統一且易於使用的資料分析平台，從而讓用戶能夠從其資料中釋放深度價值。 雲資料平台不需要管理，因為它可以無限擴展以支援來自Adobe Campaign的任意數量的營銷資料。

伺服器和進程之間的一般通信按照以下模式進行：

![](assets/fda-architecture.png)

PostgreSQL是主資料庫，Snowflake是輔助資料庫。 您可以擴展資料模型並將資料儲存在Snowflake上。 隨後，可以對效能優異的大型資料集運行ETL、分段和報告。
