---
title: 了解 Campaign 元件和程序
description: 了解 Campaign 元件和程序
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: ht
source-wordcount: '637'
ht-degree: 100%

---

# 了解 Campaign 元件和程序 {#components-and-processes}

Adobe Campaign 是跨通道行銷解決方案，可自動化電子郵件、行動裝置、社交和離線行銷活動。Adobe Campaign 提供一處集中式位置，可存取您的客戶資料和輪廓。使用 Adobe Campaign 為客戶打造一致的體驗，跨通道設計、執行並個人化您的行銷，同時改善每個裝置和接觸點的客戶體驗。使用 Adobe Campaign，您可以透過拖放視覺工作流程介面管理多個資料來源、定義對象區段，以及規劃和執行多步驟、跨通道的行銷活動。

在[本頁面](../start/get-started.md)中進一步瞭解 Campaign 主要功能。

## Campaign 元件 {#ac-components}

Adobe Campaign 元件和全球架構如下所示。

![](assets/do-not-localize//ac-components.png)

### 展示層{#presentation-layer}

您可以透過 Rich 用戶端、Thin 用戶端或 API 整合來存取 Adobe Campaign。

* Rich 用戶端

  Campaign Rich 用戶端是原生應用程式，可透過標準網際網路通訊協定 (例如 SOAP 和 HTTP) 與 Adobe Campaign 應用程式伺服器通訊。[進一步瞭解 Campaign 用戶端主控台](../start/connect.md)。

* Thin 用戶端

  Adobe Campaign 網頁存取功能可讓您使用 HTML 使用者介面，透過網頁瀏覽器存取 Campaign 功能的子集。使用此網頁介面存取報告、控制和驗證訊息、存取監控儀表板等。[深入瞭解 Campaign 網頁存取](../start/connect.md)。

* 外部應用程式與 API

  在某些情況下，可使用透過 SOAP 通訊協定公開的網頁服務 API，從外部應用程式呼叫系統。[進一步瞭解 Campaign API](../dev/api.md)。

### 持續層{#persistance-layer}

Campaign 資料庫用作持續層，並包含 Adobe Campaign 管理的幾乎所有資訊和資料。這包括：功能資料，例如輪廓、訂閱、內容；技術資料，例如傳遞工作和記錄、追蹤記錄；以及工作資料 (購買、潛在客戶)。

資料庫的可靠性至關重要，因為大部分 Adobe Campaign 元件都需要存取資料庫才能執行其工作 (重新導向模組除外)。

### 邏輯應用程式層{#logical-app-layer}

Campaign 邏輯應用程式層可輕鬆設定，以符合複雜的業務需求。您可以將 Campaign 作為單一平台使用，搭配不同的應用程式，以建立開放且可擴充的架構。每個 Campaign 執行個體都是應用程式層中的程序集合，部分為共用，部分為專用。

## Campaign Managed Cloud Services{#ac-managed-services}

Adobe Campaign v8 已作為 Managed Service 部署：Adobe Campaign 的所有元件 (包括使用者介面、執行管理引擎和 Campaign 資料庫) 皆完全由 Adobe 託管，包括電子郵件執行、鏡像頁面、追蹤伺服器和對外的網頁元件，例如取消訂閱頁面/偏好設定中心和登陸頁面。

## Campaign 程序

Campaign Web 伺服器會控制 Campaign Web 程序的存取權。JavaScript 是用於核心產品功能和自訂的伺服器端語言。Tomcat 是後端引擎，並作為 Web 程序的一部分內嵌在 Campaign 產品中。例如，JSP 或 JSSP 頁面會使用 JavaScript 來轉譯動態內容。

![](assets/do-not-localize/ac-processes.png)

Campaign 用戶端主控台會透過 HTTP 使用 SOAP XML 連線至 Web 伺服器。Web 伺服器提供安全性層，使用 JavaScript 將請求傳遞至應用程式層，Campaign 內部程序則使用 SQL 存取資料庫。

<!--The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/do-not-localize//ac-standalone.png) -->

使用者會使用 HTTP 連線至 Campaign 應用程式伺服器。所有資料和資訊都在 Campaign 資料庫中進行管理。如果 Campaign 開發人員執行任何設定變更，則會擷取到資料庫中。如果行銷人員建立新行銷活動，與此新行銷活動相關的所有資訊和資料也將在資料庫中進行管理。行銷人員執行行銷活動時，會透過 SMTP 伺服器將電子郵件傳遞從 Campaign 伺服器傳送至輪廓。當輪廓與電子郵件傳遞互動時 (例如打開電子郵件)，追蹤資料會傳回至追蹤伺服器。

[深入瞭解 Campaign 程序](../architecture/general-architecture.md#dev-env)。
