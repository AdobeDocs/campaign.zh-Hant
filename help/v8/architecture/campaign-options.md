---
title: 行銷活動選項
description: 瞭解何謂Campaign選項、其儲存位置，以及如何使用Campaign v8記錄的選項
feature: Architecture
role: Admin, Developer
level: Intermediate
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
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 92bab89570eca3eb13d6010db0deec74e7860c91
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 3%
---
# 行銷活動選項 {#campaign-options}

選項是控制Campaign執行個體行為方式的引數，例如電子郵件中的預設影像大小限制、同時執行的工作流程數量，或傳送範本的預設路由提供者。 有些選項是內建的，有些則視需要建立。 可用的選項取決於您執行個體上安裝的套件。 深入瞭解[內建套件](built-in-packages.md)。

>[!CAUTION]
>
>請僅修改Campaign檔案中記錄的選項，且僅依照所述修改。 未記錄的選項為內部選項，且不得修改。 修改選項會保留給專家使用者。

## 儲存選項的位置 {#where-options-are-stored}

選項儲存在Campaign資料庫的&#x200B;**xtkOption**&#x200B;資料表（結構描述&#x200B;**xtk:option**）中。 在Campaign Explorer中，它們可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;下使用。 在Campaign Web使用者介面中，它們可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Options]**&#x200B;下使用。 兩個清單相同。 深入瞭解[設定Campaign選項](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}。

## 使用選項 {#use-options}

1. 在Campaign Explorer中，瀏覽至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**。
1. Select選項，然後更新其值。 如果選項不存在，請以檔案中提供的確切名稱建立它。
1. 設定檔案預期型別的值。 例如，CRM同步化日期的文字選項，或工作流程重新啟動延遲的整數選項。

您也可以建立自己的選項，例如儲存工作流程的中繼資料。 輸入名稱、選取資料型別並設定值。 深入瞭解[設定Campaign選項](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}。

有些選項會保留認證。 使用`cryptString`函式加密密碼，如[使用Campaign和Adobe Experience Platform登陸頁面](../connect/ac-aep-landing-pages.md)中所述。 當您旋轉認證時，請同時旋轉儲存在選項中的認證。 進一步瞭解[認證循環指南](../../technotes/security/credential-rotation-guide.md#ac-options-credentials)。

## 在工作流程和個人化中使用選項 {#use-options-in-processes}

您可以從JavaScript程式碼、個人化和查詢中讀取和寫入選項值。

* **JavaScript程式碼**，例如JavaScript程式碼工作流程活動： `getOption('OptionName')`會傳回選項的值，且`setOption('OptionName', value, 'description')`會加以設定。 例如，`getOption('IMS_ORG_ID')`。 深入瞭解[getOption](../../campaign-api/f-getoption.md)和[setOption](../../campaign-api/f-setoption.md)。
* **傳遞個人化**： `<%@ include option='OptionName' %>`插入選項的值。 例如，`<%@ include option='NmsServer_URL' %>`在LINE訊息的網頁應用程式連結中包含伺服器URL。 透過Adobe Campaign](../send/line/line.md)在[傳送直接LINE訊息中瞭解更多。
* **查詢編輯器**：在&#x200B;**值**&#x200B;欄位中輸入`$(options:OPTION_NAME)`以使用選項的值。 深入瞭解[設計查詢](../start/design-queries.md)。

## 可用選項 {#available-options}

下表列出Campaign v8中可用的選項（依區域分組）。 當檔案的另一個頁面描述某個選項時，表格會連結到該選項。 有些專案是資訊或維護選項。 列出選項並不表示可以安全變更。

### 傳遞 {#delivery-options}

這些選項可控制如何準備和傳送傳遞。 其中涵蓋影像和附件限制、預設路由提供者、中間來源分割臨界值、開放式追蹤指令碼、公用伺服器URL、傳遞有效性、重複專案和延遲傳遞的處理以及條碼。 深入瞭解[附加檔案](../send/attaching-files.md)、[電子郵件引數](../send/email-parameters.md)、[傳遞最佳實務](../start/delivery-best-practices.md)、[開始使用行銷活動架構](architecture.md#split)、[有關電子郵件追蹤畫素的指引](../start/cnil-pixel-tracking.md)以及[傳送直接訊息](../send/line/line.md)。

| 選項 | 說明 |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | 從個人化URL下載並附加至電子郵件的影像大小上限（位元組）。 預設值為100,000位元組(100 KB)。 [了解更多](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | 顯示警告之前，電子郵件或交易式電子郵件範本中的最大附件數量。 預設值為1。 [了解更多](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | 執行個體的預設錯誤電子郵件地址，在傳遞將錯誤地址留空時使用。 [了解更多](../send/email-parameters.md) |
| XtkEmail_Characters | 電子郵件地址的有效字元。 [了解更多](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | 新傳遞範本的預設路由提供者。 將其設為分割外部帳戶的名稱，以依預設使用分割傳遞。 [了解更多](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | 在多個中間來源執行個體之間分割傳遞的大小。 預設值為100K。 [了解更多](architecture.md#split) |
| NmsTracking_OpenFormula | 計算開啟追蹤URL的指令碼。 針對每個畫素目的定義一個選項。 [了解更多](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | 公用Web應用程式伺服器的基底URL。 例如，用於將網頁應用程式連結包含在LINE訊息中。 [了解更多](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | 傳送的預設有效期（以秒為單位）。 |
| NmsBroadcast_RemoveDuplicatesRecipients | 將其設為1，以自動忽略重複的收件者。 |
| NmsDelivery_ImageServerTimeout | 擷取從個人化URL下載並附加至電子郵件的影像時，從伺服器取得回應的逾時（以秒為單位）。 如果超過逾時，則無法傳送訊息。 預設值為60秒。 |
| NmsDeliveryWizard_ShowDeliveryWeight | 顯示傳遞助理中的訊息權重。 |
| NmsMTA_Alert_Delay | 延遲（以分鐘為單位），過了這段時間，就會將傳送視為延遲。 預設值為30分鐘。 |
| NmsServer_MirrorPageUrl | 映象頁面伺服器的URL。 路由定義未指定URL時，此為電子郵件傳送的預設值。 依預設，它與追蹤伺服器URL相同。 |
| XtkBarcode_SpecialChar | 啟用或停用Code128條碼的特殊字元支援。 |
| NMS_ActivateOwnerConfirmation | 將其設為1，以便在指定特定操作員或群組開始傳送時，負責傳送的操作員可以確認傳送。 將其設為0以停用：只有指定的操作員或群組，或管理員，才能確認傳送。 |
| NmsDelivery_senderAddressMask | 電子郵件傳遞的「寄件者」欄位中允許的寄件者地址清單（以逗號分隔）。 當選項有值時，該欄位會成為下拉式清單。 此限制是全域性的：適用於每個品牌和傳遞範本，僅支援靜態地址。 [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### 行銷活動與工作流程 {#campaign-workflow-options}

這些選項可控制行銷活動和工作流程的執行方式。 其中涵蓋傳送的擁有者確認、同時處理的工作數量，以及工作流程的檢查和自動重新啟動。 內容也涵蓋SQL活動的保護、預設行銷活動有效性以及匯出報告的標誌。 深入瞭解[行銷活動傳遞](../../automation/campaigns/marketing-campaign-deliveries.md)、[工作流程最佳實務](../../automation/workflow/workflow-best-practices.md)、[監視工作流程執行](../../automation/workflow/monitor-workflow-execution.md)、[工作流程屬性](../../automation/workflow/workflow-properties.md)以及[SQL程式碼和JavaScript程式碼](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)。

| 選項 | 說明 |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | 將其建立並設為1，以便行銷活動擁有者可以確認傳送，即使已定義稽核者亦然。 將其設為0以停用。 [了解更多](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | 行銷活動同時處理的傳遞、工作流程、假設和模擬工作的最大數量。 預設值為10。 [了解更多](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | 兩次檢查暫停的工作流程之間的天數。 [了解更多](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | 將其建立為整數選項，以變更自動檢查並重新啟動工作流程的30秒間隔。 [了解更多](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | 將其設為0，可針對封鎖的SQL方法停用SQL程式碼活動的保護。 [了解更多](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | SQL活動封鎖或警告的SQL方法清單。 [了解更多](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | 行銷活動的預設有效期（以秒為單位）。 |
| NmsOperation_TimeRange | 排程模式中鎖定和擷取條件的時段。 |
| NmsOperation_OperationMgtDebug | 將其設為1，在工作流程稽核記錄中記錄operationMgt技術工作流程的執行資訊。 |
| NmsOperation_DeliveryPreparationWindow | 天數過後，operationMgt技術工作流程會從執行中的傳遞計數中排除狀態不一致的傳遞。 預設值為7。 |
| Workflow_AnalysisThreshold | 受影響的記錄數目，之後會自動重新計算表格統計資料。 |
| XtkReport_Logo | 標誌顯示在匯出報告的右上角。 |

### 電子郵件預設值 {#email-default-options}

這些選項會定義預設寄件者和回覆地址，以及您電子郵件的標籤。 當傳送將對應欄位留空時，Campaign會使用它們。 深入瞭解[電子郵件引數](../send/email-parameters.md)和[使用傳遞範本](../send/create-templates.md)。

| 選項 | 說明 |
|---|---|
| NmsEmail_DefaultFromAddr | 執行個體的預設寄件者地址，在傳遞將其留空時使用。 |
| NmsEmail_FromName | 執行個體的預設From標籤，在傳遞將其留空時使用。 |
| NmsEmail_DefaultReplyToAddr | 執行個體的預設回覆位址，在傳遞將其留空時使用。 |
| NmsEmail_ReplyToName | 執行個體的預設回覆標籤，在傳遞將其留空時使用。 |
| NmsEmail_DefaultErrorAddr | 執行個體的預設錯誤位址，在傳遞將其留空時使用。 [了解更多](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | 傳送訊息時使用之寄件者地址的語法。 |
| NmsDelivery_ErrorAddressMasks | 回複訊息時使用的錯誤位址語法。 |
| NmsEmail_ExpOrganization | 您組織的一般名稱，用於向收件者顯示的一些警告訊息。 |

### 軟錯誤和隔離 {#error-options}

這些選項會定義在軟錯誤（即暫時性傳送失敗）後將收件者置於隔離狀態的時間。 深入瞭解Campaign](../send/quarantines.md#soft-error-management)的[隔離管理，以及Campaign](../send/delivery-failures.md#retries)的[傳遞失敗。

| 選項 | 說明 |
|---|---|
| NmsNPAI_EmailMaxError | 在收件者被隔離之前，電子郵件通道上接受的最大軟錯誤數。 |
| NmsNPAI_EmailSignalErrorDelay | 計及新軟錯誤之前，電子郵件通道上上一個軟錯誤之後必須經過的最短時間。 |
| NmsNPAI_MobileMaxError | 在收件者被隔離之前，行動裝置頻道上接受的最大軟錯誤數。 |
| NmsNPAI_MobileSignalErrorDelay | 行動裝置頻道上一個軟錯誤之後，必須經過的最短時間，才會考慮新的軟錯誤。 |

### 管道 {#channel-options}

這些選項定義直接郵件的寄件者地址、LINE和SMS通道的設定，以及傳入電子郵件的允許轉寄地址。 深入瞭解[透過Adobe Campaign傳送直接郵件](../send/direct-mail.md)、[透過Adobe Campaign傳送直接LINE訊息](../send/line/line.md)以及[透過Adobe Campaign傳送簡訊](../send/sms/sms.md)。

| 選項 | 說明 |
|---|---|
| NmsPaper_SenderLine1， NmsPaper_SenderLine3， NmsPaper_SenderLine4， NmsPaper_SenderLine6， NmsPaper_SenderLine7 | 直接郵件傳遞的寄件者地址的第1、3、4、6和7行。 |
| NmsLine_AESKey | lineImage servlet用來編碼LINE頻道中URL的AES金鑰。 |
| NmsLine_MessageCenterURL | Message Center伺服器URL用來在LINE通道中傳送歡迎訊息。 |
| NmsSMS優先順序 | 已傳送簡訊的優先順序，已傳輸至簡訊閘道。 |
| NmsInmail_AllowlistEmails | 傳入郵件處理模組的授權轉寄電子郵件地址，以逗號分隔。 使用*以允許所有地址。 |

### 訊息中心臨界值 {#message-center-options}

這些選項會定義當處理即時事件（觸發交易式訊息）時降低而引發警告或警示的臨界值。 每個量度都有警告臨界值和警報臨界值。 選項名稱的結尾是Warning或Alert，例如MC_RtEventErrorWarning和MC_RtEventErrorAlert。 深入瞭解[行銷活動異動訊息](../send/transactional.md)與[行銷活動異動訊息設定](../config/transactional-msg-settings.md)。

| 選項名稱前置詞 | 量度 |
|---|---|
| MC_RtEventAvgDeliveryTime | 即時事件的平均傳送時間。 |
| MC_RtEventAvgProcessTime | 即時事件的平均處理時間。 |
| MC_RtEventAvgQueueTime | 即時事件的平均佇列時間。 |
| MC_RtEventAvgQueue | 已排入佇列的即時事件平均數量。 |
| MC_RtEventMaxQueue | 已排入佇列的即時事件數上限。 |
| MC_RtEventMinQueue | 已排入佇列的即時事件數下限。 |
| MC_RtEventQueue | 待處理即時事件的佇列。 警示臨界值是嚴重狀況。 |
| MC_RtEventError | 即時事件的處理錯誤。 |
| MC_RtEventThroughput | 即時事件的輸送量。 |

### 資料保留與資料庫 {#database-options}

清理工作流程會清除舊記錄，以防止資料庫成長。 這些選項會定義Campaign保留每種資料型別的時間。 當您變更介面的延遲時，會自動建立清除延遲選項。 如果您從選項清單進行編輯，請以秒為單位表示值。 深入瞭解[一般架構](general-architecture.md)和[安全性方針](../config/security.md#consent)。

只有管理員可以修改清除延遲選項。 適當的值視您的環境而定，因此請檢查您執行個體上的目前值，且不採用通用預設值。

| 選項 | 說明 |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | 拭除傳遞記錄(broadlog)之後的延遲。 |
| NmsCleanup_TrackingLogPurgeDelay | 清除追蹤記錄之後的延遲。 |
| NmsCleanup_TrackingStatPurgeDelay | 清除追蹤統計資料之後的延遲。 |
| NmsCleanup_EventPurgeDelay | 事件被拭除之後的延遲。 |
| NmsCleanup_EventHistoPurgeDelay | 拭除事件記錄的延遲。 |
| NmsCleanup_EventStatPurgeDelay | 事件統計資料被清除之後的延遲。 |
| NmsCleanup_PropositionPurgeDelay | 建議被拭除之後的延遲。 |
| NmsCleanup_QuarantineMailboxFull | 拭除隔離的延遲。 |
| NmsCleanup_RecycledDeliveryPurgeDelay | 延遲再生傳遞之後會遭到拭除。 |
| NmsCleanup_RejectsPurgeDelay | 拭除拒絕之後的延遲。 |
| NmsCleanup_VisitorPurgeDelay | 訪客被擦除之後的延遲。 |
| NmsCleanup_WorkflowResultPurgeDelay | 拭除工作流程結果之後的延遲。 |
| WdbcKillSessionPolicy | PostgreSQL上無條件停止工作流程的行為。 0 （預設）：停止工作流程處理作業，不會影響資料庫。 1：停止處理並取消查詢(pg_cancel_backend)。 2：停止處理並終止查詢(pg_terminate_backend)。 |
| XtkSequence_AutoGeneration | 套用至在設定此選項後建立的自訂結構描述，具有autopk=&quot;true&quot;且沒有pkSequence屬性：Campaign會自動產生序列。 |

### 訊息中心自訂 {#message-center-customization}

這些選項可讓您自訂Campaign如何豐富和路由即時和批次事件。 深入瞭解[行銷活動異動訊息](../send/transactional.md)與[行銷活動異動訊息設定](../config/transactional-msg-settings.md)。

| 選項 | 說明 |
|---|---|
| MC_EnrichmentCustomJs | 豐富事件的JavaScript資料庫。 它必須針對即時事件實作extenderRtEvents(aiEventId)，並為批次事件實作extenderBatchEvents(aiEventId)。 這兩個函式都會豐富事件，並將其儲存在資料庫中。 |
| MC_RoutingCustomJs | 路由事件的JavaScript資料庫。 它必須實作dispatchRtEvent(iEventId)和dispatchBatchEvent(iEventId)，這兩者會傳回為即時或批次事件選取的交易式訊息的內部名稱。 |
| NmsMessageCenter_RoutingBatchSize | 用於事件路由的群組大小。 |
| NmsTracking_RT_ClickFormula、NmsTracking_RT_OpenFormula | 品牌啟用時，用於即時(RT)傳遞的點選與開啟追蹤的公式。 它們是在RT控制例項上設定的。 [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | 包含自訂追蹤公式的選項清單（以逗號分隔），以便RT傳送可套用這些公式。 [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### 互動（優惠方案管理） {#interaction-options}

這些選項適用於優惠方案管理模組Campaign Interaction 。 它們控制如何寫入主張以及如何同步控制和執行例項。 深入瞭解[Campaign互動 — 優惠方案管理](../interaction/interaction.md)以及互動架構的[維護選項](../interaction/interaction-architecture.md#maintenance-options)。

| 選項 | 說明 |
|---|---|
| NmsInteraction_UseDaemon | 將其設為1可啟用非同步寫入主張，或設為0可停用它。 |
| NmsInteraction_MapWorkflowId | 所有產生的同步工作流程清單。 控制執行個體的資訊性維護選項：請勿修改它。 |
| NmsExecutionInstanceId | 執行例項的識別碼。 執行例項上可用的資訊選項：請勿修改它。 |

下列選項也是控制例項的維護選項：

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**：指定執行個體上同步環境的上次日期。
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**：結構描述的主張從一個執行個體同步到另一個執行個體的上次日期。

>[!CAUTION]
>
>僅針對特定維護案例使用維護選項。

下列選項適用於企業(FFDA)部署中不提供的抵用券。 進一步瞭解[個人化優惠券](../send/personalized-coupons.md)。

| 選項 | 說明 |
|---|---|
| NmsModule_CouponsEnabled | 啟用優惠券。 |
| NmsCoupons_MaxPerTransac | 每個SQL交易更新的優惠券數目。 |

### 隱私權請求 {#privacy-options}

這些選項可控制Campaign處理隱私權請求的方式，例如刪除確認、允許的錯誤數量，以及保留請求資料的時間長度。 深入瞭解[在Campaign](../start/privacy.md)管理隱私權要求。

| 選項 | 說明 |
|---|---|
| Privacy_Request_ConfirmDeletePending | 將其設為1，以在第二個步驟中在介面中手動確認每個刪除。 否則，將會刪除資料而不進行確認。 |
| Privacy_Request_ConfirmDeletePendingDelay | 延遲等候刪除確認的要求取消之後。 |
| Privacy_Request_MaxErrorAllowed | 處理或刪除隱私權請求時允許的錯誤數上限。 |
| Privacy_Request_PurgeDelay | 在佇列中建立請求與刪除其資料之間的延遲。 |
| realtimeReporting_collectPII | 選擇用於動態報告的個人識別資訊(PII)合約。 值1對應至「稍後詢問我」、2對應至「拒絕」、3對應至「接受」。 [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### 稽核軌跡 {#audit-trail-options}

稽核軌跡會記錄對行銷活動實體所做的變更。 使用這些選項可為實體啟用或停用它，例如節省資料庫空間。 將值設為1可啟用稽核軌跡，設為0可停用稽核軌跡。 深入瞭解[稽核軌跡](../reporting/audit-trail.md#enable-disable-audit-trail)。

| 選項 | 已稽核的實體 |
|---|---|
| XtkAudit_Workflows | 工作流程 |
| XtkAudit_DataSchema | 結構描述 |
| XtkAudit_Option | 選項 |
| XtkAudit_Delivery | 傳遞 |
| XtkAudit_ExtAccount | 外部帳戶 |
| XtkAudit_DeliveryMapping | 傳遞對應 |
| XtkAudit_WebApp | 網頁應用程式 |
| XtkAudit_Offer | 產品建議 |
| XtkAudit_Operator | 運算子 |
| XtkAudit_Enable_All | 所有實體 |

### 整合與調查 {#integration-options}

這些選項儲存整合與調查的設定：登陸頁面的Adobe Developer Console憑證、CRM聯結器活動的最後同步日期，以及調查答案的預裝置份。 深入瞭解[從Adobe Experience Platform登陸頁面](../connect/ac-aep-landing-pages.md)更新Adobe Campaign設定檔，[CRM Connectors資料同步處理](../connect/crm-data-sync.md)，以及[管理答案](../dev/surveys/managing-answers.md)。

| 選項 | 說明 |
|---|---|
| IMS_CLIENT_ID、IMS_CLIENT_SECRET、IMS_ORG_ID、IMS_CLIENT_API_KEY | 用於具有Adobe Experience Platform之登陸頁面的Adobe Developer Console憑證。 [了解更多](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_，後面接著執行個體的內部名稱和活動名稱 | 上次同步一般CRM聯結器活動的日期。 以文字選項手動建立，格式為`yyyy/MM/dd hh:mm:ss`。 [了解更多](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | 建立並將其設為1，依預設為所有調查儲存原始答案的副本。 [了解更多](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | 可以在Campaign中使用的Adobe Experience Manager資源型別，並以逗號分隔。 [了解更多](../connect/ac-aem.md) |
| nmsPipeline_config | 設定Adobe Experience Cloud觸發程式，JSON格式。 將其建立為長文字選項。 [了解更多](../connect/ac-triggers.md) |
| TNT_EdgeServer | 用於整合的Adobe Target伺服器，預設為設定。 這是Adobe Target網域伺服器，後面接著/m2，例如tt.omtrdc.net/m2。 [了解更多](../connect/ac-at.md) |
| TNT_TenantName | Adobe Target組織（使用者端）的名稱。 [了解更多](../connect/ac-at.md) |
| AAM_DataSourceId， AAM_DestinationId | 與Adobe Audience Manager整合所使用的識別碼。 [了解更多](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Azure Synapse (Azure SQL Data Warehouse)聯結器的選項。 [了解更多](../connect/fda.md) |

## 相關主題 {#related-topics}

* [內建套件](built-in-packages.md)
* [全域原則](general-architecture.md)
* [認證循環指南](../../technotes/security/credential-rotation-guide.md)
