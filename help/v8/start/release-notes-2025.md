---
title: Campaign v8 (主控台) 2025 發行說明
description: 2025 Campaign v8版本的功能和改進清單
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '3472'
ht-degree: 33%

---

# 2025 年發行說明 {#2025-rn}

本頁面列出 **2025 Campaign v8 版本**&#x200B;附帶的新功能、改善和修正。如需最新版本，請參閱[此頁面](release-notes.md)。

對於任何新的實作或升級至現有環境，請安裝[最新版本](release-notes.md)。

>[!BEGINSHADEBOX]

**在此頁面中**

* [發行版本 8.8.2](#release-8-8-2)
* [發行版本 8.6.5](#release-8-6-5)
* [發行版本 8.6.4](#release-8-6-4)
* [發行版本 8.7.4](#release-8-7-4)
* [發行版本 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## 發行版本 8.8.2 {#release-8-8-2}

_2025 年 10 月 9 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。

### 新功能 {#features-8-8-2}

**新的SMS傳送聯結器**&#x200B;現在可用於[Campaign FFDA部署](../architecture/enterprise-deployment.md)。 請參閱[詳細檔案](../send/sms/sms.md)。

此版本也隨附Campaign Web使用者介面提供的一組功能：

* [交易式訊息中的設定檔擴充](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=zh-Hant){target="_blank"}
* [異動訊息、推播通知和簡訊的多語言功能](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=zh-Hant){target="_blank"}

請參閱Campaign Web UI [發行說明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hant){target="_blank"}

### 修正 {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* 修正可能導致資料庫清理工作流程失敗的問題。 (NEO-87949)
* 修正分散式行銷中，未針對合作行銷活動傳遞記錄追蹤資料的問題。 (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* 修正片段中個人化無法正常運作的問題。 (NEO-88161)
* 修正移轉至新Redshift ODBC聯結器後，可能導致分割工作流程活動因SQL錯誤而失敗的問題。 (NEO-87466)
* 修正工作流程中可能導致排除計數不正確的問題。 (NEO-89207)
* 修正可能導致推播通知的點按指標不正確的問題。 (NEO-89503)
* 修正SMS傳送記錄檔未正確更新，導致Adobe Campaign無法正確報告狀態的問題。 (NEO-88479)
* 修正傳送內容中，法文引號錯誤轉換為英文引號的問題。 (NEO-89631)
* 修正Real-Time Server針對無效的IMS權杖傳回錯誤回應代碼的問題。 (NEO-87428)
* 修正電子郵件和簡訊的傳遞統計資料未完全重新計算，導致成功指標不準確的問題。 (NEO-88106)
* 修正新SMS傳送聯結器的問題，該問題導致傳送記錄錯誤指派一小部分訊息的傳送狀態。 (NEO-89581)
* 修正新SMS傳送聯結器的問題，該問題導致成功量度傳遞未在行銷和中間伺服器上正確更新。 (NEO-89850)
* 修正即時和行銷執行個體之間的同步問題，此問題會導致遺失追蹤記錄及不正確的報表。 (NEO-90247)
* 修正在自訂結構中選擇兩個連續1-N連結的欄位時，可能會導致錯誤的工作流程擴充問題。 (NEO-87682)

## 發行版本 8.8.1 {#release-8-8-1}

_2025年7月9日_

### 新功能 {#features-8-8-1}

先前為少數客戶所發行，現在下列功能適用於所有Campaign FDA環境：

* **新的SMS傳送聯結器** - SMS傳送聯結器已經過現代化與改善，可啟用收發器模式SMPP連線、啟用永久性SMPP連線，並確保更好的相容性。 新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。我們仍支援現有的實施，但建議改用此全新的現代化擴充聯結器。 如果您想要轉換為新聯結器，請聯絡Adobe。 [閱讀更多](../send/sms/sms.md)

  >[!NOTE]
  >
  >此功能&#x200B;**不**&#x200B;可用於[Campaign FFDA部署](../architecture/enterprise-deployment.md)。

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=zh-Hant)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html?lang=zh-Hant){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=zh-Hant){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html?lang=zh-Hant#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hant#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hant#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hant#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=zh-Hant){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=zh-Hant#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hant#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

下列功能先前以「有限可用性」發行，現在可於&#x200B;**依需求提供**：

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-Hant){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **Rest API** — 您現在可以使用Rest API來建立Adobe Campaign的整合，並將Adobe Campaign與您使用的技術面板結合，以建立您自己的生態系統。 異動訊息REST API也適用於SMS頻道。 當承載中同時存在 email 和 mobilePhone 時，您可以使用「wishedChannel」欄位來指定管道。如果未提供，除非 wishedChannel 明確地要求簡訊，否則預設會使用電子郵件。事件型異動API也可用於電子郵件。 [閱讀更多](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >此功能&#x200B;**不**&#x200B;可用於[Campaign FFDA部署](../architecture/enterprise-deployment.md)。

* **一鍵式清單 — 取消訂閱** — 由於主要ISP要求寄件者允許收件者只要按一下即可立即選擇退出，您現在可以直接從電子郵件範本或傳遞屬性在使用者介面中啟用「一鍵式清單 — 取消訂閱」標題。 此選項預設為啟用。 [閱讀更多](../send/email-parameters.md#one-click-list-unsubscribe)

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

除了上述功能以外，此版本也隨附Campaign Web使用者介面提供的一組功能：

* [建立多語言傳遞](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=zh-Hant#multilingual-delivery){target="_blank"}
* [傳遞提醒](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=zh-Hant){target="_blank"}
* [登陸頁面改善](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html?lang=zh-Hant){target="_blank"}
* [動態報告](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=zh-Hant){target="_blank"} （隨選）
* [集中式品牌](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=zh-Hant){target="_blank"} （隨選，新實作）

請參閱Campaign Web UI [發行說明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hant){target="_blank"}

### 一般改善 {#improvements-8-8-1}

* Microsoft網狀架構現在可支援作為具有Adobe Campaign同盟資料存取(FDA)的外部資料庫。 [閱讀更多](../config/external-accounts.md#transfer-data-external-accounts)
* Campaign v8現在支援Android 15和iOS 18的推播通知。 [閱讀更多](../start/compatibility-matrix.md#MobileSDK)
* 除了用於安全虛擬私人網路通道的內部部署資料庫外，現在也支援雲端資料庫。 [閱讀更多](../config/enhanced-security.md#vpn-databases)
* 已在SMS 2.0聯結器的「傳入流量」區段中新增一組新的「提供者ID」欄位。 [閱讀更多](../send/sms/smpp-external-account.md#incoming-traffic)
* 透過「mailto」List-Unsubscribe方法取消訂閱的收件者，不再傳送至隔離區。 他們或是從與傳送相關聯的服務取消訂閱，或是傳送到封鎖清單（設定檔的「不再聯絡」區段），前提是沒有為傳送定義服務。 [閱讀更多](../send/quarantines.md)
* Adobe Campaign使用者端主控台現在提供收件匣轉譯報告的改良版本。
* 已將`setup-client.exe`檔案取代為`ac-client.msi`檔案，提供更簡單的方法，讓系統管理員不需要使用者介入即可執行大量升級。

### 修正 {#fixes-8-8-1}

* 修正由於SMS 2.0中的有效期間無效而未收到自動回覆的問題。這可確保在移轉後正確傳送訊息。 (NEO-88088)
* 解決SMS 2.0中`inSms`表格中某些欄位未正確更新的問題，確保SMS功能可正確插入資料。 (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* 修正SQL查詢中遺失或不正確資料行參考所造成的資料庫清理工作流程失敗。 這可確保正確清除記錄檔和訪客資料。 (NEO-86813)
* 解決傳送記錄中缺少事件日期的問題。 此修正可確保事件日期母體的準確性，對排程的觸發器和工作流程至關重要。 (NEO-86708)
* 修正SMS 2.0中的SMS傳遞記錄插入問題，確保`nmsBroadLogMid`表格中的記錄正確。 (NEO-86556)
* 已解決直接郵件範本中外部傳遞模式的檔案擷取問題，確保相容性和功能。 (NEO-86520)
* 解決涉及跨多個MID執行個體分割路由的傳送處理問題，確保準確傳送狀態更新和輸送量。 (NEO-86500)
* 修正從Campaign Standard移轉至Campaign v8後，動態報告中遺失的追蹤資料，確保傳遞追蹤記錄的準確報告。 (NEO-86419)
* 解決觸發工作流程執行兩次導致重複金鑰違規問題的工作流程。 此修正可確保正確處理及執行事件。 (NEO-86154)
* 修正Redshift OOTB SQL函式部署後的相容性問題，確保在工作流程中正確執行`GetDate()`等函式。 (NEO-85834)
* 已解決附加URL時影像消失的電子郵件組建中的轉譯問題。 此修正可確保在收件匣預覽中正確顯示影像。 (NEO-85716)
* 更正WebUI中捲曲引號的呈現方式，確保電子郵件傳送中字元顯示準確。 (NEO-85687)
* 修正映象頁面連結功能，確保映象頁面中的語言變體之間可正確導覽。 (NEO-85625)
* 解決Web App日期選擇器中的日期格式問題，確保與日文日期格式(`yyyy-mm-dd`)相容。 (NEO-85234)
* 修正了中間來源中替代製程設定的後處理工作流程問題，確保正確執行工作流程。 (NEO-85111)
* 改善使用波段時的Android傳遞輸送量，確保傳遞部分根據排程以正確順序處理。 (NEO-84324)
* 修正由於`to_varchar`函式中出現Null處理錯誤而導致的傳遞準備失敗，以確保順利啟動行銷活動。 (NEO-84108)
* 已解決過期的`libcurl`和`libssh2`版本所導致的SFTP連線問題，確保與Azure代管的SFTP伺服器相容。 (NEO-84038)
* 修正了包含金鑰組驗證錯誤的Snowflake FDA聯結器問題，以確保成功的資料庫連線。 (NEO-84024)
* 已解決型別規則功能問題，確保在「推送」傳遞中正確套用壓力規則。 (NEO-84010)
* 解決升級後不相符的日期和時間戳記比較所導致的BigQuery查詢錯誤，確保與篩選條件相容。 (NEO-83826)
* 解決在因個人化錯誤而繼續暫停的傳遞時，傳遞活動會失敗的問題。 此修正可確保更順暢的傳送工作流程，並防止與暫停活動相關的錯誤。 (NEO-83809)
* 修正FFDA中使用「目標籤錄載入查詢」選項時的問題。 已新增「order by」和「where」子句的支援。 (NEO-83793)
* 已解決Null值寫入broadLogRcp表格中不可為空的欄所造成的週期性傳送失敗。 此修正可改善傳送可靠性，並防止即時行銷活動期間發生錯誤。 (NEO-83729)
* 解決在傳遞準備期間複製種子地址，導致訊息計數不一致的問題。 此修正可確保準確定位並防止重複錯誤。 (NEO-83703)
* 修正生產傳遞在有效期後傳送，可能引發法律問題的嚴重問題。 現在，傳遞會嚴格遵守定義的有效期。 (NEO-83350)
* 已解決將大型資料磁碟區載入Teradata表格時遇到的空間問題。 此修正可最佳化資料處理，並解決生產環境中的間歇性錯誤。 (NEO-83252)
* 解決與SendMetricsToNewRelic錯誤相關的技術工作流程失敗，其導致RT事件處理延遲。 此修正可確保更順暢的工作流程執行，並防止事件積壓。 (NEO-83143)
* 修正FFDA互動執行個體中，ID轉換為UUID所導致的資料庫清理工作流程失敗。 此更新可確保進行正確的清理操作，並降低系統負載。 (NEO-83138)
* 解決種子成員內部名稱長度限制所造成的傳遞失敗。 此修正可允許更長的內部名稱，而不會影響傳遞個人化。 (NEO-83044)
* 修正傳送因隨機錯誤而卡在個人化擱置中的問題。 此更新可確保更流暢的個人化流程以及可靠的傳送執行。 (NEO-82781)
* 已解決由於API錯誤和速度緩慢而無法在主控台中檢閱優惠方案主張的問題。 此修正可改善UI回應並確保適當的選件功能。 (NEO-82742)
* 解決使用自訂傳送物件時Adobe Campaign主控台中的間歇性當機問題。 此修正可確保使用自訂工作流程時的穩定性和可靠性。 (NEO-82675)
* 已修正從v7移轉至v8後所回報的處理速度緩慢和工作流程失敗。 此更新會最佳化行銷活動工作流程並確保及時執行。 (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* 修正MTA子程式卡住、封鎖「推播」和WhatsApp傳遞的關鍵問題。 此更新可確保通訊工作流程更順暢，並防止傳送瓶頸。 (NEO-82351)
* 已解決GCP表格中的字串欄位在更新Teradata期間導致錯誤的資料移轉問題。 此修正可免除因應措施，並提升工作流程效率。 (NEO-82260)
* 更新資料庫清理邏輯，以處理FFDA執行個體中的主要資料庫，防止清除不存在的表格的不必要嘗試。 此修正會最佳化清理作業。 (NEO-81879)
* 解決子工作流程與列舉欄位結合使用所導致的主控台當機問題。 此修正可確保使用擴充的工作流程時的穩定性。 (NEO-81864)
* 修正傳送複製後，目標對應中的子相似性欄位修改不正確，導致工作流程失敗的問題。 此更新可確保一致的子相似性值。 (NEO-81809)
* 在Adobe Campaign Classic v8的檔案傳輸活動中新增對萬用字元的支援，讓使用者能在工作流程中上傳具有動態名稱的檔案（例如， `abc_*`）。 (NEO-81758)
* 推出可在Adobe Campaign Classic v8的iOS推播通知中啟用`content-available`旗標的選項。 此增強功能可讓行動應用程式將通知儲存在收件匣中，並支援背景更新，解決由APNS限制導致的傳送捨棄問題。 (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* 在Adobe Campaign Classic v8中新增BigQuery連線的逾時設定選項。 此增強功能可讓使用者調整查詢的逾時期間，解決由於預設逾時限制導致的查詢失敗問題。 (NEO-81222)
* 修正在v8移轉後，透過分割和替代路由傳送的外部帳戶傳送的映象頁面URL失敗的間歇性問題。 基礎傳遞部分現在已正確複製到`mirrorPageInfo`。 (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* 修正使用者端主控台中的「存取新的Web UI」按鈕，指向生產執行個體的正確URL (`https://experience.adobe.com`)。 如此可解決生產環境中無效URL的問題。 (NEO-80673)
* 修正分割活動中同時使用排序和大小（以區段百分比表示）導致SQL錯誤的問題。 功能現在可以正確運作。 (NEO-80432)
* 已使用`CCurlAzureBlobStorage::UploadStream`解決工作流程中的當機問題。 工作流程現在會在Azure Blob儲存上傳期間執行，沒有分段錯誤。 (NEO-79598)
* 解決在生產環境中無法從使用者端主控台檢視映象頁面的問題。 映象頁面連結現在在電子郵件和主控台檢視中均可正常運作。 (NEO-78946)
* 修正儘管成功傳送訊息，部分記錄檔仍錯誤標示為「傳送已取消」的傳送記錄檔問題。 已解決與聯絡日期和事件日期差異相關的根本原因。 (NEO-78933)
* 已更新`com.google.code.gson:gson`資料庫以提高安全性。 (NEO-78299)
* 解決FDA連線記錄(`nmsconnectionlogs`)中造成工作流程失敗的重複金鑰限制錯誤。 插入邏輯已調整為防止重複ID。 (NEO-78050)
* 修正位址表格中隔離的電子郵件地址錯誤地標示為行動地址，導致傳送分析錯誤的問題。 已更正傳遞物件之間的調解邏輯。 (NEO-76986)
* 解決搭配Oracle資料庫使用控制組時的傳遞準備失敗。 已更正SQL查詢產生，以確保與Oracle資料庫相容。 (NEO-76947)
* 解決在新的月份轉換期間，同時建立資料夾所導致的傳遞失敗。 已調整傳遞資料夾建立邏輯，以防止重複的索引鍵違規。 (NEO-76824)
* 修正Teradata外部帳戶中時區轉換不一致的問題。 顯示的時間戳記現在與設定的時區設定正確對齊。 (NEO-76716)
* 改善資料庫清理工作流程，以有效處理大型資料集。 已實施使用列ID和繫結變數的新方法，以最佳化刪除效能。 (NEO-76439)
* 解決具有「其他」頻道的外部傳遞未產生輸出檔案的問題。 傳遞屬性現在正確包含產生檔案的檔案路徑。 (NEO-75962)
* 修正`ffdaReplicateStagingData`工作流程中因大型資料更新導致的錯誤。 已最佳化逾時設定和表格大小管理，以防止工作流程失敗。 (NEO-75643)
* 已解決預覽直接郵件輸出檔案導致儀表板變為空白的問題。 現在，在檔案預覽後，儀表板可正確顯示。 (NEO-75359)
* 已增強推播通知的追蹤指標，以包含點按和開啟。 指標（例如`@recipientClick`、`@personClick`和`@totalRecipientClick`）現在可計算行動通知點按次數。 (NEO-75240)
* 修正具有外部取消擱置狀態的傳遞的清理工作流程錯誤。 已更正資料庫記錄擷取邏輯。 (NEO-74833)
* 解決俄羅斯（UTC+3:00莫斯科）中`nlserver`輸出時間不正確的時區差異問題。 時間同步邏輯已更新。 (NEO-74754)
* 修正MSSQL資料庫的SQL語法不正確所導致`defaultMidSourcingDlvStat`工作流程中的錯誤。 查詢產生邏輯已針對相容性進行調整。 (NEO-74156)
* 已解決Web流程中的多次當機。 (NEO-73174)
* 修正條件中出現撇號時BigQuery查詢失敗的問題。 查詢處理邏輯已更新，以正確解譯特殊字元。 (NEO-72547)
* 解決具有排除篩選器的型別規則無法正常運作的問題。 已修正傳遞準備的SQL查詢產生。 (NEO-72292)
* 解決退信管理的事件日期和聯絡日期不一致問題。 時區處理邏輯已改善。 (NEO-72277)
* 增強直接郵件傳送中錯誤轉換UTF-8字元的處理。 隱藏字元現在可正確處理，以防止傳送失敗。 (NEO-72148)
* 修正傳入SMS活動中篩選器導致儲存問題的錯誤。 工作流程現在可正確儲存，而不會產生錯誤。 (NEO-70427)
* 更正優惠方案空間中群組適用性條件之SQL查詢的產生。 已新增SQL條件中遺漏的括弧，以確保正確篩選。 (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* 修正BigQuery資料載入工作流程中，由HTTP內容或傳輸編碼問題造成的間歇性錯誤。 連線處理邏輯已經過改良。 (NEO-66989)

## 發行版本 8.6.5 {#release-8-6-5}

_2025 年 4 月 25 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。

### 新功能 {#features-8-6-5}

**新的 SMS 傳送連接器** - SMS 傳送連接器已經過現代化及改善，可啟用收發器模式 SMPP 連線、啟用永久性 SMPP 連線，並確保轉換自 Adobe Campaign Standard 的環境有更好的相容性。新的 SMS 外部帳戶現在可用於所有新的 SMS 實施。仍支援現有的實施，但建議改用此新的現代化及擴充連接器。[閱讀全文](../send/sms/sms.md)。

### 一般改善 {#improvements-8-6-5}

* 在企業 (FFDA) 部署的情境下，應用程式的全域效能已改善，包括傳遞證明傳送和資料庫清理。

* 為了提高應用程式之間所有通訊的安全性，外部 API 呼叫現在支援 mTLS。

* 郵件傳輸代理程式 (MTA) — 已修正孤立 MTA 子代理卡在 **[!UICONTROL Start pending]** 狀態的問題。

### 修正 {#fixes-8-6-5}

此版本還修正下列問題：

NEO-67620、NEO-71534、NEO-80245、NEO-81105、NEO-81758、NEO-81908、NEO-82351、NEO-82742、NEO-83044、NEO-83138、NEO-83350、NEO-83729、NEO-83793、NEO-83809、NEO-84038、NEO-84108、NEO-85269、NEO-86121、NEO-86556、NEO-86739

## 發行版本 8.7.4 {#release-8-7-4}

_2025 年 4 月 10 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#features-8-7-4}

* **簡訊 REST API 支援** - 交易型傳訊 REST API 現在已可用於簡訊頻道。當承載中同時存在 email 和 mobilePhone 時，您可以使用「wishedChannel」欄位來指定頻道。如果未提供，除非 wishedChannel 明確地要求簡訊，否則預設會使用電子郵件。

* **多語言傳送** - 自 4 月發行的 Campaign Web 使用者介面版本起，您將能夠以不同語言傳送多封電子郵件，並存取相關的動態報告。此功能僅於 4 月底在 Adobe Campaign Web 使用者介面中提供，且需要伺服器更新至 Campaign v8.7.4。

### 修正 {#fixes-8-7-4}

此版本已修正下列問題：

NEO-80245、NEO-83559

## 發行版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。僅限&#x200B;**從 Adobe Campaign Standard 移轉至 Adobe Campaign v8** 的客戶，且無法部署於任何其他環境。
>
>作為轉換至 Campaign v8 的 Campaign Standard 使用者，請在 [Campaign v8 網頁使用者介面文件](https://experienceleague.adobe.com/tw/docs/campaign-web/v8/start/acs-migration){target="_blank"}中進一步了解此轉換。

### 新功能 {#features-8-7-3}

* **交易型訊息的動態報告** - 您現在可以在動態報告使用者介面中監視交易型訊息。這些報告可讓行銷人員即時檢視交易型訊息的所有報告量度和維度，以及透過範本傳送的傳遞劃分。[閱讀更多](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=zh-Hant){target="_blank"}

* **交易型訊息 REST API** - 以事件為基礎的交易型 API 現在可用於電子郵件。[閱讀更多](../dev/api/get-started-apis.md)

### 修正 {#fixes-8-7-3}

此版本已修正下列問題：

NEO-79373、NEO-81908、NEO-83081

## 發行版本 8.6.4 {#release-8-6-4}

_2025 年 1 月 15 日_

### 一般改善 {#improvements-8-6-4}

* 已改善 Campaign 應用程式在[企業 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)情境下的傳遞分析期間的穩定性。
* 此版本隨附改善及增強的 FFDA 架構機制，包括金鑰管理、暫存和資料複寫。
* 已為[企業 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。這些工作流程會集中對應表格上的平行複寫請求，以複寫傳遞和相關資料。這些工作流程以 `Replicate nms` 開始。[閱讀更多](../architecture/replication.md)
* 新的&#x200B;**啟用監督者以保持工作流程永久執行**&#x200B;選項現在可在工作流程屬性中使用。啟用此選項後，工作流程會在發生錯誤時自動重新啟動。如果工作流程仍然錯誤，預設會每 30 秒重新啟動一次。若要調整此間隔，您可以建立新的 `XtkWorkflow_WatchdogRestartTimerTimeout` 選項，並設定整數資料類型以指定新的延遲。此選項只應在技術工作流程中啟用。[閱讀更多](../../automation/workflow/workflow-properties.md#execution)

### 安全性改善 {#security-8-6-4}

增強Apache Web模組中的HTTP請求處理功能，以增強安全性並防止潛在請求處理漏洞。 (NEO-85824)

透過 **[!UICONTROL Adobe Experience Cloud]** 外部帳戶與 Adobe 解決方案和應用程式的連線已更新，以加強安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

已新增下列 FDA 連接器。請參見此[頁面](compatibility-matrix.md#FederatedDataAccessFDA)。

* 現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。

* 全新 Amazon Redshift FDA ODBC 連接器現已推出。提供更優異的連線能力、更輕鬆的維護作業，以及更優異的相容性。此新版本帶來下列改進：

   * 新的連接器以 ODBC 介面為基礎，與我們最新的 FDA 連接器一致。這可確保長期支援。
   * 此外也引進了使用 s3 儲存貯體的新資料載入機制，大幅改善效能。

  仍可使用舊版連接器。如果您想要試用新版連接器，請洽詢您的 Adobe 代表。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512、NEO-81520、NEO-81566、NEO-81704、NEO-81908、NEO-82195、NEO-82591、NEO-82592、NEO-82640、NEO-82665、NEO-82781、NEO-82920、NEO-83081、NEO-83096、NEO-83137、NEO-83143。

