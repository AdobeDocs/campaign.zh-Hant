---
title: Campaign v8 的新增功能
description: 探索 Campaign v8 中的重要功能
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 79a220ad9c9c372b64db9a33efc1843c95a2a619
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 30%

---

# Adobe Campaign v8 有哪些新功能？ {#ac-gs-what-is-new}

Adobe Campaignv8專為需要一流雲解決方案的跨渠道營銷人員而設計，該解決方案適用於具有企業規模的跨渠道營銷活動管理。 它提供強大的ETL和資料管理功能，幫助制定和組織完美的活動。 其業務流程引擎為豐富的多點觸控營銷計畫提供了支援，其核心是基於批處理的驅動行程。 它還配備了可擴展的即時消息伺服器，使營銷團隊能夠基於來自任何IT系統的包含所有內容的負載來發送預定義的消息，用於諸如密碼重置、訂單確認、電子回執等等。

Adobe Campaign v8 明顯改善基礎架構、安全性、可傳遞性和監視功能。 

![](assets/home-page.png)

## 主要功能{#key-capabilities}

主要功能包括：

* **集中工作流管理**。 提高營銷活動各個方面的速度和規模，從建立市場細分和準備消息到交付。

   Adobe Campaign通過單一、易用的市場活動業務流程介面，讓您輕鬆實現渠道同步。 因此，您的線上渠道 — 如電子郵件、網路、移動和社交渠道 — 與您的離線渠道相匹配，包括直郵、呼叫中心、店內等。 它使您能夠在數字和傳統渠道中為客戶提供一致和上下文相關的體驗。 Adobe Campaign使內容能夠輕鬆地通過任何渠道向客戶可能採取的所有途徑提供。

   ![](../assets/do-not-localize/glass.png) [瞭解有關市場活動工作流的詳細資訊](../config/workflows.md)

* **個性化電子郵件營銷**。 建立與客戶其他體驗相一致的個性化和上下文相關的電子郵件。

   有了Adobe Campaign，您可以讓電子郵件更好、更個性化、更盈利。 電子郵件建立簡單，易於傳遞。 市場活動v8讓您能夠靈活地設計、個性化、test、細化和改進您發送的每封郵件。

   ![](../assets/do-not-localize/glass.png) [瞭解有關個性化功能的詳細資訊](create-message.md)

* **客戶資料管理**。 查看客戶的整張圖片，以便您可以快速建立企業規模的個性化市場活動。

   Adobe Campaign幫助您根據收集到的所有渠道的資料構建客戶配置檔案。 使用此配置檔案，您可以跨渠道協調市場活動。 通過連接所有營銷渠道，您可以定制每個客戶將採取的對他們有意義的方式的不同行程。

   ![](../assets/do-not-localize/glass.png) [瞭解有關客戶資料管理的更多資訊](audiences.md)

* **同類最佳的促銷活動管理**。 Adobe Campaignv8為營銷人員提供了一流的能力，可以跨渠道規劃、發佈和衡量營銷活動。

   功能包括提供客戶單一視圖的整合配置檔案。 針對大規模活動受眾構建的資料管理和細分。 跨渠道工作流管理，用於自動化多渠道和多波次的活動。 整合電子郵件，減少對成本高昂的ESP的依賴。 報告和分析，以瞭解客戶行為和市場活動績效。

   ![](../assets/do-not-localize/glass.png) [瞭解有關市場活動管理的詳細資訊](campaigns.md)


* **與Adobe Experience Platform的聯繫**。 Adobe Campaignv8支援與Real-Time CDP和Adobe Experience Platform的資料連接器，因此組織可以利用即時統一的客戶配置檔案。

   此外，Adobe Campaignv8與即時行程協調功能本機整合，因此營銷人員可以重新使用Adobe Campaign的相同模板和交付功能，以便與客戶即時接觸。 這些投資將最佳化 Adobe Campaign 的客戶體驗，並解鎖新的使用實例，例如新增個人化即時客戶歷程至行銷活動等功能。

   您也可以使用 Journey AI 設定預測性傳送時間最佳化和預測性參與度評分，並提高開放率、點擊次數和收入。

   ![](../assets/do-not-localize/glass.png) [進一步瞭解 Campaign 整合](../connect/integration.md)


* **Managed Cloud Services**。Adobe Campaignv8可作為托管Cloud Service提供，提供前瞻性監督、及時警報和服務治理。

   Adobe受管Cloud Service為營銷商提供了更靈活、安全和可擴展的跨渠道營銷管理解決方案，而且總體擁有成本低。 這一新產品將服務與前瞻性監督和及時警報結合在一起。

* **速度和規模**。Adobe Campaign現在可以利用雲規模資料庫技術來大幅提高其規模和速度。

   [市場活動v8企業版](../architecture/enterprise-deployment.md) 帶來了 **完全聯合資料存取** (FFDA):現在，雲資料庫上的所有資料都是遠程資料。 利用此新產品，Campaign v8簡化了資料管理：雲資料庫不需要索引。 您只需要建立表格、複製資料，即可開始。[!DNL Snowflake] 是 Campaign Cloud 資料庫，可為您帶來速度和耐力：系統活動峰值不會過載。雲端資料庫技術不需要進行具體的維護來保證效能等級。

   ![](../assets/do-not-localize/glass.png) [瞭解有關企業(FDA)部署的詳細資訊](../architecture/enterprise-deployment.md)


>[!CAUTION]
>
>* 市場活動v8是 **僅** 可作為托管Cloud Service使用，並且不能部署在內部或混合環境中。
>
>* 尚無法從現有 Campaign Classic v7 環境進行移轉。




## 自助服務管理介面{#self-service-admin}

作為產品管理員，您可以利用 **Campaign 控制面板**&#x200B;來管理設定並追蹤每個 Campaign v8 執行個體的使用情況。

透過直觀的使用者介面，管理員可以監視重要資產的使用情況，執行進階任務，例如 IP 位址允許清單、SFTP 儲存監視、金鑰管理等等。 此自助服務介面為您帶來更多彈性，並幫助您：

* 自行快速變更設定，而無需聯絡 Adobe 支援部門。
* 根據不同時間的不同業務需求進行設定
* 根據需求控制存取設定，以加強安全性

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [深入瞭解 Campaign 控制面板](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=zh-Hant){target=&quot;_blank&quot;}


