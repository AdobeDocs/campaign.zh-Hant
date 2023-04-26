---
title: 開始使用Campaign架構
description: 探索環境和部署基本知識，包括如何報告行銷活動環境。
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 9%

---

# 開始使用Campaign架構{#gs-ac-archi}

## 環境 {#environments}

促銷活動可作為個別例項使用，每個例項代表完整的促銷活動環境。

有兩種環境可供使用：

* **生產環境**:為業務從業者托管應用程式。

* **非生產環境**:在將應用程式的變更推送至生產環境之前，會先用於各種效能和品質測試。

您可以將套件從一個環境匯出並匯入至另一個環境。

![](../assets/do-not-localize/book.png) 深入了解套件，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## 部署模型{#ac-deployment}

提供兩種部署模型：

* **促銷活動FDA [!DNL Snowflake] 部署**

   在 [[!DNL Snowflake] FDA部署](fda-deployment.md), [!DNL Adobe Campaign] v8連接到 [!DNL Snowflake] 若要透過同盟資料存取功能存取資料：您可以存取及處理儲存在 [!DNL Snowflake] 資料庫，而不變更Adobe Campaign資料的結構。 PostgreSQL是主資料庫，Snowflake是次資料庫。 您可以擴充資料模型，並將資料儲存在Snowflake上。 隨後，您可以對效能卓越的大型資料集運行ETL、細分和報告。

* **Campaign Enterprise(FFDA)部署**

   在 [企業(FFDA)部署](enterprise-deployment.md), [!DNL Adobe Campaign] v8可與兩個資料庫一起使用：本地 [!DNL Campaign] 資料庫，用於透過API和雲端的使用者介面即時訊息傳送和統一查詢與寫入 [!DNL Snowflake] 用於促銷活動執行、批次查詢和工作流程執行的資料庫。

   Campaign v8 企業版帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。使用此新架構，Campaign v8 企業 (FFDA) 部署可簡化資料管理：雲端資料庫不需要索引。 您只需要建立表格、複製資料，即可開始。雲端資料庫技術不需要進行具體的維護來保證效能等級。

## 分割傳送執行 {#split}

>[!AVAILABILITY]
>
>此功能僅適用於具有多個MID執行個體設定的客戶。

根據您的Campaign v8套件，您已布建特定數量的中間來源例項，負責執行傳送。

依預設，所有管道的外部帳戶都使用 **[!UICONTROL Alternate]** 路由模式，表示每次會以交替的方式從每個中間執行個體傳送一個傳送。

為確保在速度和規模上提供更佳效能，您可以允許傳送自動分割到中間來源執行個體，以便更快傳送給收件者。 從行銷執行個體執行傳送時，此操作是透明的：傳送後，所有記錄檔都會合併在一起，再傳回至行銷執行個體至單一傳送物件。

若要這麼做，請使用 **[!UICONTROL Split]** 在為每個通道預配時建立路由模式：

* 分割傳送 — 電子郵件(splitDeliveryEmail)
* 分割傳送 — SMS(splitDeliverySMS)
* 分割傳送 — iOS(splitDeliveryIOS)
* 分割傳送 — Android(splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>「分割傳送 — 電子郵件」帳戶預設會啟用分割路由模式。 對於所有其他管道外部帳戶，請連絡客戶服務以啟用選項。
>
>依預設，在多個mid之間分割傳送的臨界大小值為100K。 您可以在 **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** 功能表。

為了將分割的外部帳戶設為傳送傳遞的預設帳戶，您必須在傳遞範本中變更路由提供者。 要執行此操作，請依照下列步驟執行：

1. 導覽至 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** 資料夾，並開啟所需的傳送範本。 在此範例中，我們要編輯電子郵件傳送範本。

   ![](assets/split-default-list.png)

1. 按一下 **[!UICONTROL Properties]** 按鈕，並將路由提供程式更改為相應的拆分傳送外部帳戶。

   ![](assets/split-default-delivery.png)

1. 儲存您的變更。使用範本傳送的所有傳送現在預設會使用分割路由模式。

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

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

進一步了解交易式訊息事件，位於 [本頁](../send/event-processing.md).
