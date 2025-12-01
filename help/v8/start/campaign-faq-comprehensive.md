---
title: Campaign v8 常見問題
description: 取得有關設定、設定、傳訊、工作流程等常見Adobe Campaign v8問題的解答
feature: Overview
role: User
level: Beginner
keywords: 常見問題集， Campaign v8，問題，回答，說明，支援，疑難排解
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: 266facaaf2bd6bcce23db2bb5ab29f1c419bb3c1
workflow-type: tm+mt
source-wordcount: '12960'
ht-degree: 9%

---

# 常見問題集 {#faq}

取得Adobe Campaign v8常見問題的快速解答。 無論您是剛開始使用還是尋找進階設定說明，您都可以找到以下依主題整理的答案。

**Campaign新使用者？**&#x200B;以[一般問題](#general)和[重要概念](#key-concepts)開始。\
**需要技術協助嗎？**&#x200B;檢查[開發人員](#developers)和[行銷活動設定](#settings)。\
**找不到您的答案？**&#x200B;造訪我們的[社群論壇](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}或[連絡支援](#get-help)。

**提示：**&#x200B;使用Ctrl+F (Mac上的Cmd+F)在此頁面上搜尋特定關鍵字。 按一下任何問題以展開答案。


## 一般問題 {#general}

取得有關Adobe Campaign v8最常見問題的解答，包括如何連線、升級和取得支援。

+++ 如何連線至 Campaign v8？

您需要下載並安裝Campaign使用者端主控台，才能連線至Adobe Campaign。 [了解更多](connect.md)。

自Campaign v8.6發行版本開始，您可以透過中央Adobe Experience Cloud環境存取&#x200B;**Campaign網頁使用者介面**。 Experience Cloud是Adobe的整合式數位行銷應用程式產品和服務系列。

在此頁面[瞭解如何連線至Adobe Experience Cloud以及存取Adobe Campaign網頁介面](campaign-ui.md#ac-web-ui)。 在 [Adobe Campaign Web 使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}之中瞭解更多資訊。


**相關主題：**

[安裝使用者端主控台](connect.md) | [Campaign使用者介面](campaign-ui.md) | [使用者許可權](gs-permissions.md)

+++

+++ 如何改進電子郵件傳遞機制?

對於每個位寄件者的成功行銷方案，電子郵件傳遞能力是關鍵部分，必須具備不斷變化的標準及規則。 在這個數位世界中進行有效導覽，需要定期調整您的電子郵件策略，考量傳遞能力的重要趨勢，以便最能觸及您的客群。

請參閱本指南以瞭解[傳遞能力最佳實務](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}

在[本指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hant){target="_blank"}中，瞭解如何在 Campaign 中實施傳遞能力

**相關主題：**

[開始傳遞能力](../send/about-deliverability.md) | [控制訊息內容](../send/control-message-content.md) | [監視傳遞能力](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ 如何確定我是否成功傳遞，以及是否出現錯誤？

請依照下列步驟操作，以確保成功傳送：

傳送前&#x200B;**：**

* 執行傳遞分析以偵測錯誤（遺失個人化、無效的收件者、內容問題）
* 傳送測試校樣以驗證轉譯與個人化
* 準備期間檢閱警告
* 驗證目標母體計數

**傳送期間與傳送之後：**

* 監控傳送控制面板的即時統計資料（已傳送、已傳送、已退回、錯誤）
* 檢查訊息層級狀態的傳遞記錄
* 追蹤成功率、跳出率和錯誤訊息
* 檢閱隔離的地址

**最佳實務：**

* 設定錯誤臨界值的警示
* 對大型磁碟區使用波段（批次傳送）
* 先以小型磁碟區進行測試
* 定期清除您的收件者資料庫
* 監視寄件者信譽

深入瞭解[監視傳遞](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hant){target="_blank"}和[傳遞最佳實務](delivery-best-practices.md)。

+++

+++ 是否可以監視工作流程執行？

是。 Campaign提供數個工具來監視工作流程的執行：

* **[工作流程儀表板](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** — 檢視每個工作流程活動的即時狀態、進度和錯誤
* **[工作流程記錄檔](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** — 存取詳細的執行記錄檔以疑難排解問題
* **[熱度圖](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** — 視覺化工作流程活動並識別效能瓶頸
* **[稽核軌跡](../reporting/audit-trail.md)** — 追蹤對工作流程所做的所有修改
* **[警示](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** — 設定工作流程失敗或延遲的通知

若要監視工作流程，請開啟並按一下&#x200B;**記錄檔**&#x200B;索引標籤。 失敗的活動會以紅色反白顯示，您可以按一下它們來檢視錯誤詳細資訊。

深入瞭解[監視工作流程執行](https://experienceleague.adobe.com/zh-hant/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}和[工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target="_blank"}。

+++

+++ 如何下載Campaign？

您可以從 Adobe 下載中心取得安裝程式和用戶端主控台。

以管理員使用者身分，存取Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/tw/campaign.html){target="_blank"}以下載Adobe Campaign。

在此頁面[上進一步瞭解發佈中心](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hant){target="_blank"}。

+++

+++ 網域委派的程序為何？

子網域是您的網域分區，可用來隔離您的名稱或各類流量 (異動訊息、行銷資訊等等)。

>[!NOTE]
>
>請以 Managed Cloud Services 使用者身分，聯絡 Adobe 以委派您的子網域至 Adobe。

+++

+++ 如何記錄問題？

建立案例可讓您聯絡 Adobe 客戶支援團隊，瞭解您在 Adobe 產品上遇到的任何問題。為協助解決或疑難排解您的問題，您可使用 Adobe Admin Console 與 Adobe 客戶支援部門進行交談。

如要在該新系統中記錄問題或啟動聊天工作階段，請連結到 [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}。

此系統要求每個使用者都需要有新的個別帳戶，並擁有正確權限。 如果您發現無法使用 Adobe ID 登入，請透過 Experience League 請求存取權限，客戶服務團隊會盡快為您設定。[了解更多](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

加入 Campaign 社群：在現有問題中尋找答案或向專家提問。 [加入對話](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++

+++ 哪些系統和元件與 Campaign v8 相容？

在 [Adobe Campaign 相容性矩陣](compatibility-matrix.md)中，您可以取得 Campaign 最新建立支援的所有系統和組件清單。

+++

+++ 我可以將Campaign v8搭配其他Adobe解決方案搭配使用嗎？

是。 Campaign v8與Adobe Experience Cloud解決方案緊密整合，建立強大且統一的行銷生態系統。 作為Managed Cloud Service， v8專為與Adobe的企業應用程式原生整合而設計。

**可用的金鑰整合：**

* **Adobe Experience Platform** — 運用統一的客戶設定檔和即時資料
* **Adobe Analytics** — 測量各管道的行銷活動績效和客戶行為
* **Adobe Target** — 根據客戶區段和行為個人化內容
* **Adobe Experience Manager** — 集中內容建立和資產管理
* **Adobe Audience Manager** — 跨平台建置並啟用對象區段

**優點：**&#x200B;整合的客戶資料、一致的使用者體驗、簡化的工作流程，以及增強的個人化功能。

**設定：**&#x200B;與Adobe解決方案的整合需要Adobe Identity Management系統(IMS)驗證，此驗證會自動設定為Campaign v8受管理的Cloud Services。

**相關主題：**

[Adobe Campaign整合](../connect/integration.md) | [與Adobe ID連線](connect.md)

+++

+++ Campaign v8有哪些限制？

Campaign v8引進了架構變更（特別是FFDA部署），帶來顯著的效能改善，但也與Campaign Classic v7有些差異。 瞭解這些資訊有助於規劃移轉，並設定適當的期望。

**主要v8考量事項：**

* **FFDA架構** — 企業部署使用具有不同資料存取模式的雲端資料庫(Snowflake)
* **單位更新** — 資料更新應在工作流程中完成，而非透過API或直接資料庫存取
* **即時寫入** — 已針對批次作業（而非高頻個別更新）最佳化
* **資料模型** — 某些結構描述自訂需要不同的方法
* **外部資料庫存取** - FDA （同盟資料存取）組態與v7不同

**功能在FFDA部署中無法使用：**

* 調查（適用於標準v8部署）
* 行銷資源管理(RM)
* 某些特定的聯結器設定

**移轉考量事項：**

* 使用直接資料庫寫入的自訂程式碼需要重構
* API整合可能需要針對批次處理進行調整
* 工作流程應該遵循資料操作的FFDA最佳實務
* 測試對於驗證自訂開發至關重要

**重要：**&#x200B;這些限制會隨著Adobe持續增強v8而改變。 請參閱最新檔案，瞭解目前狀態和藍圖。

**相關主題：**

[Campaign v7移轉至v8](../start/v7-to-v8.md#limitations) | [FFDA架構](../architecture/enterprise-deployment.md)

+++

+++ 身為Campaign Classic v7使用者，我可以移轉至Campaign v8嗎？

無法從現有 Campaign Classic V7 環境進行自動移轉。

Campaign v8 目前&#x200B;**僅**&#x200B;以 Managed Cloud Service 的形式提供，不適用於內部部署或混合式環境。 

如需移轉流程的詳細資訊，請洽詢您的 Adobe 代表。

在[Campaign v8與舊版](#v7-differences)一節中瞭解更多。

+++

+++ 我的 Campaign 版本是什麼？

從 Campaign 用戶端主控台的 **Help > About...** 功能表檢查您的[版本和建立編號](upgrades.md#version)。

+++

+++ 如何將 Campaign 升級至最新版本？

定期更新 Adobe Campaign。每年都會推出次要版本，其中包含新功能、改進和修正。 此外，我們定期發行只累積修正的版本編號。

此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。這就是我們認為您需要執行最新 Adobe Campaign 版本的重要原因。

**注意：**&#x200B;作為Managed Cloud Services使用者，您的執行個體已由Adobe以新版本升級。

深入瞭解[行銷活動版本和升級](upgrades.md)。

+++

+++ 如何通知我新版本的發行？

透過以下管道掌握最新Campaign發行版本的最新資訊：

* **Adobe代表** — 在新版本可用時直接聯絡您
* **發行說明** - [Campaign發行說明](release-notes.md)中記錄的所有版本與變更
* **Adobe優先產品更新** - [訂閱](https://www.adobe.com/tw/subscription/priority-product-update.html){target="_blank"}電子郵件通知
* **Campaign社群** — 加入[討論](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}以取得早期更新

Adobe身為Managed Cloud Services使用者，會處理升級並協調與您相關的計時。

**相關主題：**

[發行說明](release-notes.md) | [新增功能](whats-new.md) | [行銷活動版本和升級](upgrades.md)

+++

+++ 我的組織為何需要升級？

升級至最新的Campaign版本對於安全性、效能和支援品質至關重要。

**主要優點：**

* **增強安全性** — 針對漏洞提供保護、最新修補程式、增強資料保護
* **更好的支援** — 更快的問題解決、存取錯誤修正、最新版本的優先支援
* **增強效能** — 資料庫和工作流程最佳化、更好的擴充性、更可靠的作業
* **新功能** — 最新功能、改善的Adobe Experience Cloud整合、現代化的UI增強功能

Adobe強烈建議執行最新版本。 身為受管理的Cloud Services客戶，升級是由Adobe以最低的中斷執行。

**相關主題：**

[行銷活動版本和升級](upgrades.md) | [新增功能](whats-new.md) | [相容性矩陣](compatibility-matrix.md)

+++

+++ 升級的流程和時間表為何？

作為受管理的Cloud Services客戶，Adobe會管理整個升級程式，並將對您作業的影響降到最低。

**處理序：**

1. **通知** - Adobe會提前幾週通知您
2. **規劃** — 與您的Adobe代表安排在最佳時間升級
3. **準備** - Adobe準備環境並驗證
4. **執行** - Adobe以最小的停機時間升級基礎結構
5. **驗證** - Adobe的升級後測試
6. **使用者端主控台升級** — 您升級使用者端主控台以符合伺服器版本

**您的職責：**

* 協調內部利害關係人的時間安排
* [將使用者端主控台](connect.md#upgrade-ac-console)升級為新版本
* 升級後測試行銷活動和工作流程
* 向Adobe支援報告問題

Adobe執行基礎架構升級。 您不需要在伺服器上執行任何技術動作。

**相關主題：**

[行銷活動版本和升級](upgrades.md) | [升級使用者端主控台](connect.md#upgrade-ac-console) | [發行說明](release-notes.md)

+++


## 重要概念 {#key-concepts}

瞭解基本Campaign概念，包括驗證、使用者介面、工作流程和核心功能，以便有效開始。

+++ 我可以使用Adobe ID連線至Campaign v8嗎？

是！ 與IMS (Adobe Identity Management系統)整合之後，使用者可以使用Adobe ID連線至Adobe Campaign主控台。 此整合具備以下優勢︰

* 所有 Experience Cloud 解決方案都可以使用相同的 ID。
* 使用不同整合中的 Adobe Campaign 時，可以記憶連線。
* 更安全的密碼管理原則。
* 使用 Federated ID 帳戶（外部 ID 提供者）。

[進一步瞭解](connect.md)如何使用Adobe ID存取Campaign v8。

+++

+++ 如何設定使用者權限?

作為 Campaign 管理者，您可以為組織使用者設定權限。

有一套權限或限制可授權或拒絕執行以下操作：

* 存取特定功能
* 存取特定資料
* 建立、修改和/或刪除資料

[進一步瞭解](../start/gs-permissions.md)Campaign v8中的使用者許可權。

**相關主題：**

[開始使用許可權](gs-permissions.md) | [管理使用者許可權](manage-permissions.md) | [新增資料夾許可權](folder-permissions.md)

+++

+++ 我應該了解哪些 Campaign 使用者介面概念?

請參閱[本節](campaign-ui.md)，深入瞭解Adobe Campaign使用者介面基本知識。

自Campaign v8.6發行版本開始，您也可以存取新的&#x200B;**Campaign網頁使用者介面**，此介面可透過中央Adobe Experience Cloud環境取得。

[在Adobe Campaign Web使用者介面檔案中進一步瞭解](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}。

+++

+++ 如何選取訊息的對象？

透過 Adobe Campaign，您可以使用不同策略來建立客群，並選取收件者。

[深入瞭解](../audiences/gs-audiences.md)如何在Campaign v8中定義對象。

+++

+++ 什麼是工作流程？

Adobe Campaign 的工作流程包含跨應用程式伺服器的不同模組策劃所有流程和任務。使用這個全方位的圖像式環境，您可以設計各式流程，包含細分、行銷活動執行、檔案處理、人力參與等。工作流程引擎將執行並追蹤這些流程。

例如，您可以使用工作流程從伺服器下載檔案、解壓縮，然後將其中的記錄匯入 Adobe Campaign 資料庫。

此外，工作流程也涉及到要進行通知的一或多個操作者，或者是可以選擇並核准流程的相關人員。如此一來，就可以在開始傳送前建立傳送動作、指派任務給一位或多位操作員來處理內容、指定目標以及核准校樣。

[進一步瞭解](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=zh-Hant){target="_blank"}工作流程。 您也可以閱讀[工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"}。

**相關主題：**

[開始使用工作流程](../config/workflows.md) | [建置您的第一個工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"} | [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [監視工作流程執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何建立並傳送第一封電子郵件？

在Campaign v8中建立您的第一封電子郵件涉及幾個關鍵步驟：

1. **建立傳遞** — 從範本或從頭開始建立新的電子郵件傳遞
1. **定義對象** — 使用查詢、清單或工作流程選取目標收件者
1. **設計內容** — 使用電子郵件設計工具來建立包含個人化的訊息
1. **使用校樣進行測試** — 傳送測試電子郵件以驗證內容及個人化
1. **分析並傳送** — 執行傳遞分析以檢查錯誤，然後傳送您的電子郵件

Campaign v8提供兩種建立電子郵件的介面：

* **使用者端主控台** — 具有進階功能的完整案頭應用程式
* **Campaign Web UI** — 新式、直覺式的網頁介面，可加快建立電子郵件的速度

[進一步瞭解Campaign v8中的電子郵件設計和驗證](../send/email.md)。

**相關主題：**

[建立您的第一個傳遞](create-message.md) | [使用傳遞範本](../send/create-templates.md) | [傳遞最佳實務](delivery-best-practices.md) | [定義電子郵件內容](../send/defining-the-email-content.md) | [預覽和校樣](../send/preview-and-proof.md) | [設定並傳送](../send/configure-and-send.md) | [個人化內容](../send/personalize.md)

+++

+++ 如何傳送 SMS 訊息？

使用Campaign v8傳送SMS訊息需要初始設定，然後遵循直接的傳送程式：

**初始設定（一次性設定）：**

1. **設定簡訊頻道** — 設定簡訊傳遞設定和外部帳戶
1. **設定SMPP連線** — 透過SMPP通訊協定連線到您的SMS服務提供者
1. **測試連線** — 驗證與您的SMS提供者的連線
1. **設定路由** — 定義透過您的提供者路由SMS訊息的方式

**建立和傳送簡訊：**

1. **建立簡訊傳遞** — 從範本開始新的簡訊傳遞
1. **定義收件者** — 使用電話號碼欄位選取您的行動對象
1. **撰寫簡訊內容** — 建立您的訊息（標準160個字元，或更長串連）
1. **新增個人化** — 包含每個收件者特有的動態欄位
1. **傳送校樣** — 測試SMS傳遞以驗證內容與傳遞
1. **分析並傳送** — 執行分析並傳送給您的對象

**重要簡訊功能：**

* **多個SMPP聯結器** — 支援各種SMS提供者和通訊協定
* **傳遞報告** — 追蹤已傳送、已傳遞及失敗的訊息
* **字元編碼** — 支援GSM7、Unicode和特殊字元
* **長簡訊支援** — 較長文字的自動訊息串連
* **雙向SMS** — 使用工作流程處理傳入的SMS回應

[進一步瞭解Campaign v8中的簡訊設定和傳送](../send/sms/sms.md)。

**相關主題：**

[開始使用簡訊](../send/sms/sms.md) | [簡訊傳遞設定](../send/sms/sms-delivery-settings.md) | [SMPP外部帳戶設定](../send/sms/smpp-external-account.md) | [建立SMS傳遞](../send/sms/create-sms.md) | [簡訊內容](../send/sms/sms-content.md) | [傳送SMS校樣](../send/sms/sms-proofs.md) | [監視SMS](../send/sms/sms-monitor.md)

+++

+++ 如何傳送推播通知？

使用Campaign v8傳送推播通知涉及設定行動應用程式整合及建立吸引人的通知：

**初始設定（一次性設定）：**

1. **設定推播頻道** — 在Campaign中設定推播通知頻道設定
1. **整合Campaign SDK** — 將Adobe Campaign SDK新增至您的行動應用程式（或使用資料收集）
1. **設定行動應用程式** — 在Campaign中註冊iOS和Android應用程式
1. **設定憑證** — 設定APNs憑證(iOS)和FCM金鑰(Android)
1. **測試註冊** — 確認裝置可以註冊及接收權杖

**建立和傳送推播通知：**

1. **建立推播傳遞** — 從範本開始新的推播通知
1. **選取平台** — 選擇iOS、Android或兩者皆選
1. **定義對象** — 使用行動應用程式訂閱資料的目標應用程式訂閱者
1. **設計通知** — 建立標題、訊息和多媒體內容
1. **設定行為** — 設定點選動作、深層連結和自訂資料
1. **傳送測試通知** — 在傳送之前在真實裝置上進行驗證
1. **分析並傳送** — 檢閱目標定位並傳送給您的行動裝置對象

**推播通知功能：**

* **豐富推送通知** — 包含影像、影片和互動式按鈕(iOS和Android)
* **Personalization** — 根據使用者設定檔和行為的動態內容
* **深層連結** — 將使用者導向至特定應用程式畫面或內容
* **排程** — 根據使用者時區以最佳時間傳送
* **A/B測試** — 測試不同的訊息並最佳化參與
* **追蹤** — 監視開啟、點按和轉換

**平台特定功能：**

* **iOS** — 無訊息通知、通知類別、聲音自訂
* **Android** — 豐富推送範本、通知頻道、自訂配置

[進一步瞭解Campaign v8中的推播通知設定](../send/push-settings.md)。

**相關主題：**

[建立並傳送推播通知](../send/push.md) | [設定推播通知頻道](../send/push-settings.md) | [設計Android豐富推送](../send/rich-push-android.md) | [設計iOS豐富推送功能](../send/rich-push-ios.md) | [設定資料彙集](../send/push-data-collection.md) | [追蹤和監視](tracking.md)

+++

+++ 如何建立登陸頁面？

您可以使用Adobe Campaign數位內容編輯器來設計登入頁面，並定義與資料庫欄位的對應。

[在Campaign v8檔案中瞭解更多](../dev/landing-pages.md)。

您也可以使用Campaign網頁使用者介面來建立和發佈登入頁面 — [深入瞭解](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}。

+++

+++ 如何追蹤傳送內容？

您可以透過專用的[傳遞報告](../reporting/delivery-reports.md)追蹤與Campaign v8一起傳送的傳遞，然後監視您的傳遞。

在此頁面[中進一步瞭解Campaign &#x200B;](../start/tracking.md)中的追蹤管理。

**相關主題：**

[追蹤及監視訊息](tracking.md) | [傳遞報告](../reporting/delivery-reports.md) | [瞭解傳遞失敗](../send/delivery-failures.md) | [設定追蹤的連結](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ 如何翻譯錯誤訊息？

出現了以外文顯示的錯誤訊息？[本頁面](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant){target="_blank"}列出所有錯誤訊息及其翻譯。

+++

+++ 我可以在 Campaign 中製作網路表單和收集解答嗎？

是。 使用&#x200B;**Campaign Web Applications &amp; Forms** （使用者端主控台）建立網路表單，以完整控制表單邏輯和驗證，或使用&#x200B;**Campaign登陸頁面** (Web UI)，搭配現代化的拖放介面以進行訂閱和潛在客戶產生。 兩者都會直接將資料收集到Campaign中，並整合自動化動作的工作流程。

**相關主題：**

[進一步瞭解Web應用程式和表單](../dev/webapps.md) | [Campaign Web UI登陸頁面](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8與舊版 {#v7-differences}

瞭解Campaign v8與舊版（Classic v7和Standard）之間的主要差異，包括架構、部署、移轉路徑和功能變更。 無論您是來自Campaign Classic v7還是Campaign Standard，瞭解新增功能以及如何順暢地轉換。

+++ Campaign v8是否可安裝在內部部署或混合環境中？

沒有。Campaign v8是以&#x200B;**受管理的Cloud Service**&#x200B;獨家提供，並完全由Adobe代管。

**Managed Cloud Services的主要優點：**

* 卓越的效能與擴充能力
* 自動升級 — 一律使用最新版本
* 透過持續監控增強安全性
* 沒有基礎建設管理或IT負荷
* 內建的高可用性與災難回覆

深入瞭解[Campaign v8架構](../architecture/architecture.md)以及Campaign v8與Classic v7[之間的](../start/v7-to-v8.md)差異。

+++

+++ Campaign v8和舊版之間有何主要差異？

Campaign v8建置在現代雲端原生架構上，並大幅改善：

* **僅限Managed Cloud Services** — 完全由Adobe代管（無內部部署/混合選項）
* **卓越的效能** — 高達20,000,000作業/小時，搭配完整同盟資料存取(FFDA)架構
* **全新Campaign Web UI** — 現代的直覺式介面與傳統主控台
* **自動升級** — 一律使用最新版本，停機時間為零
* **增強功能** - AI助理、豐富推播通知、升級簡訊、改善與Adobe Experience Cloud的整合

**若為Campaign Classic v7使用者：**&#x200B;瞭解[從v7轉變到v8](v7-to-v8.md)，包括架構變更、功能無法使用及移轉考量事項。

**若為Campaign Standard使用者：**&#x200B;探索[到v8](acs-to-v8.md)和[Campaign Standard移轉指南](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"}的轉換路徑。

**相關主題：**

[Campaign v8主要功能](whats-new.md) | [Campaign v8架構](../architecture/architecture.md) | [功能矩陣](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [護欄和限制](ac-guardrails.md)

+++

+++ 我應該從Campaign Classic v7或Campaign Standard移轉至v8嗎？

**Campaign v8適用於需要：**&#x200B;的組織

* **大量行銷活動** — 以改進的效能和可靠性（每小時2000萬次作業）傳送數百萬封訊息
* **企業擴充能力** — 提升資料庫與行銷活動，避免效能問題
* **新式網頁使用者介面** — 直覺式回應式Campaign網頁UI，可加快行銷活動建立速度並改善使用者體驗
* **雲端原生優點** — 運用自動更新、受管理基礎結構、彈性擴充和主動監控
* **長期支援** - Campaign v8是Adobe的策略平台，並具備延伸支援，而舊版將在未來幾年內終止支援
* **降低IT負荷** — 消除基礎建設管理與升級規劃
* **進階功能** - AI小幫手、豐富推播、增強型SMS、Adobe Experience Platform整合

Campaign Standard使用者的&#x200B;**：**

Campaign Standard使用者現在有資格轉換至Campaign v8受管理的雲端服務。 主要優點包括：

* **熟悉的介面** - Campaign網頁UI與Campaign Standard有許多相似之處，可儘量減少學習曲線
* **同位功能** — 重要Campaign Standard功能已新增至v8 （動態報告、集中式品牌、REST API、登陸頁面、視覺片段）
* **增強型支援** — 最先進的協助功能，提供順暢的轉換與持續的平台監控
* **資料移轉** — 您從Campaign Standard匯入的所有資料中斷最少
* **一致的使用者體驗** — 繼續使用熟悉的工作流程和介面

**若為Campaign Classic v7使用者：**

Campaign v8在維持核心Campaign功能的同時，也提供大幅改善：

* **雙介面** — 存取功能強大的使用者端主控台和現代的Campaign Web UI
* **更好的效能** — 大幅改善查詢效能和資料處理
* **雲端優勢** — 由Adobe管理的自動升級、安全性修補程式、備份/復原
* **現代架構** — 增強型FFDA架構搭配PostgreSQL，提供更優異的擴充能力

**何時考慮移轉：**

* 您目前的Campaign執行個體會處理大量資料（數百萬個設定檔）
* 您遇到複雜工作流程或定位的效能問題
* 您想要降低基礎建設管理與維護成本
* 您需要與Adobe Experience Cloud或Adobe Experience Platform緊密整合
* 您正計畫進行重大升級或重新整理基礎結構
* **您想要防患於未然的技術** — 支援即將終止舊版
* **您的團隊需要現代化的介面** - Campaign網頁UI為行銷人員提供更好的協助工具

**移轉考量事項：**

* Adobe提供移轉支援、指引和工具
* v8僅限Managed Cloud Service （無內部部署或混合部署）
* 某些技術實作可能有所不同 — 檢閱[功能矩陣](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* 資料移轉和測試需要規劃和資源
* **適用於Campaign Standard使用者** — 轉換過程設計得流暢，且工作流程中斷最少

**後續步驟：**

請聯絡您的Adobe代表以：

* 評估您的移轉準備程度與時間表
* 瞭解使用案例的特定優點
* 規劃移轉策略與資源配置
* 存取移轉工具和支援

**相關主題：**

**Campaign Classic v7使用者：** [從Campaign Classic v7到v8](v7-to-v8.md) | [v7到v8詳細指南](https://experienceleague.adobe.com/zh-hant/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Campaign Standard使用者：** [Campaign Standard轉換至v8](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8採用指南](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/acs-to-ac/home){target="_blank"} | [從Campaign Standard到v8總覽](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [行銷人員快速入門](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [管理員/開發人員快速入門](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**一般資源：** [Campaign v8功能矩陣](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [相容性矩陣](compatibility-matrix.md)

+++

+++ 如何將我的Campaign Classic v7內部部署或混合環境移轉至Adobe Managed Services？

移轉至Adobe Managed Services提供從內部部署/混合v7到雲端的策略途徑，可改善擴充性、安全性並降低IT負荷。 在轉換至Campaign v8之前，這通常是踏腳石。

**關鍵點：**

* 沒有可用的自動化移轉工具 — 需要手動規劃和執行
* 強烈建議Adobe Professional Services支援
* 優點包括雲端基礎建設、自動安全性修補程式、專家支援，以及更輕鬆的v8存取途徑
* 移轉涉及盡職調查、環境稽核、資料清理、中繼移轉和生產轉換

**快速入門：**&#x200B;請聯絡您的Adobe代表，評估您的環境並透過Adobe Professional Services制定詳細的移轉計畫。

深入瞭解[移轉至Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"}，包括挑戰、最佳實務和詳細的移轉藍圖。

+++

+++ Campaign v8的主要術語和功能差異為何？

Campaign v8強化了大部分的Campaign Classic v7和Campaign Standard功能，但部分功能會因雲端原生架構而有所變更，部分術語也會因版本而異。

**術語差異(Campaign Standard到v8)：**

* **自訂資源**&#x200B;現在是&#x200B;**結構描述**
* **訊息**&#x200B;稱為&#x200B;**傳遞**
* **產品使用者**&#x200B;現在是&#x200B;**操作員**
* **角色**&#x200B;設定了&#x200B;**已命名的許可權**
* **安全性群組**&#x200B;現在是&#x200B;**運運算元群組**
* **組織單位**&#x200B;是透過&#x200B;**資料夾許可權**&#x200B;管理的

**Campaign Web UI術語更新：**

Campaign Web UI中更新下列詞語（使用者端主控台使用傳統詞語）：

* **收件者**&#x200B;現在是&#x200B;**設定檔**
* **種子地址**&#x200B;現在是&#x200B;**測試設定檔**
* **傳遞分析**&#x200B;現在是&#x200B;**傳遞準備** （按一下&#x200B;**準備**&#x200B;按鈕）
* **電子郵件預覽**&#x200B;可透過&#x200B;**模擬內容**&#x200B;按鈕使用
* **清單**&#x200B;現在是&#x200B;**對象**

**在v8中無法使用：**

* **內部部署和混合式部署** - v8僅限Managed Cloud Services
* **直接資料庫存取** — 改用提供的API和工具
* **客戶管理基礎架構** - Adobe管理所有基礎架構
* **手動建置升級** — 現在為自動(Adobe管理)

**v8中的不同實作：**

* **技術工作流程** — 某些針對雲端架構最佳化的工作流程可能會有不同的運作方式
* **資料庫結構** — 增強型FFDA架構可能需要結構描述調整
* **自訂整合** — 可能需要更新雲端架構
* **低階自訂** — 有些在受管理的環境中需要不同的方法

**在v8中增強或取代：**

* **建置升級** — 使用持續傳遞模式自動而非手動
* **效能調整** — 由Adobe基礎架構最佳化處理
* **安全性修補程式** — 由Adobe自動套用
* **備份與復原** — 由Adobe管理，作為服務的一部分
* **使用者介面** — 新的Campaign Web UI和使用者端主控台

**為Campaign Standard使用者新增的功能正在轉換至v8：**

* **動態報告** — 可自訂的即時報告，包含人口統計分析
* **集中式品牌** — 定義品牌視覺化與技術准則
* **REST API** — 建立整合併建立您的生態系統
* **登陸頁面改善** — 加強與Campaign Standard的功能同位性
* **視覺片段** — 可重複使用的電子郵件和內容範本視覺元件

**重要：**&#x200B;大部分的行銷與營運功能在v8中皆已推出並改善。 Adobe在雲端環境中管理技術和基礎架構層級功能。

**相關主題：**

[功能矩陣](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [相容性矩陣](compatibility-matrix.md) | [護欄和限制](ac-guardrails.md) | [v7到v8轉換指南](v7-to-v8.md)

[Campaign Standard到v8的轉換](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## 輪廓與客群 {#audiences}

尋找管理設定檔、建立對象、匯入資料，以及定位行銷活動收件者的相關問題解答。

+++ 如何建立收件者？

在個別設定檔的使用者端主控台中手動建立收件者、從檔案(CSV/TXT)匯入以進行大量新增、使用網路表單進行自我註冊，或透過外部系統的API進行整合。 使用匯入工作流程進行週期性資料載入。

**相關主題：**

[手動建立設定檔](../audiences/create-profiles.md) | [從檔案匯入設定檔](../audiences/import-profiles.md) | [使用網路表單收集設定檔](../audiences/collect-profiles.md)

+++

+++ 如何匯入用戶檔案？

Campaign提供多種匯入方法：使用匯入精靈匯入簡單的檔案、針對複雜轉換以工作流程為基礎的匯入、利用來自SFTP的排程工作流程重複匯入，以及用於程式設計整合的API匯入。

針對檔案匯入，準備您的資料檔案（CSV/TXT、UTF-8編碼）、使用匯入精靈或工作流程、將欄對應到Campaign欄位、定義更新/插入規則，以及先以小型範例進行測試。 使用工作流程進行週期性匯入，並套用重複資料刪除規則。

**相關主題：**

[匯入資料指南](../start/import.md) | [週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hant){target="_blank"} | [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何定義行銷宣傳活動的目標母體？

Campaign提供多種鎖定目標方法：使用視覺條件建立查詢、鎖定現有清單或區段、從外部檔案(CSV、TXT)匯入收件者，或套用預先定義的篩選器。 您可以將條件與AND/OR邏輯結合、排除特定母體、使用控制組，以及分割A/B測試。 傳送前，請一律預覽目標母體大小。

[定義行銷活動目標](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant){target="_blank"} | [查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"} | [建立對象](../audiences/create-audiences.md)

+++

+++ 如何建立用戶檔案清單？

清單是一組靜態的收件者名單，您可以在傳送時加以定位，並在行銷活動中重複使用。

**三種建立方法：**

* **手動建立：**&#x200B;瀏覽至&#x200B;**[!UICONTROL Profiles and Targets > Lists]**&#x200B;並按一下&#x200B;**[!UICONTROL Create]**。 從查詢、依個別選取專案或資料夾新增收件者。

* **工作流程自動化：**&#x200B;使用&#x200B;**[!UICONTROL List update]**&#x200B;活動自動從查詢結果或匯入的資料建立及維護清單。

* **匯入期間：**&#x200B;匯入設定檔時，請建立清單，以將設定檔儲存為可重複使用的群組。

**秘訣：**&#x200B;對於需要定期更新的清單，請使用工作流程，並手動建立單次分段。

**相關主題：**

[建立對象](../audiences/create-audiences.md) | [清單更新活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何在傳送訊息前排除重複的母體？

在工作流程中使用&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動，在傳遞前移除重複的收件者。 將其置於您的&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Delivery]**&#x200B;活動之間，然後選擇您的重複資料刪除條件（通常是電子郵件地址或收件者ID）以及要保留的記錄。

**秘訣：**&#x200B;傳送訊息前請一律刪除重複專案，確保每個人只收到一次您的訊息。

深入瞭解[重複資料刪除活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何識別和鎖定新聞稿的訂閱者？

Campaign透過資訊服務自動追蹤電子報訂閱。 若要鎖定訂閱者：

* 使用&#x200B;**[!UICONTROL Query]**&#x200B;活動並篩選&#x200B;**[!UICONTROL Subscriptions]** >選取您的Newsletter服務
* 選擇&#x200B;**[!UICONTROL To > Subscribers of an information service]**，直接從您的傳遞鎖定訂閱者
* 使用&#x200B;**[!UICONTROL Subscription Services]**&#x200B;工作流程活動建立訂閱者清單

Campaign會追蹤訂閱/取消訂閱歷程記錄，並自動管理選擇加入/選擇退出。

**相關主題：**

[管理訂閱](../start/subscriptions.md) | [查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"}

+++

+++ 從目標母體中排除用戶檔案的最佳做法是什麼？

在工作流程中使用&#x200B;**[!UICONTROL Exclusion]**&#x200B;活動，從目標中移除不要的設定檔。 將其放在目標定位活動之後，並定義要排除的母體。

深入瞭解[排除活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=zh-Hant){target="_blank"}

+++

+++ 我可以在Campaign中使用外部設定檔而不匯入它們嗎？

可以，Campaign v8可讓您使用儲存在外部資料庫中的外部設定檔，而不需將其載入到Adobe Campaign中。 [了解更多](../audiences/external-profiles.md)。

+++

+++ 如何建立傳送的測試設定檔？

測試設定檔是特殊的收件者，用來傳送校樣及驗證傳遞，而不會影響您的生產資料庫。 在&#x200B;**[!UICONTROL Profiles and Targets > Test profiles]**&#x200B;中建立這些收件者，或使用&#x200B;**[!UICONTROL Seed addresses]**&#x200B;功能自動將測試收件者新增至您的傳遞，以進行品質保證和收件匣監視。

深入瞭解[測試設定檔](../audiences/test-profiles.md)

+++

## 訊息設計 {#design}

瞭解如何在Campaign v8中設計有效的行銷訊息，包括電子郵件範本、個人化技巧和多語言內容。 在使用者端主控台中設計您的訊息，或在Campaign網頁UI中使用現代的&#x200B;**電子郵件Designer**，以獲得增強的視覺編輯體驗。

+++ 在Campaign中設計電子郵件的最佳實務是什麼？

重要准則：確保行動裝置回應式設計、使用與內嵌CSS相容的HTML 4.0/XHTML程式碼、使用替代文字最佳化影像（100KB以下）、使用個人化合併欄位、在傳送前跨電子郵件使用者端測試，以及包含純文字版本。 將總電子郵件大小調整為500KB以下以獲得最佳傳遞能力。

[電子郵件設計手冊](../send/email.md) | [傳遞最佳實務](delivery-best-practices.md)

+++

+++ 什麼是傳遞範本？

傳遞範本是預先設定的傳遞，可儲存所有設定和引數以供多個行銷活動重複使用。 範本包括目標規則、內容設計、個人化、技術設定（寄件者、回覆）和型別規則。 建立一次並重複使用，以維持一致性並加快行銷活動的建立。

瞭解如何[建立傳遞範本](../send/create-templates.md)

+++

+++ 在 Campaign 中可以輕鬆地匯入現有的 HTML 並製作電子郵件嗎?

是。 透過直接複製/貼上將HTML內容匯入內容編輯器、從電腦上傳檔案或從URL載入。 確認您的HTML使用與電子郵件相容的程式碼(HTML 4.0/XHTML)搭配內嵌CSS，並在公用伺服器上託管影像。 Campaign會自動新增個人化和追蹤至匯入的HTML。

**秘訣：**&#x200B;若要獲得最佳的電子郵件設計體驗，請在Campaign網頁UI中使用&#x200B;**電子郵件Designer**，它提供現代拖放功能和內建回應式範本，而不是匯入原始的HTML。

瞭解如何[匯入HTML內容](../send/defining-the-email-content.md)

+++

+++ 如何在 Campaign 中建立訂閱式新聞稿？

是。 使用Campaign的資訊服務來管理新聞稿訂閱。 主要功能包括自動選擇加入/選擇退出處理、訂閱追蹤、合規性管理(GDPR、CAN-SPAM)、多電子報支援、登錄檔單的Web整合，以及針對訂閱者的傳送作業。

瞭解如何[管理訂閱](../start/subscriptions.md)

+++

+++ 如何個人化訊息？

Campaign提供個人化功能，根據收件者資料、行為和偏好設定來建立相關的鎖定目標訊息。

**Personalization選項：**

* **個人化欄位** — 插入收件者資料(例如，`"Hello {{firstName}}")`
* **個人化區塊** — 使用預先定義或自訂的內容區塊
* **條件式內容** — 根據收件者條件顯示不同的內容
* **行為資料** — 運用瀏覽記錄、購買模式或參與量度

在傳送前測試個人化，以驗證合併欄位和條件邏輯是否正確運作。

**相關主題：**

[Personalization指南](../send/personalize.md) | [個人化欄位](../send/personalization-fields.md) | [條件式內容](../send/conditions.md)

+++

+++ 我可以傳送多國語言的訊息嗎？

是。 Campaign v8提供多語言功能，而&#x200B;**Campaign網頁UI**&#x200B;提供最簡單的方法。 Web UI提供具有語言變體的原生多語言傳送，可將語言變體新增至您的傳送中，且Campaign會根據收件者偏好的語言自動傳送適當版本。 可用於電子郵件、推播通知、簡訊與交易式訊息。

主要功能：自動內容複製、自動語言傳送、預設語言後援及簡易的變體管理。

使用者端主控台也支援使用條件式內容和工作流程的多語言內容，但需要更多手動設定。

[多語言傳送(Web UI)](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [條件式內容（使用者端主控台）](../send/conditions.md)

+++

+++ 可以將網頁表單當地語系化嗎？

是。 Campaign網頁應用程式支援多語言本地化。 定義所有表單元素（標籤、按鈕、訊息、錯誤文字）的翻譯，並根據收件者設定檔或瀏覽器設定自動偵測語言。 單一Web應用程式支援多種語言版本，必要時可遞補為預設語言。

深入瞭解[網頁應用程式本地化](../dev/webapps.md)

+++

+++ 我可以在電子郵件中使用AI支援的內容嗎？

是，但&#x200B;**只能透過Campaign Web UI**。 由Microsoft Azure OpenAI和Adobe Firefly提供支援的AI小幫手，可跨電子郵件、簡訊和推播通知建立專業且品牌一致的內容。

**主要功能：**

* 產生文字（電子郵件復本、主旨列、簡訊/推播內容）與品牌一致的影像
* 建立針對不同受眾最佳化的內容變數
* 精簡內容（精緻、摘要、改寫、簡化）
* 上傳品牌資產並取得品牌一致性分數
* 使用現有內容作為參考和上傳樣式參考影像

**注意：** AI助理只能在Campaign Web UI中使用，目前僅支援英文。 使用者需要適當的許可權，而且必須同意使用者協定。

[AI助理概述](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI助理使用案例](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [品牌一致性](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 測試和傳送訊息 {#send}

瞭解測試、驗證、傳送和追蹤行銷訊息的最佳實務，以確保成功傳遞行銷活動。

+++ 什麼是傳遞分析？

傳遞分析是Campaign在傳送前執行的驗證階段。 它會計算目標母體、驗證內容、檢查錯誤、套用型別規則，以及估計傳遞量。

Campaign產生顯示警告和錯誤的記錄。 錯誤會封鎖傳送，且必須修正；警告為建議。 傳送前，請務必檢閱分析記錄。

進一步瞭解[傳遞分析指南](../send/delivery-analysis.md)

+++

+++ 為何要建立測試？

校樣是測試訊息，可在傳送給主要受眾之前驗證您的傳送內容。 使用校樣來驗證個人化、測試電子郵件使用者端間的內容轉譯、確認連結和追蹤工作、檢查影像和附件，以及驗證行動回應。

校訂有助於在錯誤觸及數千個收件者之前鎖定錯誤、啟用利害關係人核准並測試收件匣位置。 將校樣傳送至多個電子郵件使用者端和裝置，並一律在生產傳送前取得核准。

進一步瞭解[校訂和預覽指南](../send/preview-and-proof.md)

+++

+++ 如何在 Adobe Campaign 中使用種子地址？

種子地址是特殊收件者，會自動新增至每次傳遞，以進行測試、品質保證和監控，不符合您的目標條件。 適合用於持續監控、收件匣位置測試、直接郵件驗證和利害關係人可見度。

**與校訂的主要差異：**

* **種子地址** — 自動新增到生產傳遞，計入傳送量
* **校訂** — 測試會在生產前傳送，不會計入磁碟區，用於驗證

管理&#x200B;**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;中的種子地址。 保持小清單以避免影響傳遞量度。

[種子地址指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何設定傳送訊息前的驗證過程？

Campaign提供核准工作流程，以確保訊息在傳送前符合品質標準。 在行銷活動或傳遞層級設定內容、目標、擷取（直接郵件）和預算的核准。

**安裝程式：**

在&#x200B;**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;中建立操作員群組，然後在行銷活動或傳遞屬性中指派核准群組。 Campaign會傳送通知電子郵件給可核准、拒絕或要求變更的稽核者。

**對於獨立傳送（不在行銷活動中）：**

使用&#x200B;**校訂作為您的核准程式**。 將校訂傳送至您的核准組進行驗證，並進行變更後一律傳送新校訂，以確保利害關係人檢閱最新版本。

**相關主題：**

[傳遞驗證](../send/preview-and-proof.md) | [行銷活動核准](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hant){target="_blank"}

+++

+++ 什麼是類型規則？

型別規則是在傳遞分析期間套用的自動化商業邏輯，以驗證和最佳化訊息傳送。 它們可確保遵守行銷政策、保護傳遞能力並防止客戶疲勞。

**主要規則型別：**

* **篩選規則** — 排除收件者（已加入封鎖名單、已取消訂閱、已隔離）
* **壓力規則** — 控制訊息頻率以避免收件者過多
* **容量規則** — 限制處理容量或ISP限制的訊息量
* **控制規則** — 檢查郵件有效性（主旨列、取消訂閱連結、寄件者格式）

規則會分組為型別，並在傳遞分析期間套用。 Campaign可以根據規則排除收件者、封鎖傳遞或產生警告。

[型別規則指南](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何分批次傳送電子郵件？

是。 波次傳送會將您的傳遞分割為多個批次，以排程間隔傳送。 這對於大型行銷活動至關重要，這些活動可以平衡伺服器負載、防止ISP節流、使用新IP建立寄件者信譽和管理波段之間的選擇退出/跳出。

**組態：**

在您的傳遞屬性中，啟用波段傳送並定義波段數（或批次大小）、波段之間的間隔和波段分佈（線性或自訂百分比）。 Campaign會自動劃分目標母體，並按照排程傳送每個波段。

波段用於大型行銷活動，在繼續之前監視第一個波段績效，並在波段之間留出足夠的時間來處理退信和選擇退出。

瞭解如何[設定波動傳送](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ 在 Campaign 中建立電子郵件有哪些重要步驟？

在Campaign v8中建立電子郵件涉及以下重要步驟：建立傳遞、定義目標對象、設計內容、新增個人化、設定設定（寄件者、主旨、回覆）、執行傳遞分析、傳送要測試的校樣，以及最後傳送或排程。

**關鍵步驟：**

1. **建立傳遞** — 選擇電子郵件作為通道，並選擇性地選取傳遞範本
1. **定義目標** — 使用查詢、清單或匯入的檔案來選取您的收件者對象
1. **設計內容** — 使用電子郵件編輯器(網頁使用者介面電子郵件Designer或使用者端主控台編輯器)建立您的訊息
1. **新增個人化** — 插入動態欄位、個人化區塊和條件式內容
1. **設定設定** — 設定寄件者地址、主旨列、回覆及傳遞引數
1. **執行傳遞分析** - Campaign會驗證內容、計算目標並檢查錯誤
1. **傳送校樣** — 使用核准群組測試您的電子郵件，以驗證轉譯與內容
1. **傳送或排程** — 立即傳送至主要目標或排程，以供日後使用

**兩個介面選項：**

* **Campaign Web UI** — 現代介面，具有增強的電子郵件Designer、AI助理和多語言功能
* **使用者端主控台** — 具有進階目標定位和工作流程功能的傳統介面

**秘訣：**&#x200B;使用Campaign網頁UI，透過現代設計工具更快速、更直覺地建立電子郵件。 使用使用者端主控台進行複雜的目標定位或進階的工作流程型行銷活動。

**相關主題：**

[建立您的第一封電子郵件](create-message.md) | [電子郵件設計手冊](../send/email.md)

+++

+++ 如何排程傳遞？

Campaign可讓您排程傳送以利未來傳送，最佳化傳送時間並協調行銷活動。

**排程選項：**

* **傳遞屬性** — 立即傳送、排程為特定日期/時間，或依時數/天遞延
* **行銷活動層級** — 協調行銷活動內的所有傳遞
* **工作流程排程器活動** — 適用於週期性傳遞、複雜模式和事件觸發的行銷活動

Campaign也支援聯絡日期最佳化（每個收件者的最佳傳送時間）和時區調整（所有收件者的相同當地時間）。

瞭解如何[排程傳遞傳送](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ 我可以將附件新增至電子郵件嗎？

是。 Campaign支援靜態附件（所有收件者的相同檔案）和個人化附件（根據設定檔資料，每個收件者的不同檔案）。 在傳遞屬性的&#x200B;**[!UICONTROL Attachments]**&#x200B;區段中新增附件。

**重要考量：**

* 將附件保持在1MB以下，以獲得最佳傳遞能力
* 附件可能會觸發垃圾郵件篩選器；請在傳送前進行徹底測試
* 避免電子郵件使用者端(.exe、.zip、.js)通常會封鎖的檔案型別
* 若為大型檔案，請考慮改用追蹤的下載連結

使用安全的檔案格式(PDF、JPEG、PNG、DOCX)並在生產傳送之前使用種子地址進行測試。

進一步瞭解[電子郵件附件指南](../send/email.md#attachments)

+++

+++ 如何在電子郵件傳送中設定追蹤連結？

Campaign會自動將電子郵件中的所有URL轉換為追蹤連結，以監視收件者參與情形。 存取傳遞中的&#x200B;**[!UICONTROL Tracking]**&#x200B;區段以設定每個連結的追蹤設定。

**組態選項：**

* **啟用/停用追蹤** — 每個連結的控制追蹤
* **連結標籤** — 新增描述性的報表名稱(例如「立即購買CTA」)
* **連結類別** — 依彙總分析型別將連結分組
* **追蹤型別** — 追蹤點按次數、開啟次數或兩者

Campaign會追蹤內容連結、映象頁面連結、取消訂閱連結，並可包含電子郵件開啟次數的可選追蹤畫素。 使用有意義的標籤和類別來簡化報表，並快速找出高效能的內容。

**相關主題：**

[連結追蹤指南](../start/tracking.md) | [追蹤最佳實務](../send/send.md)

+++

+++ 我可以在哪裡存取傳送內容和追蹤記錄？

直接從每個傳遞控制面板存取傳遞和追蹤記錄。 在使用者端主控台中，按一下底部的&#x200B;**[!UICONTROL Delivery]**&#x200B;標籤。 在Campaign Web UI中，導覽至&#x200B;**[!UICONTROL Logs]**&#x200B;區段。

**可用記錄：**

* **傳遞記錄** — 已傳送包含收件者詳細資料和狀態的訊息（已傳送、擱置中、失敗）
* **追蹤記錄** — 具有時間戳記的收件者互動（開啟、點按）
* **排除記錄檔** — 排除的收件者有理由（隔離、型別規則、重複專案）
* **廣播記錄** — 完成傳送歷程記錄，包括重試和錯誤

使用這些記錄來疑難排解傳送問題、分析參與及維護清單衛生。

**相關主題：**

[傳遞監視](../send/send.md) | [追蹤指南](../start/tracking.md)

+++

+++ 我在哪裡可以取得傳遞報告？

Campaign提供完整的內建報告，以分析傳遞成效、收件者參與度和行銷活動有效性。 從任何傳遞中的&#x200B;**[!UICONTROL Reports]**&#x200B;標籤、行銷活動儀表板或跨行銷活動分析的全域&#x200B;**[!UICONTROL Reports]**&#x200B;功能表存取報告。

**主要報表包括：**

* **傳遞摘要** — 傳送統計資料、開啟、點按、退信和取消訂閱
* **熱門點按** — 連結效能的視覺化熱度圖
* **追蹤指標** — 點進率和參與量度
* **無法傳遞的專案** — 含有失敗原因的退回分析

報表可用於具有現代化視覺效果的使用者端主控台和Campaign Web UI。

**相關主題：**

[內建傳遞報告](../reporting/delivery-reports.md) | [行銷活動報告](../reporting/gs-reporting.md)

+++

+++ Adobe Campaign如何確定和管理隔離地址？

Campaign會自動管理隔離清單，以保護您的寄件者信譽並改善傳遞能力。 隔離的地址會自動從未來的傳送中排除，直到驗證它們或從隔離中移除為止。

**隔離地址的原因：**

* **硬退信** — 永久傳遞失敗（無效的電子郵件地址、網域不存在、已刪除信箱）
* **軟退信閾值** — 重複的暫時失敗（信箱已滿，伺服器暫時無法使用）超過錯誤閾值
* **垃圾郵件投訴** — 將您的電子郵件標示為垃圾郵件的收件者
* **無效的位址** — 有語法錯誤或驗證失敗的位址
* **已加入封鎖清單** — 選擇退出或要求排除的收件者

**隔離的運作方式：**

Campaign會追蹤每個地址的傳送錯誤。 當位址達到設定的錯誤臨界值時，就會在分析期間自動將其隔離並排除在所有未來的傳送中。 硬退信（永久失敗）會立即隔離，而軟退信則在隔離前需要多次失敗。

**管理隔離的地址：**

**[!UICONTROL Administration > Campaign Management > Non deliverables Management]**&#x200B;中的存取隔離管理。 您可以檢視隔離的地址、從隔離中手動移除已驗證的地址，或設定自動清理規則。

**秘訣：**&#x200B;定期監視隔離清單。 提高隔離率通常表示資料品質問題在影響寄件者信譽之前需要注意。

**相關主題：**

[隔離管理指南](../send/quarantines.md) | [退回管理](../send/delivery-failures.md)

+++

## 工作流程 {#workflows}

探索如何使用工作流程在Adobe Campaign中自動化流程、管理資料及協調複雜的行銷活動。

+++ 建立工作流程的主要步驟是什麼？

在Campaign中建立自動化行銷流程的工作流程：

1. **建立新的工作流程** — 瀏覽至&#x200B;**[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]**&#x200B;或&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;並按一下&#x200B;**[!UICONTROL Create]**
1. **新增活動** — 從浮動視窗拖放活動（目標定位、流量控制、動作活動）
1. **設定活動** — 按兩下每個活動以設定引數並定義邏輯
1. **連結活動** — 連結活動與轉換，以定義執行流程
1. **測試並驗證** — 使用工作流程圖表來檢查邏輯，然後使用小型資料集進行測試
1. **執行** — 手動啟動工作流程或排程自動執行

常見的工作流程模式：資料匯入、對象細分、傳遞傳送、資料擴充和跨頻道協調。

**相關主題：**

[建置工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"} | [工作流程活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target="_blank"} | [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ 如何將資料匯入 Campaign 中？

視您的需求，使用多種方法將資料匯入Campaign：

**簡單檔案匯入：**

* 使用匯入精靈透過引導式介面進行一次性CSV/TXT匯入
* 適合手動上傳和快速資料載入

**工作流程型匯入：**

* 為複雜匯入建立具有&#x200B;**[!UICONTROL Data loading (file)]**&#x200B;活動的工作流程
* 新增資料轉換、擴充和重複資料刪除
* 排程從SFTP、本機目錄或雲端儲存空間重複匯入

**API整合：**

* 使用REST API以程式設計方式從外部系統匯入資料
* 最適合與CRM、電子商務或其他平台進行即時同步

**最佳作法：**&#x200B;永遠以小樣本進行測試、使用UTF-8編碼、正確對應欄位、套用重複資料刪除規則，以及排程在非尖峰時間的大量匯入。

**相關主題：**

[匯入最佳實務](../start/import.md) | [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hant){target="_blank"} | [週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hant){target="_blank"}

+++

+++ Campaign的常見工作流程使用案例為何？

行銷活動工作流程幾乎可自動化任何行銷流程。 以下是最常見的使用案例：

**資料管理：**

* **匯入及載入資料** — 自動從SFTP、API或雲端儲存空間匯入檔案
* **資料清除** — 重複設定檔、標準化格式、移除無效記錄
* **資料擴充** — 使用外部資料或計算欄位增強設定檔
* **清單管理** — 根據行為或條件自動更新區段

**行銷活動自動化：**

* **歡迎系列** — 觸發新訂閱者的自動上線電子郵件
* **生日行銷活動** — 在客戶生日或週年紀念日傳送個人化訊息
* **重新參與** — 以具有回饋行銷活動的非作用中訂閱者為目標
* **放棄購買** — 傳送提醒給將商品留在購物車中的客戶

**進階目標定位：**

* **A/B測試** — 分割對象並測試不同的內容變數
* **動態細分** — 根據即時行為或屬性建立區段
* **潛在客戶評分** — 根據參與計算並更新潛在客戶評分
* **跨頻道協調** — 協調電子郵件、簡訊和推播的傳訊

**監視和警示：**

* **工作流程監視** — 追蹤工作流程狀態並在失敗時傳送警示
* **傳遞監視** — 監視行銷活動效能和跳出率
* **資料庫維護** — 自動清理舊記錄檔和暫存資料

**整合與同步處理：**

* **CRM同步** — 保持客戶資料與Salesforce、Dynamics等同步
* **API整合** — 與電子商務平台、分析工具或自訂系統連線
* **事件觸發的工作流程** — 對來自網站或應用程式的即時事件做出反應

**相關主題：**

[工作流程使用案例庫](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [建置工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"} | [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target="_blank"} | [目標工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=zh-Hant){target="_blank"} | [資料管理工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ 如何使用工作流程更新 Campaign 資料？

在工作流程中使用&#x200B;**[!UICONTROL Update data]**&#x200B;活動，對資料庫執行大量作業：

**支援的作業：**

* **插入** — 新增記錄至資料庫
* **更新** — 根據比對條件修改現有記錄
* **插入或更新** — 新增記錄或更新現有記錄（更新插入）
* **刪除** — 移除符合特定條件的記錄

**常見使用案例：**

* 在資料擴充後更新設定檔屬性
* 與外部系統同步資料
* 根據行為維護清單成員資格
* 清除並刪除重複資料
* 套用大量狀態變更（例如，選擇退出、隔離）

設定調解金鑰以正確比對記錄，並選擇更新選項（更新所有欄位或僅更新空白欄位）。

**相關主題：**

[更新資料活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=zh-Hant){target="_blank"} | [資料管理活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ 如何運用資料管理功能？

Campaign的資料管理活動可在工作流程中啟用複雜的資料作業，以進行複雜的目標定位和細分。

**金鑰資料管理活動：**

* **擴充** — 從相關資料表或外部來源新增資料至工作母體
* **分割** — 根據條件或隨機分配的區段母體
* **重複資料刪除** — 根據指定的索引鍵移除重複記錄
* **更新資料** — 執行大量插入、更新或刪除作業
* **變更維度** — 切換目標維度（例如，從收件者變更為訂閱）
* **交集/聯合/排除** — 合併或篩選多個母體

**常見使用案例：**

* 使用購買歷史記錄或行為資料豐富設定檔
* 針對不同的訊息，將受眾細分為多個群組
* 在傳遞前移除重複專案
* 整合來自外部資料庫的資料（FDA — 同盟資料存取）
* 建立複雜的多資料表查詢和聯結

這些活動可讓您處理非直接在主要收件者表格中的資料，並執行進階資料庫作業。

**相關主題：**

[資料管理活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [目標工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=zh-Hant){target="_blank"} | [擴充活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=zh-Hant){target="_blank"}

+++

+++ 我可以自動個人化訊息傳送嗎？

是。 工作流程會根據收件者資料、行為和自訂條件，啟用完全自動化的個人化訊息行銷活動。

**自動化工作流程結構：**

1. **查詢** — 根據條件選取目標對象
1. **擴充** — 從相關資料表中新增個人化資料
1. **分割** — 針對不同的訊息變體將區段分成群組（選擇性）
1. **傳遞** — 傳送包含合併欄位的個人化訊息
1. **排程器** — 設定自動行銷活動的循環執行

**Personalization選項：**

* 使用收件者設定檔資料（名稱、位置、偏好設定）
* 包括行為資料（購買記錄、參與分數）
* 根據區段或屬性套用條件式內容
* 計算動態值（熟客點數、到期日）

常見情境：生日行銷活動、購物車放棄、忠誠計畫、回饋行銷活動，以及事件觸發訊息。

**相關主題：**

[Personalization指南](../send/personalize.md) | [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant){target="_blank"} | [擴充活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何使用工作流程將受眾分隔到子集中？

使用&#x200B;**[!UICONTROL Split]**&#x200B;活動，根據條件或分佈規則將單一母體劃分為多個子集。

**分割方法：**

* **篩選條件** — 根據條件建立子集(例如年齡群組、位置、VIP狀態)
* **百分比分佈** — 隨機分割為相等或自訂百分比以進行A/B測試
* **限制記錄** — 限制子集大小（前N筆記錄、前X%、隨機選取）
* **資料群組** — 為每個不同的值建立一個子集（例如，每個國家/地區一個子集）

**常見使用案例：**

* 使用控制組進行A/B測試
* 管道偏好設定路由（電子郵件與簡訊）
* 漸進式轉出（傳送至10%，然後傳送至90%）
* 區段特定訊息(VIP、一般、新客戶)
* 跨多個傳遞伺服器的負載平衡

每個分割的子集都會流向個別的轉變，允許每個群組進行不同的處理或傳送。

**相關主題：**

[分割活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=zh-Hant){target="_blank"} | [A/B測試指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ 如何從外部檔案更新收件者資料？

是。 使用工作流程以外部檔案(CSV、TXT)的值更新Campaign資料。

**工作流程結構：**

1. **資料載入（檔案）** — 載入外部檔案並對應欄
1. **擴充** （選擇性） — 新增其他資料或轉換
1. **調解** — 定義金鑰以比對檔案記錄與資料庫記錄（例如，電子郵件地址、收件者識別碼）
1. **更新資料** — 選擇更新選項：
   * 僅更新相符的記錄
   * 更新現有欄位或僅更新空白欄位
   * 找不到相符專案時插入新記錄

**常見案例：**

* 從CRM匯出更新設定檔屬性
* 從外部系統重新整理訂閱狀態
* 同步熟客點數或客戶分數
* 更新選擇加入/選擇退出偏好設定
* 使用行為資料豐富設定檔

**最佳實務：**&#x200B;使用唯一的識別碼進行調解、在更新之前驗證資料、使用小型範例進行測試，以及排程定期更新以進行同步處理。

**相關主題：**

[匯入資料指南](../start/import.md) | [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hant){target="_blank"} | [更新資料活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何識別和鎖定新的收件者？

將工作流程與查詢活動搭配使用，以識別最近新增的收件者，並觸發自動歡迎行銷活動。

**查詢方法：**

在&#x200B;**[!UICONTROL Created date]**&#x200B;欄位上建立查詢篩選，以選取在特定時間範圍內新增的收件者（例如最近24小時、上週）。

**自動歡迎工作流程結構：**

1. **排程器** — 每日或以特定間隔執行
1. **查詢** — 選取自上次執行後建立的收件者
1. **重複資料刪除** （選擇性） — 確保沒有重複專案
1. **傳遞** — 傳送歡迎訊息
1. **更新資料** （選擇性） — 將收件者標示為「已歡迎」

**具有彙總的進階技術：**

使用彙總函式來動態識別最近的增加，並與之前處理的收件者進行比較，以進行複雜的新收件者偵測。

**相關主題：**

[查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"} | [使用彙總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=zh-Hant){target="_blank"} | [歡迎計畫](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何使用工作流程活動？

行銷活動工作流程是使用4個主要類別的活動所建立，每個類別都有特定的用途：

**目標定位活動** — 定義並調整您的對象

* 查詢，分割，重複資料刪除，擴充，交集，聯合，排除
* 使用這些選項來選取收件者、區段母體，以及合併資料來源

**流量控制活動** — 管理工作流程邏輯和時間

* 排程器、等待、測試、分支、AND — 聯結、OR — 聯結、跳轉
* 控制執行流程、新增條件及管理平行路徑

**動作活動** — 執行作業並傳送訊息

* 傳送、更新資料、資料載入（檔案）、資料擷取（檔案）、JavaScript程式碼
* 執行資料庫作業、檔案傳輸和訊息傳送

**事件活動** — 回應外部觸發程式

* 外部訊號、檔案收集器、HTTP傳輸、簡訊、電子郵件
* 處理傳入資料和外部系統互動

若要使用活動，請將活動從浮動視窗拖曳至工作流程畫布、按兩下以設定引數，然後使用轉變來連線這些活動。

**相關主題：**

[目標定位活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=zh-Hant){target="_blank"} | [流量控制活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=zh-Hant){target="_blank"} | [動作活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=zh-Hant){target="_blank"} | [事件活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=zh-Hant){target="_blank"}

+++

+++ 什麼是工作流程最佳實務？

遵循下列最佳實務，建立有效率、可維護且可靠的工作流程：

**設計與組織：**

* 為工作流程和活動使用清楚的描述性名稱
* 新增標籤和說明至檔案邏輯
* 以視覺化方式分組相關活動以提高可讀性
* 將複雜的流程分成多個較小的工作流程

**效能最佳化：**

* 使用適當的篩選器限制查詢結果大小
* 使用臨時表格作為中繼資料儲存
* 在非尖峰時段排程資源密集的工作流程
* 避免不必要的回圈和過多的反複專案

**錯誤處理與監視：**

* 透過主管新增錯誤處理路徑
* 設定失敗工作流程的警報
* 在完整執行之前使用小型資料範例進行測試
* 定期檢閱執行記錄檔以瞭解效能問題

**維護與治理：**

* 封存或刪除過時的工作流程
* 版本控制工作流程變更和檔案修改
* 限制工作流程的複雜性（目標為小於20個活動）
* 使用工作流程範本進行週期性模式

**安全性與資料管理：**

* 套用適當的操作員許可權
* 使用工作流程清理來清理臨時資料
* 避免硬式編碼值 — 使用變數和選項
* 定期審查並最佳化表現不良的工作流程

**相關主題：**

[工作流程最佳實務指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hant){target="_blank"} | [建置工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"} | [監視工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hant){target="_blank"}

+++

## Campaign設定 {#settings}

使用正確的設定、整合和設定來設定您的Campaign執行個體，以最佳化行銷操作。

+++ 我可以變更 Campaign 介面的語言嗎？

這取決於您使用的介面。 **使用者端主控台**&#x200B;語言已修正，但&#x200B;**Campaign Web UI**&#x200B;可讓個別使用者變更其語言偏好設定。

**使用者端主控台（案頭應用程式）：**

* 語言是在建立執行個體時設定的，且無法變更
* 使用者端主控台和伺服器必須使用相同的語言
* 每個Campaign執行個體都以單一語言運作
* 如果是英文安裝，您可以選擇美式英文或英式英文（它們的日期和時間格式不同）

**Campaign Web UI：**

* 使用者可透過其設定檔偏好設定獨立變更其介面語言
* 地區設定特定的日期、時間和數字格式支援多種語言
* 您的Web UI語言偏好設定與Campaign伺服器和使用者端主控台語言無關


**相關主題：**

[在Campaign Web UI中變更語言](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [開始使用Campaign使用者端主控台](connect.md)

+++

+++ 什麼是Campaign「控制面板」，如何加以存取？

Campaign「控制面板」是網頁式管理介面，可協助Campaign管理員透過管理設定和監控Campaign執行個體的使用情形，提高效率。 它提供自助服務功能，無需聯絡Adobe支援即可管理關鍵執行個體設定。

**主要功能：**

* **子網域管理** — 委派及管理子網域、監視SSL憑證
* **儲存體監視** — 追蹤資料庫使用量並防止儲存體問題
* **SFTP管理** — 監視SFTP儲存空間、管理IP允許清單和SSH金鑰
* **執行個體設定** — 設定IP允許清單、管理URL許可權、檢閱執行個體詳細資料
* **作用中設定檔監控** — 根據許可權追蹤作用中設定檔的使用情況
* **效能監視** — 監視資料庫和工作流程效能
* **電子郵件傳遞能力** — 設定DMARC、BIMI和其他驗證記錄

**存取需求：**

* **僅限管理員使用者** — 控制面板僅限具有管理員許可權的使用者使用
* **Adobe IMS驗證** — 使用您的Adobe ID透過Adobe Experience Cloud存取
* **Campaign v8受管理的Cloud Services** — 僅適用於託管執行個體

**其他資源：**

[控制面板檔案](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/control-panel-home){target="_blank"} | [控制面板教學課程影片](https://experienceleague.adobe.com/zh-hant/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ 如何在 Campaign 實例上設定追蹤功能？

Campaign v8提供全方位追蹤，以監控收件者與訊息的互動。 追蹤需要正確設定執行個體和訊息設定。

**您可以追蹤的專案：**

* **電子郵件開啟** — 透過追蹤畫素（1x1透明影像）
* **連結點選次數** — 所有URL都會自動轉換為追蹤的連結
* **取消訂閱** — 選擇退出連結追蹤
* **映象頁面檢視** — 收件者檢視網頁版本時
* **自訂引數** — 新增追蹤資料至URL以進行進階分析

**金鑰設定步驟：**

1. 在執行個體設定中設定追蹤伺服器URL (由Adobe v8管理)
2. 在傳遞屬性中啟用追蹤
3. 自動設定個別連結或所有連結的追蹤
4. 定義追蹤有效期和記錄保留

**最佳實務：**&#x200B;在傳送給主要對象之前，請一律使用校樣測試追蹤，以確保連結正確運作且擷取資料。

**相關主題：**

[追蹤及監視傳遞](tracking.md) | [設定追蹤的連結](../send/email.md)

+++

+++ 如何設定電子郵件傳遞機制?

電子郵件傳遞能力取決於技術設定、內容品質和寄件者信譽。 Campaign v8提供工具和設定，以最佳化收件匣位置。

**基本設定步驟：**

* **網域驗證** — 設定SPF、DKIM和DMARC記錄以驗證您的傳送網域
* **IP預熱** — 逐漸增加新IP上的傳送量，以建立信譽
* **寄件者設定** — 使用一致且可辨識的寄件者位址和名稱
* **跳出管理** — 設定隔離規則以自動處理硬跳出和軟跳出
* **回饋迴路** — 設定投訴處理以管理垃圾郵件報告

**內容最佳實務：**

* 使用SpamAssassin測試電子郵件以檢查垃圾郵件分數
* 維持適當的文字與影像比例
* 在HTML旁包含純文字版本
* 一律提供取消訂閱連結
* 避免垃圾郵件觸發字詞和過度大寫

**監控：**&#x200B;使用Campaign的傳遞能力報告來追蹤跳出率、投訴率和收件匣位置。 對於Campaign v8，Adobe提供基礎架構層級的傳遞能力最佳化。

**相關主題：**

[關於Campaign](../send/about-deliverability.md)中的傳遞能力 | [傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}

+++

+++ 我可以將 Campaign 連線到哪些外部資料庫？

Campaign v8支援與主要企業資料庫系統的同盟資料存取(FDA)連線，讓您能夠運用現有的資料基礎架構。

**支援的資料庫：**

* **雲端資料庫：** Amazon Redshift、Google BigQuery、Snowflake、Azure Synapse Analytics
* **企業資料庫：** Oracle、Microsoft SQL Server、PostgreSQL、MySQL
* **資料倉儲：** Teradata， Vertica， SAP HANA
* **巨量資料：**&#x200B;透過Hive的Hadoop

**特定平台的考量事項：**&#x200B;支援的資料庫版本和連線需求不同。 Campaign v8作為Managed Cloud Service可能有針對外部資料庫存取的特定網路和安全要求。

**重要：**&#x200B;請務必檢查Campaign v8版本的官方相容性矩陣，以確認特定資料庫版本的支援，並確保外部資料庫聯結器的授權正確。

**相關主題：**

[相容性矩陣](compatibility-matrix.md) | [設定FDA連線](../connect/fda.md)

+++

+++ Adobe Campaign可以與CRM系統整合嗎？

是。 Campaign提供原生CRM聯結器，以在Campaign與您的CRM系統之間無縫進行雙向同步，確保所有平台上的客戶資料一致。

**支援的CRM系統：**

* **Salesforce** — 銷售機會、聯絡人、客戶、商機、行銷活動
* **Microsoft Dynamics 365** — 聯絡人、帳戶、銷售機會、自訂實體
* 透過自訂API整合的其他CRM

**同步專案：**

* **從CRM到Campaign：**&#x200B;連絡人記錄、帳戶資訊、銷售機會、自訂欄位、分段資料
* **從Campaign到CRM：**&#x200B;傳遞記錄、追蹤資料、參與量度、行銷活動回應、訂閱狀態

**同步處理模式：**

* **已排程** — 以定義的間隔（每小時、每天）自動同步
* **手動** — 運運算元觸發的隨選同步處理
* **即時** — 透過API立即更新（自訂開發）

**設定：**&#x200B;使用Campaign的內建CRM聯結器助理將CRM欄位對應到Campaign屬性、選取要同步處理的資料表，以及排程同步處理。 聯結器會處理衝突解決並維護資料一致性。

**最佳實務：**&#x200B;從唯讀同步開始以測試對應，然後啟用雙向同步。 監控同步記錄檔是否有錯誤，並維護兩個系統中的乾淨資料。

**相關主題：**

[CRM聯結器組態](../connect/crm.md) | [工作流程CRM活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何清除使用者端主控台快取？

清除使用者端主控台快取可解決許多常見的顯示和功能問題。 快取會儲存本機設定檔，這些設定檔有時可能會損毀或過時。

**何時清除快取：**

* 新品牌元素（標誌、顏色）無法正確顯示
* 匯出/匯入函式意外失敗
* 組態變更後介面元素未更新
* 效能問題或主控台回應緩慢
* 升級至新的使用者端主控台版本之後

**清除快取的步驟：**

1. 開啟Campaign使用者端主控台
2. 前往&#x200B;**[!UICONTROL File]**&#x200B;功能表
3. 選取&#x200B;**[!UICONTROL Clear the local cache...]**
4. 出現提示時確認動作
5. 重新啟動使用者端主控台

**相關主題：**

[安裝及設定使用者端主控台](connect.md)

+++

+++ 我可以設定使用者介面設定嗎？

是。 Campaign管理員可以自訂使用者介面，以符合組織品牌並最佳化使用者體驗。 在執行個體或使用者層級進行設定。

**您可以自訂的專案：**

* **品牌** — 標誌、色彩和視覺識別專案
* **預設檢視** — 首頁配置、資料夾結構可見性
* **清單設定** — 資料清單中的預設欄、排序順序、篩選器
* **導覽** — 可用的功能表專案和捷徑
* **地區設定** — 日期/時間格式、數字格式、時區
* **通知** — 電子郵件通知、應用程式內通知、工作流程通知

**組態層級：**

* **執行個體範圍** — 套用至所有使用者（需要系統管理員許可權）
* **使用者特定** — 個別偏好設定和個人設定
* **操作員群組** — 所有群組成員繼承的設定

**相關主題：**

[設定UI設定](../config/ui-settings.md) | [使用者許可權](gs-permissions.md)

+++

+++ 我可以建立自訂欄位和表格嗎？

是。 Campaign彈性的資料模型可讓您使用自訂欄位擴充內建方案，並建立全新的表格來滿足您的特定業務需求。

**您可以自訂的專案：**

* **新增欄位至現有表格** — 使用忠誠度積分、自訂偏好設定、外部ID擴充收件者表格
* **建立新的自訂表格** — 儲存產品、交易、熟客層、自訂實體
* **定義關係** — 將自訂資料表連結至現有的Campaign資料表
* **擴充表單** — 更新UI以顯示和編輯自訂欄位

**常見使用案例：**

* 儲存其他設定檔屬性(客戶期限值、偏好存放區、VIP狀態)
* 使用自訂屬性管理產品目錄
* 追蹤自訂事件和互動
* 整合外部系統ID以進行資料同步
* 建立產業專屬資料模型（零售、金融、旅遊）

**相關主題：**

[擴充資料模型](../dev/extend-schema.md) | [結構描述結構](../dev/schemas.md) | [資料模型最佳實務](../dev/datamodel-best-practices.md)

+++

## 報告 {#reporting}

深入瞭解Campaign的報告功能，包括內建報表、自訂報表和資料分析工具，例如多維度資料集。

+++ 如何建立新報表？

Campaign會根據您的需求和技術專業知識提供多種報告選項。 您可以使用內建報表、在使用者端主控台中建立自訂報表，或在Campaign Web UI中設計視覺控制面板。

**報告選項：**

* **內建報告** — 可從&#x200B;**[!UICONTROL Reports]**&#x200B;標籤存取的立即可用的傳遞、行銷活動和追蹤報告
* **描述性分析** — 使用精靈驅動介面快速統計任何資料
* **自訂報告** — 由技術使用者使用報告編輯器建置的進階報告
* **Web UI儀表板** — 具有拖放介面的現代化視覺化報表和儀表板
* **多維度資料集** — 多維度資料探索與樞紐分析表分析

**重要：**&#x200B;行銷活動是專為行銷作業報告所設計，不是作為專門的商業智慧工具。 為了滿足複雜的分析需求，請考慮與Adobe Analytics或專用的BI平台整合。

**相關主題：**

[開始使用報告](../reporting/gs-reporting.md) | [Campaign Web UI報告](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ 如何設計並分享母體的靜態報表？

使用Campaign的描述性分析工具，快速產生任何人口資料的統計報表。 此精靈驅動功能可協助您分析分佈、趨勢和模式，而不需要技術專業知識。

**您可以分析的專案：**

* 收件者人口統計和細分劃分
* 行銷活動效能量度和回應率
* 設定檔屬性的分佈（年齡、位置、偏好設定）
* 傳遞統計資料和參與模式
* 自訂欄位值和資料品品質度

**如何建立：**&#x200B;選取任何清單或查詢結果→按一下滑鼠右鍵→ **[!UICONTROL Actions > Analyze]** →選擇分析型別（質化或量化）→設定顯示選項→產生報告。

**共用：**&#x200B;將報告匯出至Excel/PDF或儲存至&#x200B;**[!UICONTROL Reports]**&#x200B;資料夾，以便擁有適當許可權存取團隊。

深入瞭解[描述性分析](../reporting/built-in-reports.md)

+++

+++ 如何在我的資料上設計進階報表？

Campaign提供兩種建立進階自訂報表的方法：用於複雜分析的使用者端主控台中的技術報表，以及用於更輕鬆建立報表的視覺控制面板。

在使用者端主控台中，您可以：

* 使用SQL查詢和自訂計算建立複雜報表
* 建立具有圖表、表格和樞紐分析表的多頁報表
* 設計條件式格式和動態內容
* 存取完整的Campaign資料模型和外部資料庫(FDA)

瞭解如何[建立自訂報告（使用者端主控台）](../reporting/custom-reports.md)

+++

+++ 什麼是多維度資料集？如何將其用於報表？

立方體是多維度資料結構，可讓業務使用者透過樞紐分析表探索及分析Campaign資料，而不需要技術技能。 請將它們視為預先設定的資料模型，可簡化複雜的報表。


* 技術使用者建立並設定多維度資料集，以定義維度（時間、地理位置、管道）和測量（開啟、點按、收入）
* 商務使用者在建立報表時選取多維度資料集，並拖放維度以探索資料
* 資料會根據立方結構組態自動彙總和計算
* 結果可以顯示為樞紐分析表、圖表或匯出至Excel

瞭解如何[使用多維度資料集探索資料](../reporting/gs-cubes.md)

+++

+++ 我可以利用線上意見調查結果建立報表嗎？

是！ Campaign包含「調查」模組，可讓您建立線上問卷，並針對調查回應產生內建報表。

**重要：**&#x200B;調查管理在Campaign v8企業(FFDA)部署中無法使用。 [了解更多](../architecture/enterprise-deployment.md)。

**問卷功能：**

* 建立包含多個頁面和問題型別的線上問卷
* 收集資料庫或本機變數中的回應
* 檢視調查回應的即時追蹤
* 產生調查答案的專屬報告（依問題、一般統計資料劃分）
* 將調查回應匯出至Excel、PDF或CSV，以供進一步分析
* 在鎖定工作流程中使用調查資料來個人化行銷活動

**內建意見調查報告：**

* **一般報告** — 依來源和語言顯示一段時間的回應趨勢
* **答案劃分** — 每個問題的詳細答案劃分
* **檔案報告** — 問卷結構的視覺化表示

**進階分析：**

* 從&#x200B;**[!UICONTROL Responses]**&#x200B;索引標籤存取調查回應並匯出資料
* 在工作流程中使用&#x200B;**[!UICONTROL Survey responses]**&#x200B;活動，根據收件者的回答來鎖定收件者
* 結合調查資料與其他Campaign資料，以進行細分和個人化
* 建立多維度調查分析的自訂報表與多維度資料集

**相關主題：**

[開始使用意見調查](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [意見調查報告](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ 如何共用報表的存取許可權？

Campaign提供彈性的選項，讓您與不同的使用者群組共用報表，根據角色和責任控制可見度和存取許可權。

**報表存取控制：**

* **資料夾許可權** — 將報表放在具有使用者群組適當讀取/寫入存取權的資料夾中
* **已命名的許可權** — 指派檢視、建立或修改報告的特定許可權
* **顯示內容** — 定義報表出現的位置：在&#x200B;**[!UICONTROL Reports]**&#x200B;資料夾、行銷活動標籤或傳送畫面中
* **網頁UI共用** — 透過Campaign網頁UI與團隊成員共用儀表板連結

**如何設定存取權：**

1. 將報告儲存至使用者端主控台中的特定資料夾
2. 設定相關操作員群組的檔案夾存取許可權
3. 定義報表屬性：報表型別、顯示內容和使用狀態
4. 在更廣的轉出之前，先與目標群組中的使用者測試存取權

**最佳實務：**&#x200B;以量身打造的存取許可權，為不同團隊（行銷、作業、管理）建立專屬的報告資料夾。 記錄報表用途和重新整理排程。

**相關主題：**

[自訂報告](../reporting/custom-reports.md) | [使用者許可權](gs-permissions.md)

+++

+++ 我可以匯出不同格式的報告嗎？

是的，Campaign支援使用者端主控台和Web UI報告的多種匯出格式，讓利害關係人可輕鬆共用，並與其他工具整合。

**可用的匯出格式：**

* **Excel (.xlsx)** — 最適合資料操作、進一步分析和樞紐分析表
* **PDF** — 適用於簡報、高階主管摘要和列印的報告
* **CSV** — 最適合將資料匯入其他系統和BI工具
* **OpenDocument (.ods)** — 開放原始碼試算表格式
* **XML** — 用於系統整合和自動化處理

**如何匯出：**

* **使用者端主控台：**&#x200B;開啟報告→按一下&#x200B;**[!UICONTROL Export]**&#x200B;按鈕→選擇格式→儲存檔案
* **網頁UI：**&#x200B;開啟儀表板→按一下匯出圖示→選取格式→下載
* **自動匯出：**&#x200B;使用工作流程搭配匯出活動排程定期匯出

**最佳實務：**

* 使用Excel處理需要利害關係人分析和註解的報告
* 使用PDF傳送靜態報告給高階主管或封存以供法規遵循
* 使用CSV與資料倉儲或外部分析工具整合
* 測試匯出的報表，確保格式化和資料的準確性

**相關主題：**

[自訂報告](../reporting/custom-reports.md) | [Campaign Web UI報告](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## 開發人員 {#developers}

存取開發人員的技術資訊，包括資料模型詳細資訊、結構描述、API和自訂功能。

+++ 什麼是Campaign資料模型？

Campaign的資料模型是方案導向的關聯式資料庫結構，可定義行銷資料的整理和相關方式。 它包含核心行銷物件（收件者、傳送、行銷活動）的內建表格，可以擴充以符合您的特定業務需求。

**重要資料模型概念：**

* **結構描述** — 描述資料表結構、欄位和關係的XML定義
* **內建資料表** — 核心行銷實體（收件者、傳遞、工作流程、行銷活動）
* **連結** — 資料表之間的關係(1-1、1-N、N-N)
* **分項清單** — 下拉式欄位的預先定義值清單
* **延伸模組** — 新增至標準模型的自訂欄位和表格

**主要內建結構描述：**

* **收件者(nms:recipient)** — 客戶設定檔與連絡資訊
* **傳遞(nms:delivery)** — 電子郵件、簡訊和推播行銷活動
* **工作流程(xtk:workflow)** — 自動化程式
* **行銷活動(nms:operation)** — 行銷活動策劃
* **追蹤記錄** — 開啟、點按和參與資料

**重要原因：**&#x200B;瞭解資料模型對於建立工作流程、建立查詢、擴充結構描述及開發自訂整合至關重要。 這種以結構描述為基礎的方法可確保資料一致性，並啟用強大的查詢功能。

**相關主題：**

[行銷活動資料模型](../dev/datamodel.md) | [資料模型最佳實務](../dev/datamodel-best-practices.md)

+++

+++ 如何使用 Campaign 綱要？

綱要是Campaign資料結構的基礎，以XML格式定義表格、欄位和關係。 瞭解結構對於自訂、整合和進階工作流程開發至關重要。

**定義的結構描述：**

* **資料表結構** — 資料庫資料表及其對應的應用程式物件
* **欄位屬性** — 資料型別、標籤、驗證規則和預設值
* **關係** — 資料表（聯結）與基數之間的連結
* **索引** — 查詢效能的資料庫最佳化
* **存取控制** — 使用者可以檢視及修改哪些欄位

**使用結構描述：**

* **檢視結構描述：**&#x200B;透過使用者端主控台中的&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;存取
* **擴充結構描述：**&#x200B;建立擴充結構描述（例如`cus:recipient`擴充`nms:recipient`）以新增自訂欄位，而不修改核心結構描述
* **建立自訂結構描述：**&#x200B;為特定企業資料建立全新的資料表
* **更新資料庫：**&#x200B;使用&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;套用結構描述變更

**常見使用案例：**

* 將自訂欄位新增至收件者表格（公司ID、忠誠度等級、偏好設定）
* 建立產品、商店或交易的自訂表格
* 定義自訂與內建表格之間的關係
* 實作特定企業資料模型

**重要：**&#x200B;絕對不要直接修改內建結構描述。 請一律使用擴充功能結構描述，以保留升級相容性和Adobe支援。

**相關主題：**

[開始使用結構描述](../dev/schemas.md) | [擴充結構描述](../dev/extend-schema.md)

+++

+++ 如何使用自訂的收件者表格？

當您的企業需要不同的資料結構來進行目標定位時（例如，B2B帳戶、訂閱者、潛在客戶或外部聯絡人），Campaign可讓您使用自訂表格，而不是內建的收件者表格。

**為何使用自訂收件者資料表：**

* 目標B2B公司或組織單位，而非個別聯絡人
* 將訂閱者資料與主要客戶資料庫分開
* 使用其他系統的現有客戶資料表
* 使用獨立的聯絡表實作多品牌架構
* 符合特定的資料控管要求

**實作步驟：**

1. 建立定義收件者表格結構的自訂結構
2. 包含必要欄位（電子郵件、主索引鍵、排除標幟）
3. 設定目標對應以將您的表格與傳遞連結
4. 更新傳遞範本以使用新的目標對應
5. 調整工作流程和查詢以參考自訂表格

**主要考量事項：**

* 自訂收件者表格必須包含傳送（電子郵件、排除、追蹤）的必要欄位
* 工作流程和表單需要調整以與自訂結構搭配使用
* 部分內建功能可能需要自訂
* 在移轉生產行銷活動之前，測試至關重要

**最佳實務：**&#x200B;在考慮自訂資料表之前，請先擴充標準收件者資料表。 自訂收件者表格會增加複雜性，因此只能在真正必要時使用。

**相關主題：**

[自訂收件者資料表](../dev/custom-recipient.md) | [目標對應](../audiences/target-mappings.md)

+++

+++ 在 Campaign 中定義查詢的最佳做法是什麼？

Campaign的查詢編輯器是一種功能強大的視覺工具，可在不具備SQL知識的情況下建立資料庫查詢。 熟悉此元素對於有效鎖定目標、細分和資料分析至關重要。

**使用查詢的位置：**

* **工作流程活動** — 查詢、分割、更新資料、擴充活動
* **傳遞目標定位** — 定義行銷活動的收件者母體
* **清單** — 建立動態或靜態收件者清單
* **報告** — 建置自訂資料擷取和分析
* **篩選器** — 建立可重複使用的目標定位條件

**查詢最佳實務：**

* **開始簡單** — 逐步建置查詢，在每個步驟進行測試
* **使用篩選維度** — 利用資料表(收件者→傳遞→追蹤記錄檔)之間的關係
* **最佳化效能** — 索引經常查詢的欄位，避免複雜的計算欄位
* **利用預先定義的篩選器** — 重複使用並合併現有的篩選器，以維持一致性
* **使用小型範例進行測試** — 先驗證查詢邏輯，然後在完整資料庫上執行
* **記錄複雜查詢** — 新增維護與知識轉移的說明

**常見查詢模式：**

* 定位開啟特定傳送的收件者：篩選連結至收件者的追蹤記錄
* 搜尋無效連絡人：查詢上次交貨日期或追蹤活動
* 依行為分段：結合傳送、追蹤和設定檔條件
* 排除先前的收件者：使用集合操作（聯合、交集、排除）

**存取一般查詢編輯器：** **[!UICONTROL Tools > Generic query editor]**，在工作流程外部進行臨機資料庫探索和資料擷取。

**相關主題：**

[查詢編輯器](../start/query-editor.md) | [在工作流程中查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hant){target="_blank"}

+++

+++ 如何匯入資料包？

資料包可讓您在執行個體之間匯出和匯入Campaign設定（結構、工作流程、型別、篩選器）和資料。 這對於將配置從開發部署到生產或在組織間共用元件至關重要。

**可封裝的專案：**

* **設定物件** — 結構描述、工作流程、型別規則、表單、篩選器
* **促銷活動元件** — 傳遞範本、促銷活動範本、內容區塊
* **應用程式設定** — 運運算元、運運算元群組、資料夾結構
* **資料** — 收件者清單、種子地址、內容片段
* **自訂開發** - JavaScript程式碼、SQL指令碼、網頁應用程式


**封裝型別：**

* **使用者套件** — 您建立和匯出的自訂組態
* **平台套件** - Adobe提供的功能和更新
* **資料套件** — 包含實際的資料記錄，而不只是結構

**最佳實務：**

* 一律從相同或較舊的Campaign版本匯出套件
* 生產前在開發環境中測試套件匯入
* 檔案套件內容和相依性
* 對封裝XML檔案使用版本控制
* 在主要套件匯入之前備份執行個體

進一步瞭解如何[使用資料套件](../dev/packages.md)

+++

+++ 我可以在哪裡找到Campaign v8 API清單？

Campaign v8提供全面的API檔案，涵蓋SOAP API （用於使用者端主控台互動）和REST API （用於現代整合）。 API參考包含所有可用的方法、引數和回應格式。

**促銷活動API型別：**

* **SOAP API** - Campaign使用者端主控台作業、結構描述操控和工作流程控制的傳統API
* **REST API** — 用於外部系統整合、設定檔管理和事件觸發的現代HTTP API
* **JavaScript API** — 工作流程活動和自訂商業邏輯的伺服器端指令碼API

**API檔案資源：**

* **完整API參考資料：**&#x200B;包含方法簽章、引數和範例的完整SOAP API檔案
* **REST API指南：**&#x200B;設定檔、事件和組織單位的現代REST端點
* **JavaScript API：**&#x200B;工作流程指令碼和Web應用程式中可用的伺服器端函式

**常見API使用案例：**

* 將Campaign與CRM、ERP或自訂應用程式整合
* 自動化行銷活動作業和工作流程執行
* 在系統之間即時同步資料
* 建立自訂監控和警報解決方案
* 為Campaign資料和作業建立外部介面

**存取：** [Campaign v8 API檔案](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant){target="_blank"}

+++


+++ 如何透過API監視工作流程？

Campaign API可讓您以程式設計方式控制和監視工作流程的執行，啟用外部監控系統、自動警報和自訂協調解決方案。

**您可以透過API執行的動作：**

* **開始工作流程** — 以程式設計方式觸發工作流程執行
* **暫停/繼續工作流程** — 控制工作流程執行流程
* **停止工作流程** — 終止執行中的工作流程
* **查詢工作流程狀態** — 檢查工作流程是否正在執行、暫停或完成
* **擷取記錄檔** — 存取工作流程執行記錄檔和錯誤訊息
* **監視活動進度** — 追蹤個別工作流程活動完成

**API端點：**

所有工作流程控制命令都會使用具有不同方法引數的相同POST端點：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**可用命令：**

* `{"method":"start"}` — 開始工作流程
* `{"method":"pause"}` — 暫停執行中的工作流程
* `{"method":"resume"}` — 繼續暫停的工作流程
* `{"method":"stop"}` — 停止工作流程

**常見使用案例：**

* 建立自訂監控儀表板，顯示工作流程健康狀況
* 在工作流程失敗或執行太長時實作自動警報
* 從外部排程器或事件系統協調工作流程
* 跨多個Campaign執行個體建立工作流程相依性
* 產生自訂工作流程執行報告

**最佳實務：**&#x200B;結合API監視與工作流程稽核軌跡，以進行完整的工作流程控管。 使用外部監視工具來追蹤工作流程SLA和效能測量結果。

瞭解如何[透過API控制工作流程](../dev/api/controlling-a-workflow.md)

+++

+++ 如何更新資料庫結構？

修改Campaign綱要（新增欄位、建立表格、變更資料型別）後，您必須更新實體資料庫結構以套用變更。 此同步會確保資料庫符合您的結構描述定義。

**需要資料庫更新時：**

* 將新欄位新增到現有結構描述
* 建立自訂表格或擴充內建表格
* 修改欄位屬性（資料型別、長度、必要狀態）
* 新增或移除表格之間的連結
* 建立新的索引以進行查詢最佳化


**重要考量：**

* **先備份** — 一律先備份資料庫，再進行結構變更
* **開發中的測試** — 在生產之前驗證開發環境中的結構描述變更
* **停機時間計畫** — 大型結構變更可能需要短暫的維護期間
* **受管理的Cloud Services** — 與Adobe支援協調重大變更
* **可還原性** — 某些變更（如移除欄位）可能會導致資料遺失

**最佳實務：**&#x200B;使用結構描述版本設定和變更追蹤。 記錄所有用於維護和疑難排解的自訂結構修改。

**相關主題：**

[更新資料庫結構](../dev/update-database-structure.md) | [擴充結構描述](../dev/extend-schema.md)

+++

## 隱私權 {#privacy}

瞭解Adobe Campaign如何協助您遵守GDPR和CCPA等隱私權法規，以及管理資料主體請求。

+++ Campaign的主要隱私權概念為何？

Campaign透過管理資料主體權利、同意和資料保留的工具，協助您遵守隱私權法規(GDPR、CCPA、PDPA、LGPD)。 重要概念包括隱私權法規、個人資料識別、資料主體權利（存取、刪除、可攜性）、同意管理和資料保留政策。

身為資料控制方，您負責處理資料主體請求、維護同意記錄，並確保資料使用透明。

深入瞭解[隱私權管理](../start/privacy.md)

+++

+++ 如何確保Campaign的隱私權法規遵循？

Campaign提供隱私權法規遵循工具，但法律責任由您承擔。 與隱私權計畫的法律顧問合作。

**基本動作：**

* 建立處理資料主體請求（存取、刪除）的程式
* 透過時間戳記和範圍追蹤實作同意管理
* 在所有行銷電子郵件中包含取消訂閱連結
* 稽核資料來源並移除未使用的資料
* 套用最低許可權存取控制項

Campaign提供隱私權核心服務整合、同意追蹤、自動刪除工作流程，以及稽核追蹤的合規性。

深入瞭解[隱私權管理](../start/privacy.md)

+++

+++ 如何在Campaign中收集和管理使用者同意？

有效的同意需要有效、特定、知情且可撤銷的同意。 使用者必須執行明確的動作 — 沒有預先核取的方塊或沈默表示同意。 針對不同用途而分開同意（未捆綁）、提供清楚的解釋，並維護包含時間戳記的記錄。

**最佳實務：**&#x200B;提供細微的選擇加入選項、定期重新整理同意、讓偏好設定中心易於存取，並在建立信任時將同意框架化。

**促銷活動中的技術實作：**

Campaign提供訂閱服務、偏好設定中心、選擇退出標幟，以及追蹤同意的自訂同意欄位。

* 擴充同意欄位的收件者綱要（日期、型別、來源）
* 為每個同意型別建立訂閱服務
* 建立偏好設定中心網路表單
* 使用工作流程強制目標定位中的同意
* 維護稽核軌跡

請諮詢法律顧問，確保您的實作符合法規要求。

**相關主題：**

[訂閱服務](../start/subscriptions.md) | [隱私權與同意](../start/privacy.md#consent-retention-roles) | [隱私權管理](../start/privacy.md)

+++

+++ 當我處理刪除請求時，會刪除哪些資料？

Campaign會自動刪除連結至資料主體的所有資料：收件者設定檔、傳遞和追蹤記錄、具有擁有權關係的自訂資料、訂閱歷史記錄以及網路追蹤資料。

**其運作方式：** Campaign會刪除結構描述定義中連結至收件者的連結有`integrity="own"`的所有資料，確保跨相關資料表進行階層式刪除。

您可以修改結構描述中的連結完整性來自訂刪除範圍，但請先洽詢法律顧問。 刪除是永久性的，無法復原。

**相關主題：**

[隱私權管理](../start/privacy.md) | [結構描述連結](../dev/schemas.md)

+++

+++ 隱私權刪除是否會影響我的傳遞報告？

沒有。行銷活動報表是根據預先計算的彙總量度（傳送總數、開啟次數、點按次數），而不是個別記錄的即時查詢。 刪除個別收件者資料不會變更歷史彙總統計資料。

整體傳遞統計資料和效能量度保持不變，而個別追蹤記錄和個人詳細資料則會被移除。 這可讓您維持行銷分析，同時尊重資料主體的權利。

**相關主題：**

[隱私權管理](../start/privacy.md) | [報告](../reporting/gs-reporting.md)

+++

+++ 如何防止重新匯入已刪除的資料？

您必須從所有來源系統，而不僅僅是Campaign刪除資料。 資料通常會從外部系統（CRM、電子商務、資料倉儲）流動。

**必要的動作：**&#x200B;識別所有資料來源、從來源系統刪除、新增至排除/隱藏清單、更新匯入工作流程以遵循刪除旗標，以及記錄程式。

身為資料控管者，您負責整個技術生態系統的完整資料移除工作。

**相關主題：**

[隱私權管理](../start/privacy.md) | [匯入工作流程](../config/workflows.md)

+++

+++ 已刪除的使用者可以再次選擇加入嗎？

是。 資料主體可在刪除後再次選擇加入。 Campaign會建立全新的收件者記錄，不含先前已刪除資料的連結 — 設定檔會以空白顯示窗開始。

Campaign的稽核軌跡會記錄刪除事件和新設定檔建立，以展示合規性，並在刪除後自由顯示新的選擇加入。

**相關主題：**

[隱私權管理](../start/privacy.md) | [訂閱](../start/subscriptions.md)

+++

## 仍需要協助嗎？ {#get-help}

找不到您要尋找的內容？ 以下是協助您成功使用Adobe Campaign v8的其他資源。

### 社群支援

與其他Campaign使用者和Adobe專家交流，以分享知識並獲得答案。

* **[Adobe Campaign社群](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** — 提出問題、共用解決方案，以及與Campaign社群連絡
* **[Experience League論壇](https://experienceleaguecommunities.adobe.com/){target="_blank"}** — 瀏覽所有Adobe產品的討論
* **[Campaign社群辦公時間](https://experienceleague.adobe.com/zh-hant){target="_blank"}** — 與Adobe專家一起加入即時會議

### 檔案與學習

存取全方位的指南、教學課程和訓練教材。

* **[Campaign教學課程](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=zh-Hant){target="_blank"}** — 逐步影片指南和實作教學課程
* **[新增功能](whats-new.md)** — 最新功能
* **[發行說明](release-notes.md)** — 目前和先前的發行資訊
* **[版本和升級](upgrades.md)** — 瞭解Campaign的版本、升級，以及如何檢查您的版本

### 技術資源

尋找詳細的技術檔案和開發人員資源。

* **[Campaign API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant){target="_blank"}** — 完整API參考檔案
* **[相容性矩陣](compatibility-matrix.md)** — 支援的系統和版本
* **[版本和升級常見問題集](upgrades.md#upgrades-faq)** — 檢查您的版本並瞭解升級相關資訊

### 支援與服務

取得Adobe支援團隊的協助並管理您的執行個體。

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** — 記錄支援案例並管理使用者
* **[Adobe客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** — 聯絡支援團隊
* **[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant){target="_blank"}** — 管理您的Campaign執行個體設定
* **[系統狀態](https://status.adobe.com/){target="_blank"}** — 檢查Adobe服務狀態

### 培訓與認證

透過官方的Adobe培訓和認證計畫提升您的技能。

* **[Experience League說明](https://experienceleague.adobe.com/zh-hant/browse/campaign/campaign-v8){target="_blank"}** - Campaign v8的說明資源（Web UI和CLient主控台）
* **[Adobe數位學習服務](https://learning.adobe.com/){target="_blank"}** — 官方講師授課和自訂進度課程
* **[Adobe Campaign認證](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=zh-Hant){target="_blank"}** — 以專業認證驗證您的專業知識
* **[Experience League學習路徑](https://experienceleague.adobe.com/zh-hant?lang=en#dashboard/learning){target="_blank"}** — 引導式學習歷程

### 其他實用資源

* **[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=zh-Hant){target="_blank"}** - Classic v7使用者的參考
* **[Campaign Web UI檔案](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}** — 新的Web介面指南
* **[傳遞能力最佳實務](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}** — 最佳化電子郵件傳遞

