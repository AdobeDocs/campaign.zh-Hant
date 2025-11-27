---
title: Campaign v8 常見問題
description: 取得有關設定、設定、傳訊、工作流程等常見Adobe Campaign v8問題的解答
feature: Overview
role: User
level: Beginner
keywords: 常見問題集， Campaign v8，問題，回答，說明，支援，疑難排解
hide: true
hidefromtoc: true
source-git-commit: 09911f7112a89b2cc5235b71bbcaa963ae739aed
workflow-type: tm+mt
source-wordcount: '9652'
ht-degree: 28%

---

# 常見問題集 {#faq}

取得Adobe Campaign v8常見問題的快速解答。 無論您是剛開始使用還是尋找進階設定說明，您都可以找到以下依主題整理的答案。

**Campaign新使用者？**&#x200B;以[一般問題](#general)和[重要概念](#key-concepts)開始。\
**需要技術協助嗎？**&#x200B;檢查[開發人員](#developers)和[行銷活動設定](#settings)。\
**找不到您的答案？**&#x200B;造訪我們的[社群論壇](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}或[連絡支援](#get-help)。

>[!TIP]
>
>使用Ctrl+F (Mac上的Cmd+F)在此頁面上搜尋特定關鍵字。 按一下任何問題以展開答案。


## 一般問題 {#general}

取得有關Adobe Campaign v8最常見問題的解答，包括如何連線、升級和取得支援。

+++ 如何連線至 Campaign v8？

您需要下載安裝 Campaign 用戶端主控台，才能連線至 Adobe Campaign。

[按一下這裡以瞭解更多資訊](connect.md)。

自Campaign v8.6發行版本開始，您可以透過中央Adobe Experience Cloud環境存取&#x200B;**Campaign網頁使用者介面**。 Experience Cloud是Adobe的整合式數位行銷應用程式產品和服務系列。

[在此頁面中](campaign-ui.md#ac-web-ui)了解如何連線至 Adobe Experience Cloud，以及存取 Adobe Campaign Web 介面。

在 [Adobe Campaign Web 使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}之中瞭解更多資訊。

>[!TIP]
>
>**疑難排解連線問題：**
>
>* 驗證您的Adobe ID憑證是否正確
>* 確定您的使用者端主控台版本符合伺服器版本
>* 檢查網路連線和防火牆設定
>* 如果發生問題，請清除使用者端主控台快取
>* 請聯絡您的管理員以驗證您的使用者許可權

**相關主題：**

* [安裝用戶端控制台](connect.md)
* [Campaign使用者介面](campaign-ui.md)
* [使用者許可權](gs-permissions.md)

+++

+++ Campaign v8是否可安裝在內部部署或混合環境中？

Campaign v8 僅適用於 Managed Cloud Services，完全由 Adobe 託管。

+++

+++ 如何將 Campaign 升級至最新版本？

定期更新 Adobe Campaign。每年都會推出次要版本，其中包含新功能、改進和修正。 此外，我們定期發行只累積修正的版本編號。

此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境安全，以改善我們的產品使用體驗。這就是我們認為您需要執行最新 Adobe Campaign 版本的重要原因。

>[!NOTE]
>
>作為「受管理的Cloud Services」使用者，您的執行個體會透過新發行版本由Adobe升級。

+++

+++ 如何改進電子郵件傳遞機制?

對於每個位寄件者的成功行銷方案，電子郵件傳遞能力是關鍵部分，必須具備不斷變化的標準及規則。 在這個數位世界中進行有效導覽，需要定期調整您的電子郵件策略，考量傳遞能力的重要趨勢，以便最能觸及您的客群。

請參閱本指南以瞭解[傳遞能力最佳實務](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}

在[本指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hant){target="_blank"}中，瞭解如何在 Campaign 中實施傳遞能力

>[!TIP]
>
>**關鍵傳遞秘訣：**
>
>* 維護乾淨的電子郵件清單，並定期移除非作用中的訂閱者
>* 使用雙重選擇加入以確保參與的收件者
>* 監視您的寄件者信譽和IP信譽
>* 使用SPF、DKIM和DMARC驗證您的電子郵件
>* 立即處理取消訂閱的要求
>* 在傳送給大型受眾之前測試您的電子郵件

**相關主題：**

* [關於傳遞能力](../send/about-deliverability.md)
* [控制訊息內容](../send/control-message-content.md)
* [監視傳遞能力](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ 如何確定我是否成功傳遞，以及是否出現錯誤？

Adobe Campaign 提供一組可監視電子郵件傳遞的儀表板和工具。

[閱讀有關 Campaign Classic v7 的文件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hant){target="_blank"}以瞭解如何確認訊息是否傳送，如何監視執行，以及在發生錯誤時如何採取行動。

+++

+++ 是否可以監視工作流程執行？

在[此頁面](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}瞭解如何監視 Campaign 工作流程執行情況

+++

+++ 哪些系統和元件與 Campaign v8 相容？

在 [Adobe Campaign 相容性矩陣](compatibility-matrix.md)中，您可以取得 Campaign 最新建立支援的所有系統和組件清單。

+++

+++ 如何下載Campaign？

您可以從 Adobe 下載中心取得安裝程式和用戶端主控台。

以管理員使用者身分，存取Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/tw/campaign.html){target="_blank"}以下載Adobe Campaign。

在此頁面[上進一步瞭解發佈中心](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hant){target="_blank"}。

+++

+++ 如何記錄問題？

建立案例可讓您聯絡 Adobe 客戶支援團隊，瞭解您在 Adobe 產品上遇到的任何問題。為協助解決或疑難排解您的問題，您可使用 Adobe Admin Console 與 Adobe 客戶支援部門進行交談。

如要在該新系統中記錄問題或啟動聊天工作階段，請連結到 [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}。

此系統要求每個使用者都需要有新的個別帳戶，並擁有正確權限。 如果您發現無法使用 Adobe ID 登入，請透過 Experience League 請求存取權限，客戶服務團隊會盡快為您設定。[了解更多](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

加入 Campaign 社群：在現有問題中尋找答案或向專家提問。 [加入對話](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

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

+++ 我的 Campaign 版本是什麼？

從 Campaign 用戶端主控台的 **Help > About...** 功能表檢查您的[版本和建立編號](connect.md#ac-version)。

+++

+++ Campaign Classic v7和Campaign v8之間有何差異？

Campaign v8是新一代Campaign版本，專為Managed Cloud Services而設計。 它大幅改善基礎架構、安全性、傳遞能力及監控。

Adobe Campaign v8獨家以&#x200B;**受管理的Cloud Service**&#x200B;的形式提供，且無法部署在內部部署或混合環境中。

[進一步瞭解從Campaign Classic v7到v8](v7-to-v8.md)的轉換。

+++

+++ 如何設定使用者權限?

作為 Campaign 管理者，您可以為組織使用者設定權限。

有一套權限或限制可授權或拒絕執行以下操作：

* 存取特定功能
* 存取特定資料
* 建立、修改和/或刪除資料

[進一步瞭解](../start/gs-permissions.md)Campaign v8中的使用者許可權。

**相關主題：**

* [開始使用權限](gs-permissions.md)
* [管理使用者權限](manage-permissions.md)
* [新增資料夾權限](folder-permissions.md)

+++

+++ Campaign如何確保遵循並符合隱私權規範？

Adobe Campaign提供一套工具，以協助您遵循隱私權法規（GDPR、CCPA及其他隱私權法規）。

[進一步瞭解](../start/privacy.md)隱私權管理，以及Adobe Campaign所提供的協助您遵從隱私權要求的工具與功能。

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

* [開始使用工作流程](../config/workflows.md)
* [建置您的第一個工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"}
* [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [監視工作流程的執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

* [建立您的第一個傳遞](create-message.md) — 逐步指南
* [使用傳遞範本](../send/create-templates.md) — 節省使用範本的時間
* [傳遞最佳實務](delivery-best-practices.md) — 成功建議
* [定義電子郵件內容](../send/defining-the-email-content.md) — 內容建立選項
* [預覽和校樣](../send/preview-and-proof.md) — 傳送前測試
* [設定並傳送](../send/configure-and-send.md) — 要傳送的最後步驟
* [個人化內容](../send/personalize.md) — 新增動態個人化

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

* [開始使用簡訊](../send/sms/sms.md) — 完成簡訊指南
* [SMS傳送設定](../send/sms/sms-delivery-settings.md) — 組態選項
* [SMPP外部帳戶設定](../send/sms/smpp-external-account.md) — 提供者設定
* [建立SMS傳遞](../send/sms/create-sms.md) — 逐步建立
* [SMS內容](../send/sms/sms-content.md) — 內容設計手冊
* [傳送簡訊校樣](../send/sms/sms-proofs.md) — 測試簡訊
* [監視SMS](../send/sms/sms-monitor.md) — 追蹤和分析傳遞

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

* [建立並傳送推播通知](../send/push.md) — 完成推播指南
* [設定推播通知頻道](../send/push-settings.md) — 頻道設定
* [設計Android豐富推送](../send/rich-push-android.md) - Android豐富通知
* [設計iOS豐富推送](../send/rich-push-ios.md) - iOS豐富通知
* [設定資料彙集](../send/push-data-collection.md) — 新版的修訂整合方法
* [追蹤和監視](tracking.md) — 分析推播績效

+++

+++ 如何建立登陸頁面？

您可以使用Adobe Campaign數位內容編輯器來設計登入頁面，並定義與資料庫欄位的對應。

[在Campaign v8檔案中瞭解更多](../dev/landing-pages.md)。

您也可以使用Campaign網頁使用者介面來建立和發佈登入頁面 — [深入瞭解](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}。

+++

+++ 如何追蹤傳送內容？

您可以透過專用的[傳遞報告](../reporting/delivery-reports.md)追蹤與Campaign v8一起傳送的傳遞，然後監視您的傳遞。

在此頁面[中進一步瞭解Campaign ](../start/tracking.md)中的追蹤管理。

**相關主題：**

* [追蹤和監視訊息](tracking.md)
* [傳遞報告](../reporting/delivery-reports.md)
* [瞭解傳遞失敗](../send/delivery-failures.md)
* [設定追蹤的連結](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (Campaign Classic v7檔案)

+++

+++ 如何翻譯錯誤訊息？

出現了以外文顯示的錯誤訊息？[本頁面](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant){target="_blank"}列出所有錯誤訊息及其翻譯。

+++

+++ 我可以在 Campaign 中製作網路表單和收集解答嗎？

是。 使用&#x200B;**Campaign Web Applications &amp; Forms** （使用者端主控台）建立網路表單，以完整控制表單邏輯和驗證，或使用&#x200B;**Campaign登陸頁面** (Web UI)，搭配現代化的拖放介面以進行訂閱和潛在客戶產生。 兩者都會直接將資料收集到Campaign中，並整合自動化動作的工作流程。

[進一步瞭解Web應用程式和表單](../dev/webapps.md) | [Campaign Web UI登陸頁面](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8與舊版 {#v7-differences}

瞭解Campaign v8與舊版（Classic v7和Standard）之間的主要差異，包括架構、部署、移轉路徑和功能變更。

+++ Campaign v8和舊版之間有何主要差異？

Campaign v8是Adobe Campaign的完整再造，專為現代雲端原生架構而設計，並較Campaign Classic v7和Campaign Standard帶來重大改善：

**部署模型：**

* **v8：**&#x200B;僅限Managed Cloud Services — 完全由Adobe代管和管理
* **v7/Standard：**&#x200B;可用的內部部署、混合或託管選項
* **優點：**&#x200B;零基礎建設管理、自動擴充、企業級安全性

**架構與效能：**

* **v8：**&#x200B;具有PostgreSQL資料庫的增強型完整FDA (FFDA)架構
* **v8：**&#x200B;已針對處理數百萬個設定檔及大量傳送進行最佳化
* **v8：**&#x200B;大幅改善查詢效能與資料處理速度
* **優點：**&#x200B;大型作業和複雜行銷活動的效能更佳

**使用者介面：**

* **v8：**&#x200B;新的Campaign Web使用者介面以及使用者端主控台
* **v8：**&#x200B;回應式現代設計，提供更佳的使用者體驗
* **v8：**&#x200B;簡化的行銷活動建立和管理工作流程
* **優點：**&#x200B;更快上線、更輕鬆執行行銷活動、更易於存取

**升級與維護：**

* **v8：**&#x200B;由Adobe管理的自動升級 — 一律使用最新穩定版本
* **v7：**&#x200B;需要手動升級規劃和執行
* **優點：**&#x200B;減少維護負擔、立即使用新功能，無停機時間

**API與整合：**

* **v8：** Modern REST API具有增強的效能和可靠性
* **v8：**&#x200B;與Adobe Experience Cloud解決方案緊密整合
* **優點：**&#x200B;更輕鬆的整合、更好的互通性、現代開發實務

[進一步瞭解Campaign v8主要功能](whats-new.md)

**相關主題：**

* [從 Campaign Classic v7 到 v8](v7-to-v8.md)
* [從 Campaign Standard 至 v8](acs-to-v8.md)
* [Campaign v8 架構](../architecture/architecture.md)
* [護欄和限制](ac-guardrails.md)

+++

+++ 我應該從Campaign Classic v7或Campaign Standard移轉至v8嗎？

**Campaign v8適用於需要：**&#x200B;的組織

* **大量行銷活動** — 傳送數百萬封郵件，並改善效能和可靠性
* **企業擴充能力** — 提升資料庫與行銷活動，避免效能問題
* **新式網頁使用者介面** — 直覺式回應式Campaign網頁UI，可加快行銷活動建立速度並改善使用者體驗
* **雲端原生優點** — 利用自動更新、受管理基礎架構和彈性縮放
* **長期支援** - Campaign v8是Adobe的策略平台，並具備延伸支援，而舊版將在未來幾年內終止支援
* **降低IT負荷** — 消除基礎建設管理與升級規劃

**何時考慮移轉：**

* 您目前的Campaign執行個體會處理大量資料（數百萬個設定檔）
* 您遇到複雜工作流程或定位的效能問題
* 您想要降低基礎建設管理與維護成本
* 您需要與其他Adobe Experience Cloud解決方案緊密整合
* 您正計畫進行重大升級或重新整理基礎結構
* **您想要的是經得起未來考驗的技術** - Campaign Classic v7和Campaign Standard即將終止支援，讓v8成為策略性的長期解決方案
* **您的團隊需要現代化的介面** — 新的Campaign網頁UI為行銷人員提供更直覺、更易於存取的體驗

**移轉考量事項：**

* 自動移轉功能尚未推出 — Adobe提供移轉支援和指引
* v8僅限Managed Cloud Service （無內部部署或混合部署）
* 某些技術實作可能與v7不同 — 檢閱[相容性矩陣](compatibility-matrix.md)
* 資料移轉和測試需要規劃和資源

**後續步驟：**
請聯絡您的Adobe代表以：

* 評估您的移轉準備程度與時間表
* 瞭解使用案例的特定優點
* 規劃移轉策略與資源配置
* 存取移轉工具和支援

**相關主題：**

* [從Campaign Classic v7到v8](v7-to-v8.md) - v7使用者的詳細比較和移轉指南
* [從Campaign Standard到v8](acs-to-v8.md) — 標準使用者的移轉路徑
* [Campaign v8功能對照表](../start/compatibility-matrix.md)

+++

+++ 哪些Campaign Classic v7功能與v8不同或無法使用？

Campaign v8強化了大部分的Campaign Classic v7功能，但部分功能會因雲端原生架構而有所變更：

**在v8中無法使用：**

* **內部部署和混合式部署** - v8僅限Managed Cloud Services
* **直接資料庫存取** — 改用提供的API和工具
* **客戶管理基礎架構** - Adobe管理所有基礎架構

**v8中的不同實作：**

* **技術工作流程** — 某些針對雲端架構最佳化的工作流程可能會有不同的運作方式
* **資料庫結構** — 增強型FFDA架構可能需要結構描述調整
* **自訂整合** — 可能需要更新雲端架構
* **低階自訂** — 有些在受管理的環境中需要不同的方法

**在v8中增強或取代：**

* **組建升級** — 現在為自動(Adobe管理)而非手動
* **效能調整** — 由Adobe基礎架構最佳化處理
* **安全性修補程式** — 由Adobe自動套用
* **備份與復原** — 由Adobe管理，作為服務的一部分


**重要：**&#x200B;大部分的行銷與營運功能在v8中皆已推出並改善。 Adobe在雲端環境中管理技術和基礎架構層級功能。

[檢閱完整的相容性矩陣](compatibility-matrix.md)以取得詳細資訊。

**相關主題：**

* [護欄](ac-guardrails.md)
* [v7到v8轉換指南](v7-to-v8.md)

+++

## 輪廓與客群 {#audiences}

尋找管理設定檔、建立對象、匯入資料，以及定位行銷活動收件者的相關問題解答。

+++ 如何建立收件者？

在個別設定檔的使用者端主控台中手動建立收件者、從檔案(CSV/TXT)匯入以進行大量新增、使用網路表單進行自我註冊，或透過外部系統的API進行整合。 使用匯入工作流程進行週期性資料載入。

[手動建立設定檔](../audiences/create-profiles.md) | [從檔案匯入設定檔](../audiences/import-profiles.md) | [使用網路表單收集設定檔](../audiences/collect-profiles.md)

+++

+++ 如何匯入用戶檔案？

Campaign提供多種匯入方法：使用匯入精靈匯入簡單的檔案、針對複雜轉換以工作流程為基礎的匯入、利用來自SFTP的排程工作流程重複匯入，以及用於程式設計整合的API匯入。

針對檔案匯入，準備您的資料檔案（CSV/TXT、UTF-8編碼）、使用匯入精靈或工作流程、將欄對應到Campaign欄位、定義更新/插入規則，以及先以小型範例進行測試。 使用工作流程進行週期性匯入，並套用重複資料刪除規則。

[匯入資料指南](../start/import.md) | [週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ 如何定義行銷宣傳活動的目標母體？

Campaign提供多種鎖定目標方法：使用視覺條件建立查詢、鎖定現有清單或區段、從外部檔案(CSV、TXT)匯入收件者，或套用預先定義的篩選器。 您可以將條件與AND/OR邏輯結合、排除特定母體、使用控制組，以及分割A/B測試。 傳送前，請一律預覽目標母體大小。

[定義行銷活動目標](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant){target="_blank"} | [查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [建立對象](../audiences/create-audiences.md)

+++

+++ 如何建立用戶檔案清單？

清單是一組靜態的收件者名單，您可以在傳送時加以定位，並在行銷活動中重複使用。

**三種建立方法：**

* **手動建立：**&#x200B;瀏覽至&#x200B;**[!UICONTROL Profiles and Targets > Lists]**&#x200B;並按一下&#x200B;**[!UICONTROL Create]**。 從查詢、依個別選取專案或資料夾新增收件者。

* **工作流程自動化：**&#x200B;使用&#x200B;**[!UICONTROL List update]**&#x200B;活動自動從查詢結果或匯入的資料建立及維護清單。

* **匯入期間：**&#x200B;匯入設定檔時，請建立清單，以將設定檔儲存為可重複使用的群組。

>[!TIP]
>
>對於需要定期更新的清單，以及需要手動建立一次性區段的清單，請使用工作流程。

[建立對象](../audiences/create-audiences.md) | [清單更新活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ 如何在傳送訊息前排除重複的母體？

在工作流程中使用&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動，在傳遞前移除重複的收件者。 將其置於您的&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Delivery]**&#x200B;活動之間，然後選擇您的重複資料刪除條件（通常是電子郵件地址或收件者ID）以及要保留的記錄。

>[!TIP]
>
>傳送訊息前請一律刪除重複專案，確保每個人都只會收到您的訊息一次。

[重複資料刪除活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ 如何識別和鎖定新聞稿的訂閱者？

Campaign透過資訊服務自動追蹤電子報訂閱。 若要鎖定訂閱者：

* 使用&#x200B;**[!UICONTROL Query]**&#x200B;活動並篩選&#x200B;**[!UICONTROL Subscriptions]** >選取您的Newsletter服務
* 選擇&#x200B;**[!UICONTROL To > Subscribers of an information service]**，直接從您的傳遞鎖定訂閱者
* 使用&#x200B;**[!UICONTROL Subscription Services]**&#x200B;工作流程活動建立訂閱者清單

Campaign會追蹤訂閱/取消訂閱歷程記錄，並自動管理選擇加入/選擇退出。

[管理訂閱](../start/subscriptions.md) | [查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ 從目標母體中排除用戶檔案的最佳做法是什麼？

在工作流程中使用&#x200B;**[!UICONTROL Exclusion]**&#x200B;活動，從目標中移除不要的設定檔。 將其放在目標定位活動之後，並定義要排除的母體。

[排除活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ 我可以在Campaign中使用外部設定檔而不匯入它們嗎？

可以，Campaign v8可讓您使用儲存在外部資料庫中的外部設定檔，而不需將其載入到Adobe Campaign中。 [了解更多](../audiences/external-profiles.md)。

+++

+++ 如何建立傳送的測試設定檔？

測試設定檔是特殊的收件者，用來傳送校樣及驗證傳遞，而不會影響您的生產資料庫。 在&#x200B;**[!UICONTROL Profiles and Targets > Test profiles]**&#x200B;中建立這些收件者，或使用&#x200B;**[!UICONTROL Seed addresses]**&#x200B;功能自動將測試收件者新增至您的傳遞，以進行品質保證和收件匣監視。

[測試輪廓](../audiences/test-profiles.md)

+++

## 訊息設計 {#design}

瞭解如何在Campaign v8中設計有效的行銷訊息，包括電子郵件範本、個人化技巧和多語言內容。 在使用者端主控台中設計您的訊息，或在Campaign網頁UI中使用現代的&#x200B;**電子郵件Designer**，以獲得增強的視覺編輯體驗。

+++ 在Campaign中設計電子郵件的最佳實務是什麼？

重要准則：確保行動裝置回應式設計、使用與內嵌CSS相容的HTML 4.0/XHTML程式碼、使用替代文字最佳化影像（100KB以下）、使用個人化合併欄位、在傳送前跨電子郵件使用者端測試，以及包含純文字版本。 將總電子郵件大小調整為500KB以下以獲得最佳傳遞能力。

[電子郵件設計手冊](../send/email.md) | [傳遞最佳實務](delivery-best-practices.md)

+++

+++ 什麼是傳遞範本？

傳遞範本是預先設定的傳遞，可儲存所有設定和引數以供多個行銷活動重複使用。 範本包括目標規則、內容設計、個人化、技術設定（寄件者、回覆）和型別規則。 建立一次並重複使用，以維持一致性並加快行銷活動的建立。

[建立傳遞範本](../send/create-templates.md)

+++

+++ 在 Campaign 中可以輕鬆地匯入現有的 HTML 並製作電子郵件嗎?

是。 透過直接複製/貼上將HTML內容匯入內容編輯器、從電腦上傳檔案或從URL載入。 確認您的HTML使用與電子郵件相容的程式碼(HTML 4.0/XHTML)搭配內嵌CSS，並在公用伺服器上託管影像。 Campaign會自動新增個人化和追蹤至匯入的HTML。

>[!TIP]
>
>為獲得最佳的電子郵件設計體驗，請在Campaign網頁UI中使用&#x200B;**電子郵件Designer**，它提供現代拖放功能和內建回應式範本，而不是匯入原始HTML。

[匯入HTML內容](../send/defining-the-email-content.md)

+++

+++ 如何在 Campaign 中建立訂閱式新聞稿？

是。 使用Campaign的資訊服務來管理新聞稿訂閱。 主要功能包括自動選擇加入/選擇退出處理、訂閱追蹤、合規性管理(GDPR、CAN-SPAM)、多電子報支援、登錄檔單的Web整合，以及針對訂閱者的傳送作業。

[管理訂閱](../start/subscriptions.md)

+++

+++ 如何個人化訊息？

Campaign提供個人化功能，根據收件者資料、行為和偏好設定來建立相關的鎖定目標訊息。

**Personalization選項：**

* **個人化欄位** — 插入收件者資料(例如，`"Hello {{firstName}}")`
* **個人化區塊** — 使用預先定義或自訂的內容區塊
* **條件式內容** — 根據收件者條件顯示不同的內容
* **行為資料** — 運用瀏覽記錄、購買模式或參與量度

在傳送前測試個人化，以驗證合併欄位和條件邏輯是否正確運作。

[Personalization指南](../send/personalize.md) | [個人化欄位](../send/personalization-fields.md) | [條件式內容](../send/conditions.md)

+++

+++ 我可以傳送多國語言的訊息嗎？

是。 Campaign v8提供多語言功能，而&#x200B;**Campaign網頁UI**&#x200B;提供最簡單的方法。 Web UI提供具有語言變體的原生多語言傳送，可將語言變體新增至您的傳送中，且Campaign會根據收件者偏好的語言自動傳送適當版本。 可用於電子郵件、推播通知、簡訊與交易式訊息。

主要功能：自動內容複製、自動語言傳送、預設語言後援及簡易的變體管理。

使用者端主控台也支援使用條件式內容和工作流程的多語言內容，但需要更多手動設定。

[多語言傳送(Web UI)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [條件式內容（使用者端主控台）](../send/conditions.md)

+++

+++ 可以將網頁表單當地語系化嗎？

是。 Campaign網頁應用程式支援多語言本地化。 定義所有表單元素（標籤、按鈕、訊息、錯誤文字）的翻譯，並根據收件者設定檔或瀏覽器設定自動偵測語言。 單一Web應用程式支援多種語言版本，必要時可遞補為預設語言。

[網頁應用程式本地化](../dev/webapps.md)

+++

+++ 我可以在電子郵件中使用AI支援的內容嗎？

是，但&#x200B;**只能透過Campaign Web UI**。 由Microsoft Azure OpenAI和Adobe Firefly提供支援的AI小幫手，可跨電子郵件、簡訊和推播通知建立專業且品牌一致的內容。

**主要功能：**

* 產生文字（電子郵件復本、主旨列、簡訊/推播內容）與品牌一致的影像
* 建立針對不同受眾最佳化的內容變數
* 精簡內容（精緻、摘要、改寫、簡化）
* 上傳品牌資產並取得品牌一致性分數
* 使用現有內容作為參考和上傳樣式參考影像

>[!NOTE]
>
>AI助理僅適用於Campaign網頁UI，目前僅支援英文。 使用者需要適當的許可權，而且必須同意使用者協定。

[AI助理概述](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI助理使用案例](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [品牌一致性](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 測試和傳送訊息 {#send}

瞭解測試、驗證、傳送和追蹤行銷訊息的最佳實務，以確保成功傳遞行銷活動。

+++ 什麼是傳遞分析？

傳遞分析是Campaign在傳送前執行的驗證階段。 它會計算目標母體、驗證內容、檢查錯誤、套用型別規則，以及估計傳遞量。

Campaign產生顯示警告和錯誤的記錄。 錯誤會封鎖傳送，且必須修正；警告為建議。 傳送前，請務必檢閱分析記錄。

[傳遞分析指南](../send/delivery-analysis.md)

+++

+++ 為何要建立測試？

校樣是測試訊息，可在傳送給主要受眾之前驗證您的傳送內容。 使用校樣來驗證個人化、測試電子郵件使用者端間的內容轉譯、確認連結和追蹤工作、檢查影像和附件，以及驗證行動回應。

校訂有助於在錯誤觸及數千個收件者之前鎖定錯誤、啟用利害關係人核准並測試收件匣位置。 將校樣傳送至多個電子郵件使用者端和裝置，並一律在生產傳送前取得核准。

[校訂和預覽指南](../send/preview-and-proof.md)

+++

+++ 如何在 Adobe Campaign 中使用種子地址？

種子地址是特殊收件者，會自動新增至每次傳遞，以進行測試、品質保證和監控，不符合您的目標條件。 適合用於持續監控、收件匣位置測試、直接郵件驗證和利害關係人可見度。

**與校訂的主要差異：**

* **種子地址** — 自動新增到生產傳遞，計入傳送量
* **校訂** — 測試會在生產前傳送，不會計入磁碟區，用於驗證

管理&#x200B;**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;中的種子地址。 保持小清單以避免影響傳遞量度。

[種子地址指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ 如何設定傳送訊息前的驗證過程？

Campaign提供核准工作流程，以確保訊息在傳送前符合品質標準。 在行銷活動或傳遞層級設定內容、目標、擷取（直接郵件）和預算的核准。

**安裝程式：**

在&#x200B;**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;中建立操作員群組，然後在行銷活動或傳遞屬性中指派核准群組。 Campaign會傳送通知電子郵件給可核准、拒絕或要求變更的稽核者。

**對於獨立傳送（不在行銷活動中）：**

使用&#x200B;**校訂作為您的核准程式**。 將校訂傳送至您的核准組進行驗證，並進行變更後一律傳送新校訂，以確保利害關係人檢閱最新版本。

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

[設定波段傳送](../send/configure-and-send.md#sending-using-multiple-waves)

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


>[!TIP]
>
>使用Campaign網頁UI，透過現代設計工具以更快、更直覺的方式建立電子郵件。 使用使用者端主控台進行複雜的目標定位或進階的工作流程型行銷活動。

[建立您的第一封電子郵件](create-message.md) | [電子郵件設計手冊](../send/email.md)

+++

+++ 如何排程傳遞？

Campaign可讓您排程傳送以利未來傳送，最佳化傳送時間並協調行銷活動。

**排程選項：**

* **傳遞屬性** — 立即傳送、排程為特定日期/時間，或依時數/天遞延
* **行銷活動層級** — 協調行銷活動內的所有傳遞
* **工作流程排程器活動** — 適用於週期性傳遞、複雜模式和事件觸發的行銷活動

Campaign也支援聯絡日期最佳化（每個收件者的最佳傳送時間）和時區調整（所有收件者的相同當地時間）。

[排程傳遞傳送](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ 我可以將附件新增至電子郵件嗎？

是。 Campaign支援靜態附件（所有收件者的相同檔案）和個人化附件（根據設定檔資料，每個收件者的不同檔案）。 在傳遞屬性的&#x200B;**[!UICONTROL Attachments]**&#x200B;區段中新增附件。

**重要考量：**

* 將附件保持在1MB以下，以獲得最佳傳遞能力
* 附件可能會觸發垃圾郵件篩選器；請在傳送前進行徹底測試
* 避免電子郵件使用者端(.exe、.zip、.js)通常會封鎖的檔案型別
* 若為大型檔案，請考慮改用追蹤的下載連結

使用安全的檔案格式(PDF、JPEG、PNG、DOCX)並在生產傳送之前使用種子地址進行測試。

[電子郵件附件指南](../send/email.md#attachments)

+++

+++ 如何在電子郵件傳送中設定追蹤連結？

Campaign會自動將電子郵件中的所有URL轉換為追蹤連結，以監視收件者參與情形。 存取傳遞中的&#x200B;**[!UICONTROL Tracking]**&#x200B;區段以設定每個連結的追蹤設定。

**組態選項：**

* **啟用/停用追蹤** — 每個連結的控制追蹤
* **連結標籤** — 新增描述性的報表名稱(例如「立即購買CTA」)
* **連結類別** — 依彙總分析型別將連結分組
* **追蹤型別** — 追蹤點按次數、開啟次數或兩者

Campaign會追蹤內容連結、映象頁面連結、取消訂閱連結，並可包含電子郵件開啟次數的可選追蹤畫素。 使用有意義的標籤和類別來簡化報表，並快速找出高效能的內容。

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

>[!TIP]
>
>定期監視隔離清單。 提高隔離率通常表示資料品質問題在影響寄件者信譽之前需要注意。

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

* [建立工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"}
* [工作流程活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

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

* [匯入最佳實務](../start/import.md)
* [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [週期性匯入工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ 是否可以監視工作流程執行？

是。 Campaign提供全方位的工作流程監控功能，以追蹤執行、識別問題並最佳化效能。

**監視選項：**

* **工作流程儀表板** — 檢視即時執行狀態、進度和活動狀態
* **執行記錄** — 存取每個活動和轉換的詳細記錄
* **稽核軌跡** — 追蹤工作流程修改和執行歷史記錄
* **警示和通知** — 設定失敗或特定狀況的電子郵件警示

**主要監視功能：**

* 視覺狀態指示器（擱置中、進行中、已完成、失敗）
* 效能最佳化的執行時間追蹤
* 疑難排解的活動層級錯誤訊息
* 視需要暫停、停止或重新啟動工作流程

從&#x200B;**[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]**&#x200B;或直接從工作流程儀表板存取監視。

**相關主題：**

* [監視工作流程的執行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}
* [工作流程最佳實務](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [開始工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=zh-Hant){target="_blank"}

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

* [更新資料活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}
* [資料管理活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

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

* [資料管理活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [目標工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"}
* [擴充活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Personalization指南](../send/personalize.md)
* [工作流程使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant){target="_blank"}
* [擴充活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [分割活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"}
* [A/B測試指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

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

* [匯入資料指南](../start/import.md)
* [資料載入活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [更新資料活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

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

* [查詢活動](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}
* [使用彙總](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}
* [歡迎計畫](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hant){target="_blank"}

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

* [目標定位活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}
* [流量控制活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}
* [動作活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}
* [事件活動參考](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

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

* [工作流程最佳實務指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [建立工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hant){target="_blank"}
* [監視工作流程](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campaign設定 {#settings}

使用正確的設定、整合和設定來設定您的Campaign執行個體，以最佳化行銷操作。

+++ 我可以變更 Campaign 介面的語言嗎？

在建立執行個體時可以選取 Campaign 語言。之後您將無法進行變更。如需詳細資訊，請參閱[本章節](../start/connect.md)。

Adobe Campaign使用者介面提供多種語言版本：英文、法文、德文、日文等。 請注意，用戶端主控台和伺服器必須設定相同的語言。每個 Campaign 執行個體只能選取一種語言。

如果是英文，在安裝 Campaign 時，您可以選取美式英文或英式英文：它們的日期和時間格式有所不同。

+++

+++ 我可以將Campaign v8搭配其他Adobe解決方案搭配使用嗎？

您可以將 Adobe Campaign 的傳遞功能和進階行銷活動管理功能與協助您個人化使用者體驗的解決方案結合使用。

[瞭解如何使用其他Adobe解決方案](../connect/integration.md)和[如何在Campaign中設定IMS](../start/connect.md)。

+++

+++ 如何在 Campaign 實例上設定追蹤功能？

身為經驗豐富的使用者，您可以在Campaign執行個體上設定追蹤功能。

[了解更多](../start/tracking.md)。

+++

+++ 如何設定電子郵件傳遞機制?

除了[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}，請檢閱傳遞能力技術建議，以瞭解如何設定執行個體，以充份發揮Campaign傳遞功能。

[了解更多](../send/about-deliverability.md)。

+++

+++ 如何實作內容核准？

Campaign 可以讓您以協作模式，針對行銷活動的主要步驟設定核准流程。您可以針對每個行銷活動，核准傳遞目標、內容和成本。可以以電子郵件的形式通知負責核准的Adobe Campaign操作者，然後他們可透過主控台或網路連線核准或拒絕核准。

[瞭解更多](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hant){target="_blank"}並探索在Campaign中實作傳遞內容核准的步驟。

+++

+++ 如何存取在外部資料庫中存儲的資料？

Adobe Campaign 提供同盟資料存取 (FDA) 選項，以處理儲存在一或多個外部資料庫中的資訊：您不需要變更 Adobe Campaign 資料的結構就可以存取外部資料。

[了解更多](../connect/fda.md)。

+++

+++ 我可以將 Campaign 連線到哪些外部資料庫？

[相容性矩陣](compatibility-matrix.md)中列有透過同盟資料存取 (FDA) 與 Campaign 相容的外部資料庫。

+++

+++ Adobe Campaign可以與CRM系統整合嗎？

Adobe Campaign 提供各種 CRM 連接器，用於將您的 Adobe Campaign 平台連結至您的第三方系統。透過這些 CRM 連接器，您可同步處理連絡人、帳戶、購買等。有了這些 CRM 連接器，您可以將您的應用程式與各第三方和企業應用程式輕鬆整合。

這些聯結器可讓您快速輕鬆地整合資料：Adobe Campaign提供專用的助理，可從CRM提供的表格中進行收集和選取。 並且可確保雙向同步處理，讓整個系統中的資料隨時保持最新。

[深入瞭解](../connect/crm.md)如何將CRM工具與Adobe Campaign同步。

+++

+++ 如何清除使用者端主控台快取？

如果您有新商標無法正確反映的問題，或匯出資料的問題，您可能需要清除使用者端主控台快取。

登出並關閉使用者端主控台。 根據您的作業系統，導覽至下列位置：

* Windows： `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* Mac： `~/Library/Application Support/Neolane/NL_5/`

刪除XML組態檔（保留`nlclient_cnx.xml`），然後重新登入使用者端主控台。

+++

+++ 我可以設定使用者介面設定嗎？

可以，身為管理員，您可以自訂使用者的Campaign UI設定。 [了解更多](../config/ui-settings.md)。

+++

+++ 我可以建立自訂欄位和表格嗎？

可以，Campaign v8可讓您使用自訂欄位和表格來擴充資料模型。 瞭解如何[擴充結構描述](../dev/extend-schema.md)。

+++

## 報告 {#reporting}

深入瞭解Campaign的報告功能，包括內建報表、自訂報表和資料分析工具，例如多維度資料集。

+++ 如何建立新報表？

除了內建報告之外，透過使用 Adobe Campaign，可以讓您在不同的工作環境中根據不同的需求產生報告。

Adobe Campaign 不是專門用於報告的工具：在 Adobe Campaign 中建立的報告主要為讓您檢視彙總的資料。

[進一步瞭解](../reporting/gs-reporting.md)Campaign報告功能。

+++

+++ 如何設計並分享母體的靜態報表？

Adobe Campaign [描述性分析報告](../reporting/built-in-reports.md)可讓您針對母體設計並分享靜態報告。

[了解更多](../reporting/built-in-reports.md)。

+++

+++ 如何在我的資料上設計進階報表？

使用Campaign v8，您可以[建立進階報告](../reporting/custom-reports.md)。 身為資深使用者，您將能夠對您的資料建立、更新和分發自訂報告。

您也可以使用Campaign Web使用者介面來建立報告和儀表板。 [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}。

+++

+++ 何謂立方體以及如何建立這類報表？

您可以擴充資料庫的探索和分析能力，同時讓最終使用者更容易設定報告和表格：他們只需在建立其報告或表格時，選取現有的（全設定好的）多維度資料集，以處理計算、測量和統計數據。

建立並設定多維度資料集後，便可以用於報告查詢方塊和網頁應用程式；可以在樞紐分析表內使用及操作多維度資料集。

瞭解如何[使用多維度資料集探索資料](../reporting/gs-cubes.md)。

+++

+++ 我可以利用線上意見調查結果建立報表嗎？

Campaign v8沒有內建調查功能。 您可以使用Adobe Experience Manager或其他網路解決方案來建立調查。

不過，您可以使用報告功能來分析任何收集的資料並建立自訂報告。

+++

+++ 如何在Campaign介面共用報表的存取許可權？

您可以在 Adobe Campaign UI 定義報告將顯示在哪些內容。如需關於報告存取權限的詳細資料，請參閱[此章節](../reporting/custom-reports.md)。

+++

+++ 我可以匯出不同格式的報告嗎？

可以，您可以Excel、PDF或CSV等不同格式匯出Campaign報表。 [了解更多](../reporting/custom-reports.md)。

+++

## 開發人員 {#developers}

存取開發人員的技術資訊，包括資料模型詳細資訊、結構描述、API和自訂功能。

+++ 什麼是Campaign資料模型？

Adobe Campaign 資料庫的概念資料模型由一組內建表格及其互動組成，並以 XML 描述了應用程式中資料的實體和邏輯結構。它遵循Adobe Campaign特有的語法，稱為結構描述。

[深入了解 Campaign 資料模型](../dev/datamodel.md)。

[此頁面列出最佳做法](../dev/datamodel-best-practices.md)。

+++

+++ 如何使用 Campaign 綱要？

在 Adobe Campaign 中，資料結構描述用於：

* 定義應用程式內資料物件與基礎資料庫表的連結方式。
* 定義 Campaign 應用程式中不同資料物件之間的連結。
* 定義及描述每個物件中包含的個別欄位。

[開始使用資料表和結構描述](../dev/schemas.md)以瞭解如何使用資料結構描述、擴充和自訂Campaign，以滿足您的需求。

+++

+++ 如何使用自訂的收件者表格？

您可以在Campaign中建立並實作非內建的收件者表格，以傳送訊息。

[了解更多](../dev/custom-recipient.md)

+++

+++ 在 Campaign 中定義查詢的最佳做法是什麼？

Adobe Campaign 查詢編輯器是一種功能強大的工具，可探索資料和建立區段。

您可以在軟體的多個層級上找到 Adobe Campaign 查詢工具：建立目標群體、劃分客戶、擷取和篩選追蹤記錄、建立篩選器等。

您可以使用一般查詢編輯器查詢 Campaign 資料庫。可透過 **Tools > Generic query editor...** 功能表存取一般查詢編輯器。透過它，您可擷取儲存在資料庫中的資訊，將其整理、分組、排序等操作。例如，使用者可以在新聞稿的連結上，還原在給定時間內按一下連結超過 [n] 次以上的收件者。透過這個工具，您可根據您的需求收集、排序和顯示結果。

[進一步瞭解](../start/query-editor.md)。您也可以參閱[Campaign自動化指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}。

+++

+++ 如何匯入資料包？

使用 Adobe Campaign，您可以透過資料包系統匯出或匯入平台配置和資料。資料包可以 XML 格式檔案的形式顯示 Adobe Campaign 資料庫的實體。資料包中包含的每個實體都會以其所有資料表示。

資料包用於匯出資料配置，並將它整合到另一個 Adobe Campaign 系統中。

[深入瞭解](../dev/packages.md)如何使用資料包匯入和匯出Campaign設定。

+++

+++ 我可以在哪裡找到Campaign v8 API清單？

[本專屬文件](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant){target="_blank"}提供所有 Campaign API，及個別完整說明。

+++

+++ 什麼是Campaign REST API？

Campaign v8公開了一組REST API，可讓您建立Adobe Campaign的整合，並將Adobe Campaign與您使用的技術面板結合，以建立您自己的生態系統。

[了解更多](../dev/api/get-started-apis.md)。

+++

+++ 如何透過API監視工作流程？

在[此專屬頁面](../dev/api/controlling-a-workflow.md)中瞭解如何使用Campaign API監視工作流程。

+++

+++ 如何更新資料庫結構？

如果您修改Campaign資料結構，則需要更新資料庫結構。 在[本節](../dev/update-database-structure.md)中瞭解如何操作。

+++

+++ Campaign v8有哪些限制？

相較於Campaign Classic v7，Campaign v8有一些限制，詳情載於[此頁面](../start/v7-to-v8.md#limitations)。

+++

## 隱私權 {#privacy}

瞭解Adobe Campaign如何協助您遵守GDPR和CCPA等隱私權法規，以及管理資料主體請求。

+++ 隱私權的主要條款為何？

以下所列出的項目會連結至 Adobe Campaign 中與隱私權和同意相關的主要條款與概念：

* [隱私權管理法規](../start/privacy.md#privacy-regulations)
* [個人資料與角色](../start/privacy.md#personal-data)
* [存取權限與被遺忘的權利](../start/privacy.md#right-access-forgotten)
* [同意、保留和角色](../start/privacy.md#consent-retention-roles)

+++

+++ 對 Adobe Campaign 遵守最新隱私權法規有何建議？

Adobe 不提供法律建議。您應該與自己的法律顧問合作，確保他們採取一切必要步驟，以便做好 GDPR、CCPA、PDPA、LGPD 或任何其他適用法規的準備。

**準備資料存取和刪除請求**

* 識別接收/回應資料主體請求的過程，包括指定隱私權聯絡點。

* 審查儲存在 Adobe Campaign 中的各種客戶資料，並確定唯一識別碼（可能不止一個）。

* 確定資料主體身份確認的驗證/驗證政策和過程。

* 請確定資料主體的回應易於理解。

**考慮同意**

* 視需要列出並更新 GDPR 資料擷取的所有接觸點（例如，考慮語言、同意機制和同意記錄檔）。

* 請確定所有行銷電子郵件都包含取消訂閱的連結。

* 評估電子郵件行銷的全球策略，以決定地理特定的實施。

**瞭解您的資料**

* 審查所有資料匯入並擷取資料流入 Adobe Campaign 的來源，以及記錄用於行銷工作的欄位。

* 從您的 Adobe Campaign 資料庫移除任何未使用的資料屬性。

* 使用 Adobe Campaign 中可用的資料來擷取資料，並為收件者提供更佳的個人化體驗。

* 審查和更新資料存取權限以協助確保 Adobe Campaign 的使用者僅能充分運用執行其促銷活動所需的資料，但不能存取其他資料。

* 確保 Adobe Campaign 的每位使用者都擁有執行其所需工作的適當存取權，但沒有執行其他工作的任何其他權利。

+++

+++ 資料控制方如何在對使用者參與影響最小的情況下獲得同意？

在某些行銷活動需要同意的情況下，消費者同意需要有效（即沒有沉默作為同意或預先選取的核取方塊）、未捆綁銷售，並且可能不以提供服務為條件。

有時甚至需要重新整理某些同意，才能繼續使用後續的資料。

行銷人員應將這些改善的同意要求視為品牌參與度、忠誠度以及客戶滿意度與信任的真正指標。

+++

+++ 資料控制方如何在 Adobe Campaign 中管理同意？

與大多數行銷人員透過自訂資料欄位或一個或多個服務善用的情況相比，Adobe Campaign 已經提供了在更高層級上管理同意的功能。

行銷人員應洽詢其法律顧問，以取得如何進行的指引，然後善用 Adobe Campaign 中內建的功能。

例如，將 Adobe Campaign 中的資料模型擴充為不僅在人們選擇加入時追蹤，還可追蹤選擇加入的時間標記，以及擷取精確同意範圍的某類指標。

+++

+++ Adobe Campaign 中的資料控制方可以根據資料主體的客戶請求刪除哪些資料？

所有與資料主體相關的資料都會被刪除，包括現成可用的表格和自訂表格。

技術上，所有連結至資料主體相關`integrity="own"`的資料都將被刪除。

作為資料控制方，您可以選擇透過更改資料結構描述中定義的連結的完整性來自訂此內容（例如，若您有商業理由不刪除某些資料）。

+++

+++ 刪除傳送和追蹤記錄時，報告會受到哪些影響？

Adobe Campaign 中的報告是以根據來自傳送和追蹤記錄彙總資料計算的指標為基礎。因此，移除個別記錄檔時，不應該影響報告上顯示的度量。

+++

+++ 我是否需要留意稍後可能重新匯入資料？

在Adobe Campaign中，記錄通常會從外部資料來源上傳。

作為資料控制方，您需要確保在收到刪除請求時，從所有系統刪除資料主體的所有必要資料。

+++

+++ 可以將資料已從 Adobe Campaign 中清除的資料主體，於稍後再次選擇加入嗎？

資料主體可以選擇再次加入，或在 Adobe Campaign 將其資料清除後，以新收件者身分加入。

您可以使用稽核軌跡，其詳細說明上次執行刪除的時間以及建立新收件者的時間。

+++

## 仍需要協助嗎？ {#get-help}

找不到您要尋找的內容？ 以下是協助您成功使用Adobe Campaign v8的其他資源。

### 社群支援

與其他Campaign使用者和Adobe專家交流，以分享知識並獲得答案。

* **[Adobe Campaign社群](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** — 提出問題、共用解決方案，以及與Campaign社群連絡
* **[Experience League論壇](https://experienceleaguecommunities.adobe.com/){target="_blank"}** — 瀏覽所有Adobe產品的討論
* **[Campaign社群辦公時間](https://experienceleague.adobe.com/){target="_blank"}** — 與Adobe專家一起加入即時會議

### 檔案與學習

存取全方位的指南、教學課程和訓練教材。

* **[Campaign v8檔案首頁](../campaign-home.md)** — 完整產品檔案
* **[Campaign教學課程](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"}** — 逐步影片指南和實作教學課程
* **[新增功能](whats-new.md)** — 最新功能
* **[發行說明](release-notes.md)** — 目前和先前的發行資訊
* **[最佳實務](delivery-best-practices.md)** — 常見工作的建議方法

### 技術資源

尋找詳細的技術檔案和開發人員資源。

* **[Campaign API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant){target="_blank"}** — 完整API參考檔案
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** — 協助撰寫說明檔案
* **[技術說明](https://experienceleague.adobe.com/zh-hant/docs/campaign/technotes-ac/technotes-home){target="_blank"}** — 深入的技術文章
* **[相容性矩陣](compatibility-matrix.md)** — 支援的系統和版本

### 支援與服務

取得Adobe支援團隊的協助並管理您的執行個體。

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** — 記錄支援案例並管理使用者
* **[Adobe客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** — 聯絡支援團隊
* **[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant){target="_blank"}** — 管理您的Campaign執行個體設定
* **[系統狀態](https://status.adobe.com/){target="_blank"}** — 檢查Adobe服務狀態

### 培訓與認證

透過官方的Adobe培訓和認證計畫提升您的技能。

* **[Adobe數位學習服務](https://learning.adobe.com/){target="_blank"}** — 官方講師授課和自訂進度課程
* **[Adobe Campaign認證](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** — 以專業認證驗證您的專業知識
* **[Experience League學習路徑](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** — 引導式學習歷程

### 其他實用資源

* **[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=zh-Hant){target="_blank"}** - Classic v7使用者的參考
* **[Campaign Web UI檔案](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/campaign-web-home){target="_blank"}** — 新的Web介面指南
* **[傳遞能力最佳實務](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant){target="_blank"}** — 最佳化電子郵件傳遞
* **[產品更新](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** — 最新的Adobe Experience Cloud更新

**上次更新日期：** 2025年11月 | **套用至：** Campaign v8.6和更新版本

*發現錯誤或想建議改進嗎？ [在GitHub上編輯此頁面](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

