---
title: Campaign安全性最佳做法
description: 開始使用Campaign安全性最佳做法
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2270'
ht-degree: 68%

---

# Campaign安全性最佳做法 {#ac-security}

Adobe非常重視您數位體驗的安全性。 安全性實務已深深植入我們的內部軟體開發和作業流程及工具，我們的跨職能團隊也嚴格遵循這些實務准則，以迅速預防、偵測和回應事件。

此外，我們與合作夥伴、領先的研究人員、安全性研究機構和其他產業組織締結合作關係，這能協助我們掌握最新的威脅和弱點，並定期將進階安全性技術整合至我們提供的產品和服務中。

## 隱私權

為正確處理隱私權並管理個人資料，工作時請遵循您營運業務所在地區的適用法規。Adobe Campaign的功能可協助您遵守[此頁面](../start/privacy.md)所列的規定

### Adobe Experience Cloud 隱私權 {#experience-cloud-privacy}

Adobe Campaign 是 Adobe Experience Cloud 解決方案的一部分。在 Campaign 中處理隱私權的方式會依循 Experience Cloud 的一般原則，例如：

* **使用 Adobe Experience Cloud 時會收集哪些資訊**

  身為使用 Adobe Experience Cloud 解決方案的公司，您可以選擇要收集哪些資訊並傳送至您的 Adobe Experience Cloud 帳戶。可收集的資訊類型範例包含網頁瀏覽活動、IP 位址、行動裝置的位置資訊、促銷活動成功率、購買或放入購物車的項目等。

  >[!NOTE]
  >
  >而對於所有 Adobe 產品，Campaign 會收集應用程式和網站使用者的相關資訊。如需此項目的詳細資訊，請參閱 [Adobe 隱私權政策](https://www.adobe.com/tw/privacy/policy.html)。

* **如何使用 Adobe Experience Cloud 收集資訊**

   * Adobe Experience Cloud 解決方案會使用 Cookie 和類似技術（例如網站信標，又稱為標籤或像素），讓您收集資訊。如需 Adobe Campaign Cookie 和追蹤功能的詳細資訊，請參閱[本節](#tracking-capabilities)。
   * 您也可以在行動應用程式中使用 Adobe Experience Cloud 技術。如需使用Campaign傳送行動傳遞的詳細資訊，請參閱[簡訊頻道](../send/sms/sms-channel.md)和行動應用程式頻道。

* **使用者對於您使用 Adobe Experience Cloud 的隱私權選擇**

  Adobe 要求您提供客戶的隱私權政策，以說明：

   * 您與 Adobe Experience Cloud 相關聯的隱私權實務
   * 使用者如何針對 Adobe Experience Cloud 收集或使用其資訊進行偏好設定

  >[!NOTE]
  >
  >而對於所有 Adobe 產品，Campaign 使用者可以透過應用程式和網站，選擇退出分享收集關於他們的資訊。如需此項目的詳細資訊，請參閱 [Adobe Experience Cloud 使用資訊常見問答](https://www.adobe.com/tw/privacy/experience-cloud-usage-info-faq.html)。

如需 Adobe Experience Cloud 隱私權的後續詳細資料，請參閱[本頁](https://www.adobe.com/tw/privacy/marketing-cloud.html)。

## 個人資料與角色 {#personal-data}

在管理隱私權時，請務必定義哪些資料應謹慎處理，以及由哪些人員處理。
* **個人資料**&#x200B;是指可直接或間接識別在世個人的資訊。
* **敏感個人資料**&#x200B;是指與個人的種族、政治觀點、宗教信仰、犯罪背景、遺傳資訊、健康資料、性傾向、生物識別資訊，以及工會會員會籍相關的資訊。

將Campaign與其他Experience Cloud解決方案整合時，如果閱聽眾可以從一個系統傳輸到另一個系統，例如[Adobe Analytics](../connect/ac-aa.md)、[Experience Cloud Audiences](../start/shared-audiences.md)、Campaign Standard，或是其他解決方案，如[CRM Connector](../../automation/workflow/crm-connector.md)，您需要支付額外的個人護理費用來保護資料。

[主要法規](#privacy-regulations)是指管理資料之不同實體，如下所示：

* **資料控制方**&#x200B;是決定收集、使用及分享個人資料之方式與目的的當局機關。

* **資料處理方**&#x200B;是指依據資料控制方的指示收集、使用或分享個人資料的任何個人或一方。

* **資料主體**&#x200B;是指正在收集、使用或分享個人資料的任何在世個人，以及可參照該個人資料直接或間接識別的在世個人。

因此，身為收集和分享個人資料的公司，您是資料控制方、客戶是資料主體，而 Adobe Campaign 在依您的指示處理個人資料時，會作為資料處理方。請注意，身為資料控制方，您有責任處理與資料主體的關係，例如管理[隱私權要求](#privacy-requests)。

### 使用實例情境 {#use-case-scenario}

為了說明不同角色如何互動，以下是 GDPR 客戶體驗的高階使用案例。

在此範例中，航空公司是 Adobe Campaign 客戶。該公司是&#x200B;**資料控制方**，而該航空公司的所有客戶為&#x200B;**資料主體**。Laura 在此特定案例中是航空公司的客戶。

以下是此範例中使用的不同角色：

* **Laura** 是&#x200B;**資料主體**。她是收到航空公司訊息的收件人。Laura 可能是常客，但可能會在某個時間點決定不想要收到關於這家航空公司提供的任何個人化廣告或行銷訊息。她會要求航空公司（根據他們的流程）刪除她的常旅客號碼。

* **Anne** 是航空公司的&#x200B;**資料控制方**。她會收到Laura的請求，檢索用於識別資料主體的有用ID，並在Adobe Campaign中提交請求。

* **Adobe Campaign** 是&#x200B;**資料處理方**。

![](assets/privacy-gdpr-flow.png)

以下是此使用案例的一般流程：

1. **資料主體** (Laura) 透過電子郵件、客戶服務或網站入口，向&#x200B;**資料控制方**&#x200B;傳送 GDPR 請求。

1. **資料控制方** (Anne) 透過介面或使用 API 將 GDPR 請求推送至 Campaign。

1. 當&#x200B;**資料處理方** (Adobe Campaign) 收到資訊後，會對 GDPR 請求採取行動，並傳送回應或向&#x200B;**資料控制方** (Anne) 進行確認。

1. 然後，**資料控制方** (Anne) 會審查該資訊並將其傳送回&#x200B;**資料主體** (Laura)。

## 資料擷取 {#data-acquisition}

Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

* 讓收件者一律同意接收通訊。為此，請盡快接受選擇退出要求，並透過雙重選擇加入程式以確認同意。如需詳細資訊，請參閱[建立雙重選擇加入的訂閱表單](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}。
* 請勿匯入詐騙清單，並使用種子地址以確認您的用戶端檔案並未遭到詐騙使用。有關此項目的詳細資訊，請參閱[關於種子地址](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}。
* 透過同意與權限管理，您可以追蹤收件者的偏好設定，並管理組織內哪些人員可以存取哪些資料。如需詳細資訊，請參閱[本節](#consent)。
* 加速和管理收件者的隱私權要求。如需詳細資訊，請參閱[本節](#privacy-requests)。

## 隱私權管理 {#privacy-management}

隱私權管理是指可協助您遵守隱私權法規（GDPR、CCPA等）的所有流程及工具。

Adobe Campaign 提供專屬於隱私權管理的各種功能：
* 同意管理、資料保留和使用者角色。請參閱[本節](#consent)。
* 隱私權要求（存取權限與被遺忘的權利）。請參閱[本節](#privacy-requests)。
* 選擇退出個人資訊銷售（專屬於CCPA）。

[本節](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)將提供 Campaign 中主要隱私權功能及相關角色的範例。

### 同意、保留和角色 {#consent}

一開始，Adobe Campaign 會提供對隱私權至關重要的功能：

* **同意管理**：透過訂閱管理程序，您可以管理收件者的偏好設定，並追蹤哪些收件者已選擇加入何種訂閱類型。有關此項目的詳細資訊，請參閱[關於訂閱](../../automation/workflow/subscription-services.md).
* **資料保留**：所有內建標準記錄表都具有預設的保留期間，通常會將其資料儲存限制在 6 個月或更短時間。您可以使用工作流程設定其他的保留期間。如需此項目的詳細資訊，請洽詢 Adobe 顧問或技術管理員。
* **權限管理**：Adobe Campaign 可讓您透過不同的預先建立或自訂角色，管理指派給各種 Campaign 運算子的權限。這可讓您管理公司內可存取、修改或匯出不同類型資料的人員。有關此項目的詳細資訊，請參閱[關於存取管理](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}。

### 隱私權請求 {#privacy-requests}

Adobe Campaign 提供其他功能，協助您作為資料控制方，針對特定隱私權要求預作準備：

* **存取權限**&#x200B;是指資料主體有權從資料控制方取得關於其個人資料是否正在處理、處理地點及處理原因的確認。

* **被遺忘的權利** (刪除要求) 為資料主體賦予權利，讓資料控制人員得以清除其個人資料。

[此節](../start/privacy.md)顯示&#x200B;**存取**&#x200B;及&#x200B;**刪除**&#x200B;要求。

建立這些請求的實施步驟將於[本節](../start/privacy.md)中詳細說明。

## 追蹤功能 {#tracking-capabilities}

### Cookie {#cookies}

Adobe Campaign 的追蹤功能讓您得以使用三種 Cookie 來追蹤傳遞收件者的瀏覽：工作階段 Cookie 和兩個永久 Cookie。

* **工作階段** Cookie：**nlid** Cookie 包含傳送到聯絡人之電子郵件的識別碼 (**broadlogId**)，以及訊息範本的識別碼 (**deliveryId**)。連絡人按一下由 Adobe Campaign 傳送的電子郵件中包含的 URL 後即可添加識別碼，並且允許您追蹤他們在網路上的行為。瀏覽器關閉時，將自動清除工作階段 Cookie。連絡人可以將其瀏覽器設定為拒絕 Cookie。

* 兩個&#x200B;**永久** Cookie：
   * **UUID** (通用唯一識別碼) Cookie 在 Adobe Experience Cloud 解決方案之間共用。 它會設定一次，直到產生新值時，從用戶端瀏覽器消失為止。 此 Cookie 可讓您識別在 Experience Cloud 解決方案造訪網站時與之互動的使用者。 您可以透過登陸頁面 (將未知的客戶活動與收件者建立關聯) 或傳遞來儲存。 此 Cookie 的說明可在[此頁面](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=zh-Hant#ec-cookies)取得。
   * **nllastdelid** Cookie (在 Campaign Classic 20.3 中推出) 是永久 Cookie，包含使用者點按連結的上次傳遞之 **deliveryId**。當工作階段 Cookie 遺失時，會使用此 Cookie 來識別將要使用的追蹤表格。

《一般資料保護規範》(GDPR) 等法規規定，公司必須先取得網站使用者的同意，才能安裝 Cookie。

* 您必須透過授權請求 (有時出現在網站頁面中) 告知使用者，網站已裝置網路追蹤工具，並要求使用者點按核取方塊授權使用 Cookie，或在使用者登陸的首頁頂端新增橫幅等。
* 快顯視窗通常會被瀏覽器封鎖，因此應避免使用。

### 訊息追蹤 {#message-tracking}

Adobe Campaign 可讓您追蹤已傳送的電子郵件和傳遞收件者的行為：開啟、點按連結、取消訂閱等。 如需詳細資訊，請參閱[關於訊息](../start/gs-message.md)。

若要這麼做，請將追蹤連結新增至您的訊息，以便在傳遞控制面板的Tracking索引標籤中測量傳遞和收件者行為的影響。 追蹤資料會在追蹤指標報告中詮釋。 若要進一步瞭解追蹤，請參閱[此頁面](../start/tracking.md)。

### 網路追蹤 {#web-tracking}

Adobe Campaign也可讓您監視收件者瀏覽網站的方式：插入追蹤標籤，以收集資訊並測量網站應用程式頁面上的造訪次數。

網路追蹤的設定在[本節](../start/tracking.md)中說明。

為進一步管理追蹤，Adobe Campaign 可讓您顯示選擇退出橫幅，以停止追蹤選擇退出行為追蹤的終端使用者的網站行為。 如需詳細資訊，請參閱[網站應用程式追蹤選擇退出](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out){target=_blank}。

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

>[!NOTE]
>
>作為「受管理的Cloud Services」使用者，Adobe將與您合作，在您的環境中實作這些設定。


## 存取管理

存取管理是強化安全性的重要一環。 以下是一些主要最佳實務：

* 建立足夠的安全性群組
* 檢查每個操作員是否具有適當的存取許可權

在[本節](../start/gs-permissions.md)中進一步瞭解許可權

## 編碼准則

在Adobe Campaign中進行開發時（工作流程、JavaScript、JSSP等），請一律遵循下列准則：

* **指令碼**：嘗試避免SQL陳述式，使用引數化函式而非字串串串連，將要使用的SQL函式新增至允許清單以避免SQL插入。

* **保護資料模型**：使用已命名的許可權來限制運運算元動作、新增系統篩選器(sysFilter)

* **在網頁應用程式中新增驗證碼**：在您的公開登陸頁面和訂閱頁面中新增驗證碼。

進一步瞭解[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=zh-Hant#installing-campaign-classic){target="_blank"}。


## 個人化

將個人化連結新增至您的內容時，請一律避免URL的主機名稱部分有任何個人化專案，以避免潛在的安全性缺口。 下列範例絕不應該用於所有URL屬性&lt;`a href="">`或`<img src="">`：

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 資料限制

您必須確定低許可權驗證的使用者無法存取加密的密碼。 要執行此操作，有兩個主要方法：限制僅存取密碼欄位或存取整個實體。

此限制可讓您移除密碼欄位，但讓所有使用者都可從介面存取外部帳戶。 在[本頁](../dev/restrict-pi-view.md)中瞭解更多。

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 建立新的&#x200B;**[!UICONTROL Extension of a schema]**。

1. 選擇&#x200B;**[!UICONTROL External Account]** (extAccount)。

1. 在最後一個畫面中，您可以編輯新的srcSchema來限制存取所有密碼欄位：

   您可以將主要元素(`<element name="extAccount" ... >`)取代為：

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   因此，您的擴充式srcSchema看起來可能像這樣：

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >您可以以`hasNamedRight('admin')`取代`$(loginId) = 0 or $(login) = 'admin'`，讓所有具有管理員許可權的使用者看見這些密碼。


## 存取管理

存取管理是強化安全性的重要一環。 以下是一些主要最佳實務：

* 建立足夠的安全性群組
* 檢查每個操作員是否具有適當的存取許可權

在本節[&#128279;](../start/gs-permissions.md)中進一步瞭解中的許可權。

## 編碼准則

在Adobe Campaign中進行開發時（工作流程、JavaScript、JSSP等），請一律遵循下列准則：

* **指令碼**：嘗試避免SQL陳述式，使用引數化函式而非字串串串連，將要使用的SQL函式新增至允許清單以避免SQL插入。

* **保護資料模型**：使用已命名的許可權來限制運運算元動作、新增系統篩選器(sysFilter)

* **在網頁應用程式中新增驗證碼**：在您的公開登陸頁面和訂閱頁面中新增驗證碼。

進一步瞭解[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=zh-Hant#installing-campaign-classic){target="_blank"}。
