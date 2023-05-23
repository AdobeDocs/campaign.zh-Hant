---
title: 開始使用活動體系結構
description: 探索環境和部署基本知識，包括如何報告行銷活動環境。
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 10%

---

# 活動體系結構入門{#gs-ac-archi}

## 環境 {#environments}

市場活動可以作為單個實例提供，每個實例代表完整的市場活動環境。

有兩種環境：

* **生產環境**:為業務從業者托管應用程式。

* **非生產環境**:在將應用程式更改推送到生產環境之前，用於各種效能和質量test。

您可以將軟體包從一個環境導出並導入到另一個環境。

![](../assets/do-not-localize/book.png) 瞭解有關中的包的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## 部署模型{#ac-deployment}

有兩種部署模式：

* **市場活動FDA [!DNL Snowflake] 部署**

   在 [[!DNL Snowflake] FDA部署](fda-deployment.md)。 [!DNL Adobe Campaign] v8連接到 [!DNL Snowflake] 要通過聯合資料存取功能訪問資料：您可以訪問和處理儲存在您的 [!DNL Snowflake] 資料庫，不改變Adobe Campaign資料的結構。 PostgreSQL是主資料庫，Snowflake是輔助資料庫。 您可以擴展資料模型並將資料儲存在Snowflake上。 隨後，可以對效能優異的大型資料集運行ETL、分段和報告。

* **市場活動企業(FFDA)部署**

   在 [企業(FDA)部署](enterprise-deployment.md)。 [!DNL Adobe Campaign] v8適用於兩個資料庫：當地 [!DNL Campaign] 用於用戶介面即時消息傳遞和統一查詢及通過API和雲寫入的資料庫 [!DNL Snowflake] 用於市場活動執行、批處理查詢和工作流執行的資料庫。

   Campaign v8 企業版帶來 **完全同盟資料存取** (FFDA) 的概念：所有資料現在都在雲端資料庫遠端處理。使用此新架構，Campaign v8 企業 (FFDA) 部署可簡化資料管理：雲端資料庫不需要索引。 您只需要建立表格、複製資料，即可開始。雲端資料庫技術不需要進行具體的維護來保證效能等級。

## 拆分交貨執行 {#split}

>[!AVAILABILITY]
>
>此功能僅適用於具有多個MID實例配置的客戶。

根據您的「市場活動v8」包，系統會為您設定特定數量的中間採購實例，負責執行交貨。

預設情況下，所有渠道的外部帳戶使用 **[!UICONTROL Alternate]** 路由模式，表示每次從每個中間實例以交替方式發送一個交貨。

為確保在速度和規模方面都有更好的效能，您可以允許在中間採購實例中自動拆分交貨，以便更快地將交貨交付給收件人。 從市場營銷實例執行交貨時，此操作是透明的：一旦發送了交貨，所有日誌就會合併在一起，然後再發回到市場營銷實例，以便將其發送到單個交付對象。

為此，請使用 **[!UICONTROL Split]** 為每個通道在預配時建立路由模式：

* 拆分交付 — 電子郵件(splitDeliveryEmail)
* 拆分交付 — SMS(splitDeliverySMS)
* 拆分交付 — iOS(splitDeliveryIOS)
* 拆分交付 — Android(splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>預設情況下，「拆分交貨 — 電子郵件」帳戶啟用拆分路由模式。 對於所有其它渠道的外部帳戶，請聯繫「客戶服務」以啟用該選項。
>
>預設情況下，在多個mid之間拆分傳遞的閾值大小值為100K。 您可以在中的「NmsDelivery_MultiMidSplitThreshold」選項中更改此值 **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** 的子菜單。

為了使分解外部帳戶成為發送交貨的預設帳戶，您需要在交貨模板中更改傳送提供商。 要執行此操作，請依照下列步驟執行：

1. 導航到 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** 資料夾並開啟所需的傳遞模板。 在本示例中，我們要編輯電子郵件傳遞模板。

   ![](assets/split-default-list.png)

1. 按一下 **[!UICONTROL Properties]** 按鈕並將傳送提供程式更改為相應的分解交貨外部帳戶。

   ![](assets/split-default-delivery.png)

1. 儲存您的變更。預設情況下，使用模板發送的所有交貨現在都將使用分解工藝路線模式。

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

## 消息中心體系結構{#transac-msg-archi}

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

![](../assets/do-not-localize/glass.png) 瞭解如何在 [此部分](../send/transactional.md)。

響應於客戶在網站上的動作，通過REST API發送活動，並且消息模板填充通過API調用提供的資訊或資料，並且事務性消息即時地發送給客戶。 這些消息可以單獨或通過電子郵件、簡訊或推式通知批量發送。

在此特定體系結構中，執行單元與控制實例分離以確保高可用性和負載管理。

* 的 **控制實例** （或營銷實例）由營銷人員和IT團隊用於建立、配置和發佈消息模板。 此實例還集中了事件監視和歷史記錄。

   ![](../assets/do-not-localize/glass.png) 瞭解如何在中建立和發佈消息模板 [此部分](../send/transactional.md)。

* 的 **執行實例** 重置傳入事件（例如密碼重置或來自網站的訂單）併發送個性化消息。 可以有多個執行實例通過負載平衡器處理消息，並擴展要進行的事件數以實現最大可用性。

>[!CAUTION]
>
>控制實例和執行實例必須安裝在不同的電腦上。 他們不能共用同一Campaign實例。

![](assets/messagecenter_diagram.png)

### 驗證

要使用這些功能，Adobe Campaign用戶登錄到控制實例以建立事務性消息模板，使用種子清單生成消息預覽，顯示報告和監視執行實例。

* 單個執行實例當與Adobe托管的消息中心執行實例交互時，外部系統可以首先檢索會話令牌（預設在24小時內過期），方法是使用提供的帳戶登錄和密碼對會話登錄方法進行api調用。
然後，通過執行實例響應上述調用提供的sessionToken，外部應用程式可以進行SOAP api調用（rtEvents或batchEvents）來發送通信，而無需在每個SOAP調用中包括帳戶登錄和密碼。

* 多個執行實例在負載平衡器後面具有多個執行實例的多單元執行體系結構中，外部應用程式調用的登錄方法正通過負載平衡器：因此，不能使用基於令牌的身份驗證。 需要基於用戶/密碼的驗證。

瞭解有關中事務性消息傳遞事件的詳細資訊 [此頁](../send/event-processing.md)。
