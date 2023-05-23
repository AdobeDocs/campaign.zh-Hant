---
title: 瞭解市場活動流程和元件
description: 瞭解市場活動流程和元件
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 2ec240b139394ce8f54a5835a4fa7bd377d226eb
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 1%

---

# 瞭解市場活動流程和元件 {#components-and-processes}

Adobe Campaign是一個跨渠道營銷解決方案，可自動執行電子郵件、移動、社交和離線活動。 Adobe Campaign為訪問您的客戶資料和配置檔案提供了一個中心位置。 使用Adobe Campaign為您的客戶協調一致的體驗，設計、執行和個性化您的跨渠道的營銷，同時改善客戶在每台設備和觸摸點上的體驗。 使用Adobe Campaign，您可以管理多個資料源、定義受眾群，以及通過拖放式可視工作流介面計畫和執行多步跨渠道市場活動。

瞭解有關中市場活動關鍵功能的詳細資訊 [此頁](../start/get-started.md)。

## 市場活動元件 {#ac-components}

Adobe Campaign元件和全球架構如下所述。

![](assets/ac-components.png)

### 表示層{#presentation-layer}

您可以通過富客戶端、瘦客戶端或API整合訪問Adobe Campaign。

* 富客戶端

   Campaign Rich客戶端是一個本機應用程式，它通過標準的Internet協定（如SOAP和HTTP）與Adobe Campaign應用伺服器通信。 [ 進一步瞭解 Campaign 用戶端主控台](../start/connect.md)。

* 瘦客戶機

   Adobe CampaignWeb訪問功能允許您使用Web瀏覽器使用HTML用戶介面訪問市場活動功能的子集。 使用此Web介面可訪問報告、控制和驗證消息、訪問監控儀表板等。  [ 深入瞭解 Campaign 網頁存取](../start/connect.md)。

* 具有API的外部應用程式

   在某些情況下，可以使用通過SOAP協定公開的Web服務API從外部應用程式調用系統。 [瞭解有關市場活動API的詳細資訊](../dev/api.md)。

### 持久性層{#persistance-layer}

市場活動資料庫被用作持久層，幾乎包含所有由Adobe Campaign管理的資訊和資料。 這包括：功能資料，如配置檔案、訂閱、內容；技術資料，如交付作業和日誌、跟蹤日誌；和工作資料（採購、銷售線索）。

資料庫的可靠性至關重要，因為大多數Adobe Campaign元件都要求訪問資料庫以執行其任務（重定向模組除外）。

### 邏輯應用層{#logical-app-layer}

市場活動邏輯應用層可輕鬆配置以滿足複雜的業務需求。 您可以將市場活動用作一個具有不同應用程式的單一平台，這些應用程式結合在一起可建立開放且可擴展的體系結構。 每個活動實例都是應用層中流程的集合，其中一些流程是共用的，有些流程是專用的。

## 市場活動管理Cloud Services{#ac-managed-services}

Adobe Campaignv8部署as a Managed Service:Adobe Campaign的所有元件（包括用戶介面、執行管理引擎和市場活動資料庫）都完全由Adobe托管，包括電子郵件執行、鏡像頁、跟蹤伺服器以及面向外部的Web元件（如取消訂閱頁/首選項中心和登錄頁）。

## 市場活動流程

市場活動Web伺服器控制對市場活動Web進程的訪問。 Javascript是用於核心產品功能和定製的伺服器端語言。 Tomcat是後端引擎，作為Web流程的一部分嵌入到Campaign產品中。 例如，在JSP或JSSP頁中使用Javascript來呈現動態內容。

![](assets/ac-processes.png)

市場活動客戶端控制台使用SOAP XML over HTTP連接到Web伺服器。 Web伺服器提供安全層，使用Javascript將請求傳遞到應用層，而市場活動內部進程使用SQL訪問資料庫。

以下獨立部署圖描述了市場活動流程之間的總體通信：所有市場活動元件都安裝在同一台電腦中。

![](assets/ac-standalone.png)

用戶使用HTTP連接到市場活動應用程式伺服器。 所有資料和資訊都在市場活動資料庫中管理。 如果市場活動開發人員執行任何配置更改，則會在資料庫中捕獲它。 如果營銷人員建立新市場活動，則與此新市場活動相關的所有資訊和資料也將在資料庫中管理。 當營銷商執行市場活動時，電子郵件遞送通過SMTP伺服器從市場活動伺服器發送到配置檔案。 當配置檔案與電子郵件遞送（例如開啟電子郵件）交互時，跟蹤資料被發回到跟蹤伺服器。

![](../assets/do-not-localize/glass.png) [瞭解有關市場活動流程的詳細資訊](../architecture/general-architecture.md#dev-env)。
