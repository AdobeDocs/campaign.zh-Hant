---
solution: Campaign
product: Adobe Campaign
title: 開始使用Campaign架構
description: 開始使用Campaign架構
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# 開始使用促銷活動架構{#gs-ac-archi}

## 環境

促銷活動可做為個別例項使用，每個例項代表完整的促銷活動環境。

促銷活動Cloud Service提供的三種環境類型：

* 生產環境：為業務從業者代管應用程式。

* 舞台環境：在將應用程式的變更推送至生產環境之前，先用於各種效能和品質測試。

* 開發環境：可讓開發人員在與舞台和生產環境相同的執行時期條件下實作Campaign。

您可以將軟體包從一個環境導出並導入到另一個環境。

:arrow_upper_right:進一步瞭解[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)中的軟體包

## 中間來源部署{#mid-sourcing-deployment}

伺服器和進程之間的通用通信根據以下方案進行：

![](assets/architecture.png)

* 執行和彈回管理模組在實例上被禁用。

* 應用程式已設定為在使用SOAP呼叫（透過HTTP或HTTPS）驅動的遠端「中端來源」伺服器上執行訊息。

>[!NOTE]
>
> Campaign v8採用混合式架構。 如果您要從Campaign Classicv7轉換，請注意，所有傳送都會經過中間採購伺服器。
> 因此，在促銷活動v8中內部路由是&#x200B;**不可能**，因此已停用外部帳戶。


## 消息中心體系結構{#transac-msg-archi}

交易式訊息（訊息中心）是專為管理觸發訊息而設計的促銷活動模組。

：球：瞭解如何在[本節](../send/transactional.md)中發送事務性消息。

響應於客戶在網站上的動作，事件會透過REST API傳送促銷活動，訊息範本會填入透過API呼叫提供的資訊或資料，而交易訊息會即時傳送給客戶。 這些訊息可以個別傳送或透過電子郵件、簡訊或推播通知分批傳送。

在該特定架構中，執行單元與控制實例分開，以確保高可用性和負載管理。

* **Control instance**（或Marketing instance）由行銷人員和IT團隊用來建立、設定和發佈訊息範本。 此例項也集中管理事件監視和歷史記錄。

   :arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)中建立和發佈訊息範本

* **執行例項**&#x200B;會保留傳入事件（例如密碼重設或來自網站的訂單）並傳送個人化訊息。 可以有多個執行實例通過負載平衡器處理消息，並擴展要處理的事件數以實現最大可用性。

>[!CAUTION]
>
>控制實例和執行實例必須安裝在不同的電腦上。 他們無法共用相同的促銷活動例項。

![](assets/messagecenter_diagram.png)

:arrow_upper_right:[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)中介紹了消息中心體系結構


### 驗證

為了使用這些功能，Adobe Campaign用戶登錄到控制實例以建立事務性消息模板，使用種子清單生成消息預覽，顯示報告和監視執行實例。

* 單執行實例
當與Adobe代管的消息中心執行實例交互時，外部系統可以使用提供的帳戶登錄和密碼，通過對會話登錄方法進行API調用，首先檢索會話令牌（預設在24小時內過期）。
然後，使用執行例項為回應上述呼叫而提供的sessionToken，外部應用程式可進行SOAP api調用（rtEvents或batchEvents）來傳送通訊，而不需在每個SOAP呼叫中加入帳戶登入和密碼。

* 多個執行例項
在負載平衡器後面具有多個執行實例的多小區執行體系結構中，外部應用程式調用的登錄方法正在通過負載平衡器：因此，無法使用以Token為基礎的驗證。 需要使用者／密碼驗證。

:arrow_upper_right:在[Campaign Classic文檔](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)中進一步瞭解事務性消息傳遞事件