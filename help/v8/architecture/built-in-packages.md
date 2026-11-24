---
title: 內建套件
description: 瞭解Campaign v8中有哪些內建套件，它們與自訂資料套件的差異，以及有哪些可用
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 87e9b7ceb3c082407ac4534e0909c6f7db76e62a
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 15%
---
# 內建套件 {#built-in-packages}

內建套件（也稱為標準套件）包含Adobe Campaign的功能。 在Campaign v8中，Adobe會為您安裝及管理這些套件。 您不需要安裝。

## 內建套件和自訂套件 {#built-in-vs-custom}

Campaign使用兩種套件。 請確定您使用正確的伺服器。

| | 內建套件 | 自訂套件 |
|---|---|---|
| 用途 | 提供Campaign功能，例如管道、整合和附加元件。 | 匯出並匯入您自己的設定和資料，例如從測試環境匯入生產環境。 |
| 誰管理這些資產 | Adobe會安裝並管理這些程式。 若使用受管理的Cloud Services，您無法修改已安裝的內建套件。 | 您可以建立、匯出和匯入它們。 |

## 檢查已安裝的套件 {#check-installed-packages}

若要檢查執行個體上已安裝哪些內建套件，請瀏覽至&#x200B;**[!UICONTROL Administration > Configuration > Package management > Installed packages]**。 您也可以在「控制面板」的「執行個體監視」中檢視它們。 深入瞭解[行銷活動監視概觀](../start/monitor.md#monitor-instance)。

如果您需要未布建的套件或附加元件，請聯絡Adobe客戶服務或您的Adobe轉換經理。

## 內建套件清單 {#list-of-built-in-packages}

下表列出內建套件以供參考。 每個套件的可用性都受限於您的授權合約和部署模式。

| 套件 | 說明 |
|---|---|
| 傳遞 | Adobe Campaign的強制核心套件。 它可讓您傳送傳遞。 [了解更多](../start/gs-message.md) |
| 行銷活動 (Campaign) | 定義、最佳化、執行和分析通訊和行銷活動。 [了解更多](../start/campaigns.md) |
| 行銷資源 (MRM) | 以合作模式控制行銷動作，管理並追蹤任務、預算和行銷資源。 [了解更多](../../automation/mrm/about-marketing-resource-management.md) |
| 優惠方案引擎（互動） | 在與聯絡人互動期間，透過提出一或多個適用優惠方案來即時回應。 [了解更多](../interaction/interaction.md) |
| 社交網路 (社交行銷) | 將Adobe Campaign與X （前身為Twitter）同步。 [了解更多](../connect/ac-tw.md) |
| 異動訊息控制與執行（訊息中心） | 管理從資訊系統中的事件產生的觸發訊息，提供更高的可用性和更好的負載管理。 [了解更多](../send/transactional.md) |
| LINE 管道 | 透過LINE頻道傳送傳遞。 [了解更多](../send/line/line.md) |
| 直接郵件管道 | 透過直接郵件通道傳送傳遞。 [了解更多](../send/direct-mail.md) |
| 行動裝置管道 (簡訊) | 透過行動裝置頻道(SMS)傳送傳遞，包括SMS聯結器v2 （自8.9.1起通常可用）。 [了解更多](../send/sms/sms.md) |
| 行動應用程式頻道 | 透過應用程式將個人化通知傳送至iOS和Android裝置。 [了解更多](../send/push.md) |
| 內容管理員 | 建立週期性電子報或網站，然後驗證並發佈您的訊息。 [了解更多](../../automation/workflow/content-management.md) |
| 線上意見調查 (意見調查管理員) | 建立和管理線上表單，以新增或修改設定檔資訊、訂閱、取消訂閱或輸入競爭者。 [了解更多](../dev/surveys/about-surveys.md) |
| 行銷分析 | 分析和測量資料、計算統計資料，以及簡化報告建立。 [了解更多](../reporting/gs-reporting.md) |
| 回應管理員 | 衡量所有管道行銷活動或優惠方案的成功和獲利能力。 [了解更多](../../automation/response/about-response-manager.md) |
| 存取外部資料 (同盟資料存取) | 處理儲存在外部資料庫中的資訊，而不變更Adobe Campaign資料的結構。 [了解更多](../connect/fda.md) |
| 行銷活動最佳化 | 控制、篩選及監控傳遞，使訊息符合客戶需求和公司通訊原則。 [了解更多](../../automation/campaign-opt/campaign-typologies.md) |
| 傳遞能力監控（電子郵件傳遞能力） | 測量您的訊息是否可到達收件匣而不會退回或標示為垃圾訊息。 [了解更多](../send/monitoring-deliverability.md) |
| 優惠券管理 | 建立一組抵用券以新增至行銷優惠方案。 [了解更多](../send/personalized-coupons.md) |
| 收件匣轉譯 (IR) | 在可能接收訊息的內容中預覽訊息，並檢查與主要案頭和Web電子郵件使用者端的相容性。 [了解更多](../send/inbox-rendering.md) |
| 中央/地方行銷 (分散式行銷) | 實作中央實體（例如總部）與當地實體（例如銷售點）之間的合作行銷活動。 [了解更多](../../automation/distributed-marketing/about-distributed-marketing.md) |
| CRM 連接器 | 將Adobe Campaign連結至第三方CRM系統。 [了解更多](../connect/crm.md) |
| 網站分析連接器 | 允許Adobe Campaign和Adobe Analytics互動。 [了解更多](../connect/ac-aa.md) |
| AEM 整合 | 管理Adobe Experience Manager中的電子郵件和表單內容。 [了解更多](../connect/ac-aem.md) |
| Adobe Experience Cloud 共用客群整合 | 與[!DNL Adobe CX Enterprise] （先前稱為Adobe Experience Cloud）解決方案和應用程式交換和共用對象。 [了解更多](../start/shared-audiences.md) |
| 與Adobe Experience Cloud整合 | 從[!DNL Adobe CX Enterprise] （原為Adobe Experience Cloud）解決方案匯入和匯出對象至Adobe Campaign。 [了解更多](../connect/integration.md) |
| 隱私權資料保護法規 | 新增協助遵循隱私權規範的功能。 [了解更多](../start/privacy.md) |
| AMP 支援 | 使用互動式AMP傳送動態電子郵件以取得電子郵件格式。 [了解更多](../send/defining-interactive-content.md) |


>[!NOTE]
>
>行銷資源(MRM)、優惠券管理和線上調查套件不適用於企業(FFDA)部署的Campaign。 深入瞭解[功能可用性](../architecture/enterprise-deployment.md#feature-availability)。

## 相關主題 {#related-topics}

* [使用資料套件](../dev/packages.md)：建立、匯出和匯入您自己的自訂套件。
* [技術工作流程](../../automation/workflow/technical-workflows.md)：內建的技術工作流程以及安裝每個工作流程的套件。
* [FFDA部署中的功能可用性](enterprise-deployment.md#feature-availability)：企業(FFDA)部署中不可用的功能。
* [不支援的功能](../start/v7-to-v8.md#gs-removed)： v8中已不再支援Campaign Classic v7功能。
* [全域原則](general-architecture.md)：在Managed Cloud Services環境中可以和無法修改的專案。
* [開始使用Campaign v8](../start/get-started.md)：核心功能及附加元件的概觀。
