---
title: 開始使用活動體系結構
description: 探索環境和部署基本知識
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 3%

---

# 活動體系結構入門{#gs-ac-archi}

## 環境

市場活動可以作為單個實例提供，每個實例代表完整的市場活動環境。

市場活動Cloud Service提供的三種環境類型：

* **生產環境**:為業務從業者托管應用程式。

* **階段環境**:在將應用程式更改推送到生產環境之前，用於各種效能和質量test。

* **開發環境**:允許開發人員在與階段和生產環境相同的運行時條件下實施市場活動。

您可以將軟體包從一個環境導出並導入到另一個環境。

![](../assets/do-not-localize/book.png) 瞭解有關中的包的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## 中間來源部署{#mid-sourcing-deployment}

伺服器和進程之間的一般通信按照以下模式進行：

![](assets/architecture.png)

* 實例上禁用了執行和彈出管理模組。

* 該應用程式配置為在使用SOAP調用（通過HTTP或HTTPS）驅動的遠程「中間源」伺服器上執行消息。

>[!NOTE]
>
> Campaing v8依賴於混合架構。 如果要從Campaign Classicv7進行轉換，請注意，所有交貨都通過中間採購伺服器。
> 因此，內部路由 **不可能** 在市場活動v8中，外部帳戶已相應禁用。

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

![](../assets/do-not-localize/book.png) 瞭解有關中事務性消息傳遞事件的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)