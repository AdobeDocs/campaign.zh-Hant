---
product: Adobe Campaign
title: 開始使用Campaign架構
description: 開始使用Campaign架構
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 973e04eb25887f63564b416515c6e229ed5233a4
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 2%

---

# 開始使用Campaign架構{#gs-ac-archi}

## 環境

促銷活動可作為個別例項使用，每個例項代表完整的促銷活動環境。

CampaignCloud Service提供的三種環境類型：

* **生產環境**:為業務從業者托管應用程式。

* **預備環境**:在將應用程式的變更推送至生產環境之前，會先用於各種效能和品質測試。

* **開發環境**:可讓開發人員在與預備和生產環境相同的執行階段條件下實作Campaign。

您可以將套件從一個環境匯出並匯入至另一個環境。

[!DNL :arrow_upper_right:] 進一步了解 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## 中間來源部署{#mid-sourcing-deployment}

伺服器和進程之間的一般通信根據以下模式執行：

![](assets/architecture.png)

* 執行和退信管理模組在執行個體上是停用的。

* 應用程式可配置為在使用SOAP呼叫（通過HTTP或HTTPS）驅動的遠程「中源」伺服器上執行消息。

>[!NOTE]
>
> Campaign v8仰賴混合架構。 如果您要從Campaign Classicv7轉換，請注意所有傳送都會經過中間來源伺服器。
> 因此，在Campaign v8中，內部路由是&#x200B;**不可能**，因此已停用外部帳戶。

## 消息中心體系結構{#transac-msg-archi}

異動訊息 (訊息中心) 是專為管理觸發訊息而設計的 Campaign 模組。

[!DNL :bulb:] 在本小節中了解如何傳送交 [易式訊息](../send/transactional.md)。

為了回應客戶在網站上的動作，事件會透過REST API傳送Campaign，而訊息範本會填入透過API呼叫提供的資訊或資料，而交易式訊息會即時傳送給客戶。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知分批傳送。

在此特定架構中，執行單元與控制實例分離，以確保高可用性和負載管理。

* 行銷人員和IT團隊會使用&#x200B;**控制例項**（或行銷例項）來建立、設定和發佈訊息範本。 此例項也會集中事件監控和歷史記錄。

   [!DNL :bulb:] 在本小節中了解如何建立和發佈 [訊息範本](../send/transactional.md)。

* **執行實例**&#x200B;會檢索傳入事件（例如密碼重置或來自網站的訂單）併發送個性化消息。 可以有多個執行實例通過負載平衡器處理消息，並縮放要進行的事件數以實現最大可用性。

>[!CAUTION]
>
>控制實例和執行實例必須安裝在不同的電腦上。 他們無法共用相同的Campaign執行個體。

![](assets/messagecenter_diagram.png)

[!DNL :arrow_upper_right:] Campaign Classicv7檔案中會說明訊 [息中心架構](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/transactional-messaging-architecture.html)

### 驗證

若要使用這些功能，Adobe Campaign使用者需登入控制執行個體以建立交易式訊息範本、使用種子清單產生訊息預覽、顯示報表及監控執行執行執行執行個體。

* 單一執行例項
當與托管的Adobe消息中心執行實例交互時，外部系統可以使用提供的帳戶登錄和密碼，通過對會話登錄方法發出api調用來首先檢索會話令牌（預設在24小時內過期）。
然後，由執行例項提供以回應上述呼叫的sessionToken，外部應用程式可讓SOAP api叫用（rtEvents或batchEvents）來傳送通訊，而不需要在每個SOAP呼叫中納入帳戶登入和密碼。

* 多個執行實例
在負載平衡器後面具有多個執行實例的多小區執行體系結構中，外部應用程式調用的登錄方法正在通過負載平衡器：因此，無法使用以權杖為基礎的驗證。 需要基於用戶/密碼的身份驗證。

[!DNL :arrow_upper_right:] 進一步了解Campaign Classicv7檔案中 [的交易式訊息事件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)