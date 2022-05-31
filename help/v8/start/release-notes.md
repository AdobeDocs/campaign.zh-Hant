---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: ht
source-wordcount: '2161'
ht-degree: 100%

---

# 最新發行版本{#latest-release}

本頁面列出&#x200B;**最新 Campaign v8 版本**&#x200B;的新功能、改善和修正。

## 發行版本 8.3.8 {#release-8-3-8}

_2022 年 5 月 18 日_

**有哪些新功能？**


<table> 
<thead>
<tr> 
<th> <strong>有時效性的通知</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>在 iOS15 ，Apple 增加了敏感性通知的概念，當通知被視為敏感，需要即時聯絡使用者時，可以讓應用程式開發人員繞過專注模式。</p>
<p>如需詳細資訊，請參閱<a href="../send/push.md#send-notifications-on-ios">詳細文件</a>以瞭解詳情。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>核心隱私權服務整合</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 現在與 Adobe 隱私權核心服務整合。 從「隱私權核心服務」推播至所有 Experience Cloud 解決方案的隱私權要求，會由 Campaign 透過專用的工作流程自動處理。</p>
<p>如需詳細資訊，請參閱<a href="privacy.md">詳細文件</a>以瞭解詳情。</p>
</td> 
</tr> 
</tbody> 
</table>


<table>
<thead>
<tr>
<th><strong>回應管理員</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Campaign 回應管理允許您評估行銷活動的成功和 ROI，或提供跨各種管道的優惠方案：電子郵件、手機、直接郵件等。</p>
<p>如需詳細資訊，請參閱<a href="../start/campaigns.md#response-manager-add-on">詳細文件</a>以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>分散式行銷</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign 分散式行銷使您能夠在中心實體 (總部、行銷部門、等) 之間實施協作行銷活動 。本地實體 (銷售地點、地區代理等)。 透過共用工作區域 (促銷活動套件)，您可以建立促銷活動範本並將其建議給本地實體。 </p>
<p>如需詳細資訊，請參閱<a href="../start/campaigns.md#distributed-marketing-add-on">詳細文件</a>以瞭解詳情。</p>
</td> 
</tr> 
</tbody> 
</table>

**相容性更新**

* Campaign v8 SDK 現在支援 Android 12 和 iOS15 的推播通知。
* Campaign v8 現在與 Windows 11相容。

請參閱 [Campaign 相容性對照表](compatibility-matrix.md)。

**功能改進**

* Microsoft Exchange Online OAuth 2.0 在 Campaign 中支援 POP3 驗證。 [閱讀全文](../config/external-accounts.md#bounce-mails-external-account)
* 已套用 Microsoft Dynamics 連接器網頁 API 的重要修正：
* 已新增名稱為權限的新運算元和群組方案寫入 (operatorWrite)，以允許使用者插入、更新和刪除運算子 (xtk:operator) 和運算子組 (xtk:group) 方案。

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* 現在，可以在單個中間來源設定多個 LINE 主要帳戶。
* Web 流程的預設連接數已從 50 增加到 150。 
* Campaign 隨附一組新的護欄，以防止在 Snowflake 資料庫中插入重複的金鑰。 [閱讀全文](../architecture/keys.md)

**修補程式**

* 修復了使用種子和控制群組定期傳送時發生的問題。(NEO-41197)
* 修正 FFDA 上的一個問題，即當個人化區塊包含以下字元之一時，在傳送過程中 (最多256)，屬於同一個 deliveryPart 的電子郵件傳送被封鎖： `' & < > "`。 個人化區塊現在支援這些字元 (例如：firstname=&quot;Brian O&#39;Neil&quot;)。 (NEO-43184)
* 修復了使用自訂方案作為目標對應時可能導致追蹤工作流程失敗的問題。 現在，我們透過目標對應精靈產生 broadLog 方案時，確保自訂目標方案的外部連結的類型正確。 (NEO-43506)
* 修復了一個問題，該問題可能導致 FFDA 部署工作流程對於英文以外的語言失敗。 (NEO-44561)

## 發行版本 8.2.10 {#release-8-2-10}

_2022 年 2 月 2 日_

**修補程式**

* 修復在達到類型規則定義的最大訊息數時導致傳遞準備失敗的問題。
* 修復在設定 Adobe Analytics 連接器期間，當電子郵件地址包含「s」字元時發生的問題。
* 修復在升級後可能導致 deliveryMapping 表格遺失客製化傳遞對應中的資料的問題。
* 修復當電子郵件地址包含單引號字元 (&#39;) 時，可能導致收件者多次接收相同傳遞的同一郵件的問題。 此字元現已逸出。 (NEO-41198)
* 修復產生 ID 的問題，發生於傳送包含種子或替代地址的校樣時。 (NEO-42637)
* 修復可能會阻止您使用地址替代方法傳送校樣的問題。 (NEO-40417)
* 修復導致無法安裝 LINE 套件的問題。 (NEO-42503)

## 第 8.2.8 發行版本 {#release-8-2-8}

_2021 年 10 月 28 日_

<table>
<thead>
<tr>
<th><strong>傳入互動</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>傳入頻道現在可使用 Real-time Interaction Management。 使用 Campaign 傳入互動模組，在客戶造訪您的網站或聯絡您的呼叫中心時，向客戶呈現最佳優惠。 此功能作為 Campaign v8 提供的選項之一，且需要您執行個體的特定設定。 請洽詢您的 Adobe 代表，以存取傳入互動模組。</p>
<p>如需詳細資訊，請參閱<a href="../interaction/interaction-architecture.md">詳細文件</a>以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>行銷活動最佳化</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>行銷活動最佳化模組現已可使用。 此模組可讓您控制、篩選及檢視傳遞的傳送。 為了避免行銷活動之間發生衝突，Adobe Campaign 可以套用特定限制規則來測試各種組合。這樣可確保傳送的訊息符合客戶和公司通訊政策的需求及期望。</p>
<p>如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=zh-Hant">Campaign Classic v7 文件</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service 是新的 Cloud Database Manager 元件。 它可協助使用者保留及監視雲端資料庫表格中唯一關鍵值限制的完整性。 這可讓您降低插入重複金鑰的風險。
<p>由於雲資料庫不強制執行 unicity 限制，Unicity Service 在應用程式層級引入 <b>新的護欄組</b> 以減少使用 Adobe Campaign 管理資料時插入重複項目的風險。</p> 
<p>Unicity Service 啟動新的內建工作流程，稱為 <b>ffdaUnicity</b> 以監視單向性限制，並在偵測到重複項目時發出警報。</p>
<p>如需詳細資訊，請參閱<a href="../architecture/keys.md">詳細文件</a>以瞭解詳情。</p>
</td> </tr> 
</tbody> 
</table>

<!--
<table> 
<thead>
<tr> 
<th> <strong>Twitter channel availability</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The <a href="../send/twitter.md">Twitter social channel</a> is now available with Campaign v8. You can:</p>
<ul> 
<li><p>Send messages on Twitter: Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.
</p></li>
<li><p>Collect new contacts: Adobe Campaign can automatically recovers the profile data, which enables you to carry out targeting campaigns and implement cross-channel strategies.
</p></li>
</ul>
<p>Learn how to connect Campaign and Twitter in the <a href="../connect/ac-tw.md">detailed documentation</a>.</p>
<p>Learn how to post tweets and send direct messages with Campaign in <a href="../connect/ac-tw.md">this page</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**功能改善**

* Snowflake 連接器效能已改善。
* 為了監視和測試之目的， **[!UICONTROL Replicate Staging data]** 工作流程現在包含已傳送至 FFDA (完整同盟資料存取) 資料庫的記錄數。
* SQL 代碼活動現在允許您選擇 SQL 指令碼將儲存於指定資料庫中：預設資料來源或所選的主要 FDA 外部帳戶。
* 預定義的倉庫組現在已可使用，並可用於並行執行各種查詢，如細分、ETL 或峰值。 [閱讀全文](../config/workflows.md)

**其他變更**

* 此 **[!UICONTROL Encrypted identifier]** 欄位已新增至訪客方案 (`nms:visitor`)。 此欄位已經過計算，將用於網路應用程式。
* 修正部分中間來源容器 (非所有) 中存在某些 IP 相關性時，導致傳遞分析失敗的問題。 現在，IP 相關性都會儲存在資料庫中，因此任何容器都可以存取其他所有容器中呈現的相關性。 (NEO-37564)
* 您現在可以匯入包含多個結構和導覽樹節點的套件。

**修補程式**

* 移除使用者後，在資料結構中，`<autoStg>`表格定義元素的屬性，或將其值從 `true` 變更為 `false`，將不會刪除相關的中繼表格。此問題已修正。
* 修正 FFDA 資料來源的 ID 管理以專用表單建立記錄時發生錯誤的問題。
* 如果優惠是由工作流程中的擴充活動管理，修正了此情況下無法將優惠插入至傳遞的問題。
* 修正了可能會拖慢套件匯入速度的問題。
* 修正了無法傳送含種子地址之電子郵件的問題。
* 修正了無法將建議儲存在優惠提案表格中的問題。
* 修正了導致網路逾時問題錯誤記錄為指令碼中斷問題，而非網路錯誤的問題。 在 JavaScript 活動中包含的 HTTP 要求中，會發生此問題。
* 修正無法將優惠複製到 Snowflake 上即時優惠環境的問題。
* 修正了忽略非擴充內建結構之「autoStg」屬性的問題。
* 修正了使用者無法選取 **[!UICONTROL Country/Region]** 預覽設定檔時的連結的問題。
* 修正了自訂報告中的日期選擇器導致指令碼錯誤的問題。 (NEO-36345)
* 修正了在重新產生設定時，如果設定檔案錯誤，會導致系統當機的問題。
* 修正了無法成功升級行銷和控制執行個體的問題。
* 修正了行銷執行個體上，計費工作流程可能當機的問題。
* 修正了 FFDA Snowflake 現成可用表格中可能重複金鑰的問題。 (NEO-38583)
* 修正了在逐一編輯兩個重複資料刪除活動時，可能導致工作流程臨時方案遺失的問題。 (NEO-34063)
* 修正了在嘗試提取時間元件時，執行 Amazon Redshift HoursDiff 和 MinutesDiff 函式時傳回錯誤結果的問題。(NEO-31673)
* 修正了由於 Proxy 組態問題，使用者無法登入主控台的問題。 (NEO-38388)
* 修正了妨礙&#x200B;**清除資料夾**&#x200B;功能正常運作的問題。 (NEO-37459)
* 修正了無法預覽附加至工作流程的行動傳遞問題。
* 修正了&#x200B;**讀取清單** 在資料庫中以負 ID 識別清單時，工作流程活動無法運作的問題。 (NEO-39607)

## 第 8.1.20 發行版本 {#release-8-1-20}

_2021 年 9 月 7 日_

**安全性改善功能**

* 修正安全性問題，針對路徑周遊攻擊加強保護。 (NEO-28547)

**功能改善**

* Flash 的生命週期結束後，已從所有相關的 Campaign 功能和元件中移除，並更換為 HTML5。 **量測**&#x200B;類型圖表已移除。 (NEO-30330) [了解詳情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=zh-Hant)
* 在 Windows 上安裝客戶端控制台時，安裝程式現在會檢查是否有父代登錄節點，如果沒有，會建立一個。 這可防止啟動主控台時發生潛在問題。 (NEO-34854)
* 追蹤簽章功能已經過改良，以防止連結至協力廠商工具 (電子郵件用戶端、網際網路瀏覽器等) 的錯誤 處理特殊字元。 URL 參數現在已編碼。

**其他變更**

* 先前已棄用的 Microsoft CRM 連接器 (Office 365 和內部部署) 已從介面中移除。 [顯示全文](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=zh-Hant#configure-acc-for-microsoft)
* 遷移到 Tomcat 8 後，已更新 IIS 安裝指令碼，修正了 IIS 整合問題。 (NEO-31019)
* 已新增護欄，僅允許[帳單技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=zh-Hant#billing-report)在行銷執行個體上執行。
* 已在工作流程轉變&#x200B;**檢視母體**&#x200B;視窗的資料和架構標籤中改善資料來源識別。
* 已將缺少的資料庫索引添加到以下架構中，以防止出現資料庫更新問題：xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**修補程式**

* 修正當優惠連結至傳遞時，**熱點擊**&#x200B;報告無法運作的問題。 (NEO-26295)
* 修正&#x200B;**子工作流程**&#x200B;活動執行未產生輸出表格時的問題。 (NEO-36242)
* 修正將&#x200B;**描述性分析**&#x200B;報表匯出為 PDF 時的各種問題。 (NEO-25847)
* 修正使用外部郵件傳遞時，可能導致傳遞失敗的問題。 (NEO-37435)
* 修正使用 Web API 連線至 Microsoft CRM 時的錯誤。 由於功能未受影響，因此已移除錯誤訊息。
* 修正當中繼伺服器設為追蹤和行銷伺服器之間的轉送時，追蹤記錄重複資料刪除的問題。 (NEO-36285)
* 修正無法將保存庫用作特定代碼儲存區的迴歸。
* 修正當傳入轉變來自 FDA 資料來源時，無法在&#x200B;**擴充**&#x200B;工作流程活動中使用變數的問題。
* 修正 FFDA 無法正確復寫運算子群組和權限的問題。
* 修正可能導致透過傳遞傳送錯誤取消訂閱連結的問題。
* 修正復寫管理中影響升級後期間的問題。
* 修正無法顯示&#x200B;**熱點擊**&#x200B;的問題。
* 修正可能導致電子郵件訊息中 URL 損毀的問題。

## 第 8.1.14 發行版本 {#release-8-1-14}

_2021 年 7 月 23 日_

**有哪些新增功能？**

<table>
<thead>
<tr>
<th><strong>新工作流程活動：變更資料來源</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的<b>變更資料來源</b>工作流程活動可讓您變更工作流程工作表格的資料來源。 這為管理不同資料來源 (FDA、FFDA &amp; 本機資料庫) 的資料提供更強大的彈性。</p>
<p>在 Adobe Campaign 工作流程中，使用工作 (或暫時) 表格來管理資料。 工作流程執行時，工作表格會在各工作流程活動中共用資料。 在預設情況下，工作表格與我們查詢的資料來源建立在同一資料庫上。</p>
<p>使用 Campaign v8 時，主要設定檔表格會直接儲存在雲端資料庫中。 因此，查詢設定檔表格也會在雲端資料庫上建立工作表格。 在某些情況下，將工作表格移動到其他資料來源以執行特定操作是很合理的。</p>
<p>如需詳細資訊，請參閱<a href="../config/workflows.md#change-data-source-activity">詳細文件</a>，以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE 頻道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/line.md">LINE 頻道</a>現在可與 Campaign v8 搭配使用，包括與<a href="../send/transactional.md">異動訊息</a>模組結合時的下列增強功能：
<ul> 
<li><p>修正無法在 LINE 傳遞中鎖定訪客的問題。 
</p></li>
<li><p>修正從執行實例擷取訪客至行銷執行個體時，可能會導致錯誤的問題。
</p></li>
<li><p>修正處理即時事件期間的問題。</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**其他改善項目**

* 修正了無法針對特定傳遞顯示&#x200B;**熱點點選**&#x200B;報告的問題。
* 修正&#x200B;**重複資料刪除**&#x200B;工作流程活動可能導致錯誤重複計數的問題。
* 修正搭配「ID不是空白」篩選使用工作流程查詢時，可能導致轉變母體中顯示空白項目的問題。
* 修正無法在新目標對應中建立其他欄位的問題。
