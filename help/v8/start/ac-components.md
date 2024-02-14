---
title: 瞭解Campaign元件和流程
description: 瞭解Campaign元件和流程
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 79d916c4d65c0c55ec20f2f5850fec40fe4e99a3
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# 瞭解Campaign元件和流程 {#components-and-processes}

Adobe Campaign是跨管道行銷解決方案，可自動化電子郵件、行動裝置、社交和離線行銷活動。 Adobe Campaign提供中央位置，可存取您的客戶資料和設定檔。 使用Adobe Campaign為客戶打造一致的體驗，跨管道設計、執行並個人化您的行銷，同時改善每個裝置和接觸點的客戶體驗。 透過Adobe Campaign，您可以透過拖放視覺工作流程介面管理多個資料來源、定義對象區段，以及規劃和執行多步驟、跨頻道行銷活動。

進一步瞭解Campaign的關鍵功能，在 [此頁面](../start/get-started.md).

## 行銷活動元件 {#ac-components}

Adobe Campaign元件和全球架構說明如下。

![](assets/do-not-localize//ac-components.png)



### 持續層{#persistance-layer}

Campaign資料庫用作持續層，並包含Adobe Campaign管理的幾乎所有資訊和資料。 這包括：功能資料，例如設定檔、訂閱、內容；技術資料，例如傳送工作和記錄、追蹤記錄；以及工作資料（購買、銷售機會）。

資料庫的可靠性至關重要，因為大部分Adobe Campaign元件都需要存取資料庫才能執行其工作（重新導向模組除外）。

### 邏輯應用程式層{#logical-app-layer}

Campaign邏輯應用程式層可輕鬆設定，以符合複雜的業務需求。 您可以將Campaign作為單一平台使用，搭配不同的應用程式，以建立開放且可擴充的架構。 每個Campaign執行個體都是應用程式層中的程式集合，部分為共用狀態，部分為專用狀態。

## Campaign ManagedCloud Service{#ac-managed-services}

Adobe Campaign v8是as a Managed Service部署：Adobe Campaign的所有元件（包括使用者介面、執行管理引擎和Campaign資料庫）都完全由Adobe託管，包括電子郵件執行、映象頁面、追蹤伺服器以及對外的Web元件（例如取消訂閱頁面/偏好設定中心和登陸頁面）。

## 行銷活動程式

Campaign網頁伺服器會控制Campaign網頁程式的存取權。 Javascript是用於核心產品功能和自訂的伺服器端語言。 Tomcat是後端引擎，並作為Web程式的一部分內嵌在Campaign產品中。 JSP或JSSP頁面會使用Javascript來呈現動態內容。

![](assets/do-not-localize/ac-processes.png)

Campaign使用者端主控台會透過HTTP使用SOAP XML連線至Web伺服器。 Web伺服器提供安全性層，使用Javascript將請求傳遞至應用程式層，Campaign內部處理程式則使用SQL存取資料庫。

Campaign流程之間的整體通訊如下獨立部署圖表所述：所有Campaign元件都安裝在同一部電腦中。

![](assets/do-not-localize//ac-standalone.png)

使用者會使用HTTP連線至Campaign應用程式伺服器。 所有資料和資訊都在Campaign資料庫中進行管理。 如果Campaign開發人員執行任何設定變更，則會擷取到資料庫中。 如果行銷人員建立新行銷活動，與此新行銷活動相關的所有資訊和資料也將在資料庫中進行管理。 行銷人員執行行銷活動時，會透過SMTP伺服器將電子郵件傳遞從Campaign伺服器傳送至設定檔。 當設定檔與電子郵件傳送互動時（例如開啟電子郵件），追蹤資料會傳回至追蹤伺服器。

![](../assets/do-not-localize/glass.png) [進一步瞭解Campaign流程](../architecture/general-architecture.md#dev-env).
