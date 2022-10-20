---
title: 開始使用Campaign架構
description: 探索環境和部署基本知識
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 110cf2ff705ecbc0b3a1690e9dfc2791f5744b97
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 12%

---

# 開始使用Campaign架構{#gs-ac-archi}

## 環境 {#environments}

促銷活動可作為個別例項使用，每個例項代表完整的促銷活動環境。

有兩種環境可供使用：

* **生產環境**:為業務從業者托管應用程式。

* **非生產環境**:在將應用程式的變更推送至生產環境之前，會先用於各種效能和品質測試。

您可以將套件從一個環境匯出並匯入至另一個環境。

![](../assets/do-not-localize/book.png) 深入了解套件，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target=&quot;_blank&quot;}

## 部署模型{#ac-deployment}

提供兩種部署模型：

* **促銷活動FDA [!DNL Snowflake] 部署**

   在 [[!DNL Snowflake] FDA部署](fda-deployment.md), [!DNL Adobe Campaign] v8連接到 [!DNL Snowflake] 若要透過同盟資料存取功能存取資料：您可以存取及處理儲存在 [!DNL Snowflake] 資料庫，而不變更Adobe Campaign資料的結構。 PostgreSQL是主資料庫，Snowflake是次資料庫。 您可以擴充資料模型，並將資料儲存在Snowflake上。 隨後，您可以對效能卓越的大型資料集運行ETL、細分和報告。

* **Campaign Enterprise(FFDA)部署**

   在 [企業(FFDA)部署](enterprise-deployment.md), [!DNL Adobe Campaign] v8可與兩個資料庫一起使用：本地 [!DNL Campaign] 資料庫，用於透過API和雲端的使用者介面即時訊息傳送和統一查詢與寫入 [!DNL Snowflake] 用於促銷活動執行、批次查詢和工作流程執行的資料庫。

   Campaign v8 企業版帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。使用此新架構，Campaign v8 企業 (FFDA) 部署可簡化資料管理：雲端資料庫不需要索引。 您只需要建立表格、複製資料，即可開始。雲端資料庫技術不需要進行具體的維護來保證效能等級。


## 訊息中心架構{#transac-msg-archi}

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

![](../assets/do-not-localize/glass.png) 了解如何在 [本節](../send/transactional.md).

為了回應客戶在網站上的動作，事件會透過REST API傳送Campaign，而訊息範本會填入透過API呼叫提供的資訊或資料，而交易式訊息會即時傳送給客戶。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知分批傳送。

在此特定架構中，執行單元與控制實例分離，以確保高可用性和負載管理。

* 此 **控制實例** （或行銷例項）供行銷人員和IT團隊用來建立、設定和發佈訊息範本。 此例項也會集中事件監控和歷史記錄。

   ![](../assets/do-not-localize/glass.png) 了解如何在 [本節](../send/transactional.md).

* 此 **執行實例** 擷取傳入事件（例如密碼重設或來自網站的訂單）並傳送個人化訊息。 可以有多個執行實例通過負載平衡器處理消息，並縮放要進行的事件數以實現最大可用性。

>[!CAUTION]
>
>控制實例和執行實例必須安裝在不同的電腦上。 他們無法共用相同的Campaign執行個體。

![](assets/messagecenter_diagram.png)

### 驗證

若要使用這些功能，Adobe Campaign使用者需登入控制執行個體以建立交易式訊息範本、使用種子清單產生訊息預覽、顯示報表及監控執行執行執行執行個體。

* 單執行實例與托管的Adobe消息中心執行實例交互時，外部系統可以使用提供的帳戶登錄和密碼，通過對會話登錄方法發出api調用，首先檢索會話令牌（預設在24小時內過期）。
然後，由執行例項提供以回應上述呼叫的sessionToken，外部應用程式可讓SOAP api叫用（rtEvents或batchEvents）來傳送通訊，而不需要在每個SOAP呼叫中納入帳戶登入和密碼。

* 多個執行實例在負載平衡器後面具有多個執行實例的多單元執行體系結構中，外部應用程式調用的登錄方法正在通過負載平衡器：因此，無法使用以權杖為基礎的驗證。 需要基於用戶/密碼的身份驗證。

![](../assets/do-not-localize/book.png) 進一步了解交易式訊息事件，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target=&quot;_blank&quot;}
