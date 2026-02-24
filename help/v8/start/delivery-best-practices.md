---
title: 關於傳遞的最佳實務
description: 瞭解使用Adobe Campaign設計和傳送傳遞時的最佳實務
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: 7bfe0ac7ba99ebf26844d2cea14a75f32ecb8b74
workflow-type: tm+mt
source-wordcount: '3068'
ht-degree: 3%

---

# 關於傳遞的最佳實務 {#delivery-best-practices}

閱讀下列Campaign傳送功能最佳實務。

## 最佳化傳遞 {#optimize-delivery}

在開始建立傳遞之前，您可以採取數個動作來保護上游的傳送流程並加以最佳化。 以下章節概述Adobe Campaign最佳設定的最佳實務和建議程式。

### 平台效能

有幾個因素可能會直接影響伺服器效能，並拖慢Campaign平台的速度：

* [個人化](../send/personalize.md)元素的數量和型別：電子郵件中的個人化會將每個收件者的資料提取出資料庫。 如果有許多個人化元素，則準備傳送所需的資料量會較高。 這可能會降低平台的速度。 在[本節](../send/personalize.md#perso-guardrails)中進一步瞭解個人化護欄。

* 伺服器載入：行銷伺服器同時處理許多不同工作時，可能會減慢效能。 行銷伺服器需要協調所有傳遞的所有傳入和傳出資料，以確保資料正確且準時。
為避免此問題，請與團隊的其他成員協調傳送排程，以確保最佳效能。

* 工作流程執行：監控工作流程是避免平台效能問題的關鍵。 請遵循此檔案[中列出的准則](../../automation/workflow/workflow-best-practices.md#execution-and-performance)。

* 連線至您的[Campaign控制面板功能](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/discover-control-panel/key-features){target="_blank"}，以使用[效能監視](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}功能來監視您的平台。

#### 隔離管理 {#quarantine-management}

維持良好的隔離管理流程符合您的最佳利益。

開始在新平台上傳送電子郵件時，您可能會使用未完全限定的地址清單。 如果您傳送至無效的位址或蜜罐位址（僅用來欺騙垃圾郵件寄件者的信箱），將開始降低平台的聲譽。 良好的隔離管理流程有助於：維持地址品質、避免網際網路存取提供者列入封鎖清單，以及降低錯誤率、加快傳遞速度與輸送量。


在[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/zh-hant/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}中進一步瞭解如何啟動新平台。

技術建議列於[此區段](https://experienceleague.adobe.com/zh-hant/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}。


+++ **閱讀一些最佳實務**

* 如果您有無效地址清單，Adobe建議透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**，將其匯入隔離表格。

* 在傳遞分析期間，預設情況下會排除其地址被隔離的收件者：他們並非目標收件者。 這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。 舉例來說，當收件匣已滿或地址不存在時，可以隔離電子郵件地址。
Adobe Campaign會根據傳回的錯誤型別管理錯誤地址。 [進一步瞭解隔離](../send/quarantines.md)

* 如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。 因此，隔離可讓您避免被這些提供者新增到封鎖清單中。

+++

### 傳遞與維護 {#delivery-maintenance}

定期維護您的傳遞內容，是獲得最佳平台效能的關鍵。

+++ **閱讀一些最佳實務**

* **移除失敗和不需要的傳遞**：請勿讓傳遞在執行個體上維持失敗狀態，因為這會維護暫時資料表並影響效能。 定期移除不再需要用來釋放系統資源的傳遞。

* **清除非作用中收件者**：應該從資料庫移除過去12個月的非作用中收件者，以維持位址品質。 ISP會在閒置一段時間後停用位址，並將退回的訊息傳送給寄件者，以通知他們此新狀態。 定期清理清單可改善傳遞能力並降低成本。

* **明智地排程大型傳遞**：請勿一起排程大型傳遞。 與團隊其他成員協調傳送排程，將負載均勻分散到系統上。 同時傳送多個大型傳遞時，可能會影響整體平台效能。

+++

### 雙重加入機制 {#double-opt-in}

為避免傳送訊息至無效地址、限制不當通訊並改善寄件者信譽，Adobe建議對訂閱後確認實施雙重選擇加入機制。 這有助於確保收件者有意識地訂閱。

## 使用範本 {#use-templates}

傳遞範本提供最常見活動型別的現成案例，有助於提高效率。 透過範本，行銷人員可以在較短的時間內以最小的自訂部署新行銷活動。 [進一步瞭解傳遞範本](../send/create-templates.md)。

### 子網域和品牌 {#subdomains-and-branding}

當您在Adobe Campaign中管理多個品牌時，Adobe建議每個品牌使用一個子網域。 例如，銀行可以有數個子網域對應至其各個地區機構。 如果銀行擁有bluebank.com網域，其子網域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每個子網域擁有一個傳遞範本，可讓您針對每個品牌一律使用正確的預先設定引數，以避免錯誤並節省您的時間。 在[Campaign控制面板檔案](https://experienceleague.adobe.com/zh-hant/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}中進一步瞭解子網域名稱。

### 設定地址 {#configure-addresses}

請務必套用下列准則：

* 寄件者的地址為必要項，才能傳送電子郵件。 有些ISP （網際網路服務提供者）在接受訊息之前，會先檢查寄件者地址的有效性。
* 格式錯誤的位址可能會導致接收伺服器拒絕該位址。 您必須確定已提供正確的地址。
* 地址必須明確識別寄件者。 網域必須屬於寄件者且已註冊給寄件者。
* Adobe建議建立與為傳送和回覆指定的地址對應的電子郵件帳戶。 請洽詢您的傳訊系統管理員。

+++ **在Campaign UI中設定位址的步驟**

若要在Campaign介面中設定地址，請遵循下列步驟：

1. 在[傳遞範本](../send/create-templates.md)中，按一下&#x200B;**[!UICONTROL From]**&#x200B;連結。 在&#x200B;**[!UICONTROL Email header parameters]**&#x200B;視窗中，輸入設定。

1. 在&#x200B;**[!UICONTROL Sender address]**&#x200B;欄位中，確認位址網域與您委派給Adobe的子網域相同。 您可以變更&#39;@&#39;之前的部分，但無法變更網域位址。

1. 在&#x200B;**[!UICONTROL From]**&#x200B;欄位中，使用收件者可輕鬆辨識的名稱（例如您的品牌名稱），以提高您傳送的開頭率。 若要進一步改善收件者的體驗，您可以新增個人名稱，例如「Emma from Megastore」。

1. 在&#x200B;**[!UICONTROL Reply address text]**&#x200B;欄位中，預設會使用寄件者的地址來回覆。 不過，Adobe建議使用現有的實際地址，例如您品牌的客戶服務。 在此情況下，如果收件者傳送回覆，客戶服務將能夠處理。

+++

### 設定控制組 {#set-up-control-group}

傳送傳遞後，您可以將排除的收件者與收到傳遞的收件者之行為進行比較。 接著，您就可以評估行銷活動的效率。 深入瞭解控制群組[本節](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group)。

### 使用型別來套用篩選器或控制規則 {#create-typologies}

型別包含在傳送任何訊息之前，在分析階段套用的檢查規則。

在範本屬性的&#x200B;**[!UICONTROL Typology]**&#x200B;標籤中，您可以視需要選取自訂型別。

例如，為了更能控制傳出流量，您可以定義要使用的IP位址，方法為為每個子網域定義一個相似性，並為每個相似性建立一種型別。 相似性是在執行個體的組態檔案中定義。 請連絡您的Adobe Campaign管理員。

如需型別的詳細資訊，請參閱[本節](../../automation/campaign-opt/campaign-typologies.md)。

## 最佳化您的內容 {#optimize-content}

### 建置個人化內容 {#perso-content}

若要個人化您的訊息，您可以使用儲存在資料庫中的收件者資料，或是透過追蹤、登陸頁面、訂閱等收集的資料。 在[本節](../send/personalize.md)中提供Personalization基本知識。

+++ **閱讀一些最佳實務**

* 檢查您的個人化設定 — 確認您的訊息內容經過適當設計，以避免任何與個人化相關的錯誤。 Adobe Campaign個人化標籤一律採用下列形式： `<%=table.field%>`。 個人化區塊中引數的使用不正確可能是個問題。 例如，JavaScript中的變數使用方式如下：

  &grave;&grave;
  <%
  var brand = "xxx"
  %>
  &grave;&grave;

  如需個人化區塊的詳細資訊，請參閱[本區段](../send/personalization-blocks.md)。

* 準備個人化資料 — 您可以在工作流程中準備個人化資料，以改進傳送準備分析。 如果個人化資料來自透過同盟資料存取(FDA)的外部表格，則應特別使用此專案。 此[本章節](../send/personalization-data.md#optimize-personalization)中說明此選項
+++

### 建置最佳化內容 {#build-optimized-content}

建立電子郵件時，請套用電子郵件內容的一般最佳實務。

+++ **閱讀一些最佳實務**

* 讓設計保持簡單

* 將行動使用者牢記在心

* 避免完全以影像為基礎的電子郵件

* 使用電子郵件安全字型

* 編碼特殊字元

+++


### 主旨列  {#subject-line-check}

處理電子郵件[主旨列](../send/personalization-fields.md#personalization-fields-uc)以提高開啟率。


+++ **閱讀一些最佳實務**


* 避免主題過長。 最多使用50個字元

* 避免使用重複性的字詞，例如「free」或「offer」，這些字詞可能會被視為垃圾訊息

* 避免使用大寫字母

* 請勿使用「！」、「£」、「€」、「$」等特殊字元

+++

### 鏡像頁面 {#mirror-page-check}

一律包含映象頁面連結。 偏好位置是電子郵件的頂端。 在[此頁面](../send/mirror-page.md)中進一步瞭解映象頁面

### 取消訂閱連結 {#unsub-link-check}

取消訂閱連結至關重要。 它必須可見且有效，而且表單必須有效。 依預設，分析訊息時，內建&#x200B;**[!UICONTROL Unsubscription link approval]** [型別規則](../../automation/campaign-opt/control-rules.md)會檢查是否包含選擇退出連結，如果缺少該連結，則會產生警告。

瞭解如何在本節[中插入選擇退出連結](../send/personalization-blocks.md)。

+++ **套用此最佳實務**

因為人因錯誤永遠是可能的，在您每次傳送前都必須檢查選擇退出連結是否正確運作。 例如，傳送校樣時，請確定連結有效、表單線上上，且`No longer contact this recipient `欄位已變更為`Yes`。

+++

### 電子郵件大小 {#email-size-check}

為避免效能或傳遞能力問題，建議的最大電子郵件大小約為&#x200B;**35KB**。 若要檢查訊息大小，請瀏覽&#x200B;**[!UICONTROL Preview]**&#x200B;索引標籤並選擇測試設定檔。 產生後，訊息大小會顯示在右上角。


+++ **閱讀一些最佳實務**

* 移除多餘或未使用的樣式

* 將部分電子郵件內容移至登陸頁面

* 將程式碼縮制

請務必在最終傳送前測試任何變更。

+++


### 簡訊長度 {#sms-length-check}

根據預設，SMS中的字元數量符合GSM（行動通訊全球系統）標準。 使用 GSM 編碼的簡訊訊息最多只能有 160 個字元，若是以多個部分傳送的訊息，則每個簡訊的簡訊訊息最多只能有 153 個字元。


+++ **閱讀一些最佳實務**

* 若要保留SMS訊息中的所有字元原樣，例如不要變更正確名稱，請勿啟用音譯。

* 不過，如果您的SMS訊息包含許多GSM標準未考慮的字元，請啟用音譯以限制傳送訊息的成本。 在本節[瞭解更多](../send/sms/smpp-external-account.md#smpp-transliteration)。

* 您可以套用SMS音譯，包括當GSM標準未考慮到SMS的一個字元時，用另一個字元取代該字元。 請注意，將個人化欄位插入您的SMS訊息內容，可能會引入GSM編碼未考慮的字元。 身為Campaign管理員，您可以核取對應&#x200B;**[!UICONTROL External account]**&#x200B;的SMPP頻道設定索引標籤中對應的方塊，以啟用字母音譯。 [了解更多](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### 避免附件

附件仍然是惡意程式碼泛濫最常見的媒介之一，尤其是大量傳送時。 加入檔案的安全連結，而非附加檔案。 這可確保額外的安全層級，以防止無意中的再散佈，並大幅減少傳入電子郵件閘道因郵件大小或安全性原因而拒絕郵件的可能性。

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=zh-Hant#authentication).-->

## 管理影像 {#manage-images}

以下是一些針對電子郵件行銷活動最佳化影像的特定准則。

### 避免影像封鎖 {#image-blocking}

有些電子郵件使用者端預設會封鎖影像，使用者可能會變更其設定以封鎖影像，以便儲存資料使用量。  因此，如果未下載影像，可能會遺失整個訊息。

+++ 若要避免此問題，您可以套用這些最佳實務

* 避免使用完全以影像為基礎的電子郵件。 平衡您的內容與影像與文字。

* 如果文字必須包含在影像中，請使用替代文字和標題文字來確認訊息是否傳入。 設定替代/標題文字的樣式，以改善其外觀。

* 避免使用背景影像，因為有些電子郵件使用者端不支援這些影像。
+++

### 讓影像回應 {#responsive-images}

嘗試使影像回應且可調整大小，使其在所有內容與裝置中皆可見。 請注意，這可能會造成成本影響，因為建置時間較長。

### 使用絕對影像參照 {#absolute-images}

若要從外部存取，連結至行銷活動的電子郵件和公共資源中所使用的影像，必須存在於外部可存取的伺服器上。

* 從傳遞小幫手，您可以匯入包含影像的HTML頁面，或透過&#x200B;**[!UICONTROL Image]**&#x200B;圖示直接使用HTML編輯器插入影像。

* 如果未顯示影像，請檢查伺服器上是否有這些影像。 若要這麼做，請瀏覽至傳遞的&#x200B;**Source**&#x200B;標籤。 尋找您的影像，並在網頁瀏覽器中複製並貼上每個影像的URL。 如果未顯示影像，請聯絡您的IT管理員或提供傳送內容的協力廠商廠商。

### 預覽和測試您的訊息 {#preview-msg}

Adobe建議預覽您的訊息，以檢查其個人化情況，以及收件者看到您傳遞內容的方式。

在傳遞助理中，**[!UICONTROL Preview]**&#x200B;子索引標籤可讓您檢視每個收件者的內容轉譯。 個人化欄位和內容的條件元素會取代為所選設定檔的對應資訊。 [了解更多資訊](../send/preview-and-proof.md)。


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## 定義正確客群 {#define-the-right-audience}

目標人口是關鍵：仔細建立您的清單，在熱門電子郵件使用者端和行動裝置上測試您的電子郵件，並確保您的電子郵件清單是最新的（沒有未知或過時的地址）。 您也可以傳送校樣來幫助設定完整的驗證週期。 若要了解客群的詳細資訊，請參閱[本章節](../audiences/gs-audiences.md)。

### 鎖定正確的對象 {#target-the-right-audience}

內容準備就緒後，您需要仔細定義將接收訊息的人員。

若要成功傳遞，您想要將最相關的個人化內容傳送給正確的收件者。 Adobe Campaign可讓您建立最精確的目標：您可以根據收件者的年齡、本地化、購買內容、是否在上一次傳送中按一下連結等來選取收件者。 透過Adobe Campaign，您還可以定義測試設定檔、控制組和種子地址，以確保您的目標正確無誤。

### 目標對應 {#target-mappings}

在Campaign中，預設的傳遞範本目標為&#x200B;**收件者**。 Adobe Campaign為您的傳送提供其他目標對應，您可以視需求加以變更。 例如，您可以傳送給已透過社交網路收集設定檔的訪客，或訂閱資訊服務的訪客。

這些對應會顯示在此區段[中的](../audiences/target-mappings.md)。

### 外部收件者 {#external-recipients}

您可以傳遞至儲存在外部檔案中而非儲存在資料庫中的收件者。 在本節[瞭解更多](create-message.md#select-external-recipients-selecting-external-recipients)。

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### 測試收件者 {#test-recipients-seed-addresses}

若要測試您的傳遞，請在傳送至主要目標之前使用證明。

請務必選取適當的校樣收件者，因為他們會驗證訊息的表單和內容。 定義校訂收件者的步驟[會顯示於本節](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target)。


### 重複位址 {#deduplicate-addresses}

請務必避免電子郵件地址重複，因為這可能會對您的目標造成影響：

* 分割目標時，相同的訊息可以傳送多次。

* 如果收件者在收到訊息後取消訂閱，其重複的設定檔仍會收到未來的訊息。

對地址進行重複資料刪除可保護您的傳送信譽，並確保良好的隔離管理。

**相關主題：**

* [重複資料刪除活動](../../automation/workflow/deduplication.md)。
* [使用案例：使用重複資料刪除活動的合併功能](../../automation/workflow/deduplication-merge.md)。


## 傳送前執行所有檢查 {#perform-all-checks}

訊息就緒後，請確定內容在所有裝置上皆正確顯示，且未包含任何錯誤，例如錯誤的個人化或中斷的連結。 在傳送訊息之前，也請確定引數和設定與傳送一致。

本節[中顯示了驗證傳遞的步驟](../send/preview-and-proof.md)。

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### 校樣訊息 {#proof-messages}

傳送校樣可讓您檢查選擇退出連結、鏡像頁面和任何其他連結、驗證訊息、驗證影像是否顯示、偵測可能的錯誤等。 您可能也會想要在不同裝置檢查您的設計和轉譯。

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### 請確定您的訊息已傳送 {#make-sure-your-message-is-delivered}

最後一步就是儘可能提高您的機會，並運用Adobe Campaign的強大功能，確保您的訊息確實會傳送給相關收件者。

#### 進行驗證程式

您可以定義涉及Adobe Campaign運運算元和群組的完整驗證程式，以驗證目標和訊息內容。 這將確保完全監控和控制行銷活動的各種流程：目標定位、內容、預算、摘錄和傳送證明。 根據使用者的許可權，使用者會收到通知、收到校樣並能夠驗證或拒絕訊息。 在本節[瞭解更多](../../automation/campaigns/marketing-campaign-approval.md)。

#### 使用波段

您可以逐步增加使用波段傳送的容量。 這可避免您的郵件被標示為垃圾郵件，或您想要限制每天的郵件數。 使用波段您可以將傳送劃分為幾個批次，而不是同時傳送大量訊息。 在本節[瞭解更多](../send/configure-and-send.md#sending-using-multiple-waves)。

#### 排定訊息的優先順序

您可以說明優先層級，設定傳送的傳送順序。 若要這麼做：

1. 編輯傳遞屬性，並選取&#x200B;**[!UICONTROL Delivery]**&#x200B;標籤。

1. 定義傳遞的優先順序層級，範圍從&#x200B;**[!UICONTROL Very low]**&#x200B;到&#x200B;**[!UICONTROL Very high]**。

>[!NOTE]
>
>無法定義從傳送中傳送訊息的順序。

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### 使用型別

您可以使用型別規則，根據特定條件排除部分目標。 這可確保在遵守公司通訊政策的同時，傳送最符合客戶需求及期望的訊息。 例如，您可以從電子報的目標篩選未成年的收件者。 在此範例[中瞭解更多](../../automation/campaign-opt/filtering-rules.md)。


## 追蹤和監視 {#track-and-monitor}

您按一下&#x200B;**傳送**&#x200B;按鈕嗎？ 讓我們看看會發生什麼事。 傳送後，Adobe Campaign可讓您追蹤已傳送的訊息，並探索收件者對傳送的反應。 這可協助您改善未來的傳送，並最佳化後續的行銷活動。

## 監視傳遞 {#monitoring-deliveries}

若要控制您的行銷活動，您必須確保訊息確實已傳送給收件者。

在Campaign傳送控制面板中，您可以檢查已處理的訊息和傳送稽核記錄。 您也可以控制傳送記錄檔中訊息的狀態。

## 追蹤行為 {#track-behaviour}

為了更清楚瞭解收件者的行為，您可以追蹤他們對傳送的反應：接收、開啟、點選連結、取消訂閱等。 在Campaign中，此資訊會顯示在傳遞所目標定位的收件者的&#x200B;**追蹤**&#x200B;索引標籤中，以及傳遞的Tracking索引標籤中。

訊息追蹤預設為啟用。 若要設定URL，請選取傳送助理員下方區段中的「顯示URL」選項。 對於訊息的每個URL，您可以選擇是否啟動追蹤。


[進一步瞭解追蹤功能](../send/tracking.md)
