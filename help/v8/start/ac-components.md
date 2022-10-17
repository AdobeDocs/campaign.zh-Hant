---
title: 了解Campaign流程和元件
description: 了解Campaign流程和元件
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 46be0379610a6a4a3491d49ce096c64270ed8016
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---

# 了解Campaign流程和元件 {#components-and-processes}

Adobe Campaign是跨通道行銷解決方案，可自動執行電子郵件、行動裝置、社交和離線行銷活動。 Adobe Campaign提供存取客戶資料和設定檔的集中位置。 使用Adobe Campaign為客戶協調一致的體驗、設計、執行並個人化各管道的行銷，同時改善每個裝置和接觸點上的客戶體驗。 透過Adobe Campaign，您可以透過拖放式視覺化工作流程介面來管理多個資料來源、定義對象區段，以及規劃及執行多步驟跨通道促銷活動。

進一步了解Campaign重要功能，位於 [本頁](../start/get-started.md).

## 促銷活動元件 {#ac-components}

Adobe Campaign元件和全域架構於下方說明。

![](assets/ac-components.png)

### 展示層{#presentation-layer}

您可以透過Rich用戶端、精簡用戶端或API整合來存取Adobe Campaign。

* 富客戶端

   Campaign Rich用戶端是原生應用程式，可透過標準網際網路通訊協定（例如SOAP和HTTP）與Adobe Campaign應用程式伺服器通訊。

   Campaign用戶端主控台會集中所有功能和設定，因需最低頻寬，因為它需仰賴本機快取。 Campaign用戶端主控台可從網際網路瀏覽器部署，且可自動更新，且不需要任何特定的網路設定，因為它只會產生HTTP(S)流量。

   ![](../assets/do-not-localize/glass.png) [進一步瞭解 Campaign 用戶端主控台](../start/connect.md)。

* 瘦客戶端

   Adobe Campaign Web存取功能可讓您使用網頁瀏覽器，使用HTML使用者介面存取Campaign功能的子集。 使用此Web介面來存取報告、控制和驗證訊息、存取監控控制面板等。

   ![](../assets/do-not-localize/glass.png) [深入瞭解 Campaign 網頁存取](../start/connect.md)。

* 使用API的外部應用程式

   在某些情況下，可使用透過SOAP通訊協定公開的網站服務API，從外部應用程式呼叫系統。

   ![](../assets/do-not-localize/glass.png) [進一步了解Campaign API](../dev/api.md).

### 持久層{#persistance-layer}

Campaign資料庫是作為持續性層，包含幾乎所有由Adobe Campaign管理的資訊和資料。 這包括：功能資料，例如設定檔、訂閱、內容；技術資料，例如傳送工作和記錄、追蹤記錄；和工作資料（購買、銷售機會）。

資料庫的可靠性至關重要，因為大多數Adobe Campaign元件都需要訪問資料庫以執行其任務（重定向模組除外）。

### 邏輯應用層{#logical-app-layer}

Campaign邏輯應用程式層可輕鬆配置，以滿足複雜的業務需求。 您可以將Campaign作為具有不同應用程式的單一平台，結合這些應用程式來建立開放且可擴充的架構。 每個Campaign實例都是應用程式層中的程式集合，有些是共用的，有些是專用的。

## Campaign管理的Cloud Services{#ac-managed-services}

Adobe Campaign v8部署as a Managed Service:Adobe Campaign的所有元件（包括使用者介面、執行管理引擎和Campaign資料庫）都完全由Adobe托管，包括電子郵件執行、鏡像頁面、追蹤伺服器，以及對外的Web元件，例如取消訂閱頁面/偏好設定中心和登錄頁面。

## 行銷活動程式

促銷活動網站伺服器控制對促銷活動網站進程的存取。 Javascript是用於核心產品功能和自訂的伺服器端語言。 Tomcat是後端引擎，是Web流程中嵌入到Campaign產品中的。 例如，JSP或JSSP頁中使用Javascript來呈現動態內容。

![](assets/ac-processes.png)

Campaign用戶端主控台使用SOAP XML over HTTP連線至Web伺服器。 Web伺服器提供安全層，使用Javascript將請求傳遞至應用程式層，而Campaign內部程式使用SQL存取資料庫。

以下獨立部署圖表中說明Campaign程式之間的整體通訊：所有Campaign元件都安裝在同一部電腦中。

![](assets/ac-standalone.png)

使用者使用HTTP連線至Campaign應用程式伺服器。 所有資料和資訊都在Campaign資料庫中管理。 如果Campaign開發人員執行任何設定變更，則會擷取至資料庫。 如果行銷人員建立新促銷活動，與此新促銷活動相關的所有資訊和資料也會在資料庫中管理。 當行銷人員執行促銷活動時，會透過SMTP伺服器，將電子郵件傳送傳送至來自促銷活動伺服器的設定檔。 當設定檔與電子郵件傳送互動時（例如開啟電子郵件），該追蹤資料會傳回至追蹤伺服器。

![](../assets/do-not-localize/glass.png) [深入了解Campaign流程](../architecture/general-architecture.md#dev-env).
