---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 1f323f4b3cca3c9ff398ad5168b2817a917ef124
workflow-type: tm+mt
source-wordcount: '3820'
ht-degree: 92%

---

# 最新發行版本{#latest-release}

本頁面列出&#x200B;**最新 Campaign v8 版本**&#x200B;的新功能、改善和修正。

## 發行版本 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#download-ac-console)了解如何升級您的用戶端主控台。

_2023年1月27日_

**功能改進**

* 修正行銷伺服器與中間來源伺服器之間的傳送指標同步問題。 (NEO-50724) <!--OKKKK-->
* 修正匯出工作流程時可能導致錯誤的問題。 (NEO-50555) <!--OKKKK-->
* 修正擴充先前已擴充之架構時的問題。 (NEO-49118) <!--OKKKK-->
* 修正在連結定義中使用具有相同識別碼的兩個擴充活動時的問題。 (NEO-48851)
* 修正了兩個傳送準備失敗問題。 當操作的潛在選件數量太多時，傳送準備可能會失敗。 第二個問題是將影像URL定義為要在文字格式傳送中追蹤的URL時。 (NEO-48807) <!--OKKKK-->
* 修正了可能導致工作流程失敗的問題，亦即工作流程會覆寫非FFDA帳戶外部帳戶中定義的倉儲名稱。 (NEO-43209) <!--OKKKK-->
* 改善Web應用程式的安全性，以防止DDoS攻擊。 (NEO-50757) <!--OKKKK-->
* 已改善 **[!UICONTROL Consolidated tracking]** (nms:trackingStats)FFDA表格以避免重複。 (NEO-46409)
* 修正使用 `enableIf` 在邏輯運算子條件中。 已覆寫先前的邏輯條件。 (NEO-45815)  <!--OKKKK-->
* 帳單工作流程中已最佳化作用中設定檔的產生，以改善效能。 (NEO-47658) <!--OKKKK-->
* 修正當影像節點 (img) 包含具有個人化欄位的 URL 時，HTML 檔案匯入的問題。 (NEO-48396)
* 修正使用排序參數(位於 **分割** 工作流程活動。 (NEO-45899) <!--OKKKK-->
* 修正了當 nmsDeliveryMapping 資料夾上具有讀取存取權限的使用者嘗試執行行銷活動或工作流程時，導致錯誤的問題。 (NEO-48230)
* 修正傳送 HTML 標籤中，大型 HTML 程式碼可能發生的效能問題。 (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修正使用者無法使用 **合併所選行** 工作流程選項。 (NEO-48488)
* 修正了在SnowflakeFDA連接器上，在擴充期間使用「0或1基數簡單加入」選項時，會捨棄記錄的問題。 (NEO-48737)
* 對 log4j 程式庫的其餘參考已從 Windows 上安裝的 Campaign 中移除。 (NEO-44851)
* 修正在&#x200B;**查詢** 工作流程活動的其他資料中新增&#x200B;**已開啟的收件者**  (estimatedRecipientOpen) 指標導致錯誤的問題。(NEO-46665)
* 透過多次傳送來改善工作流程中追蹤URL的管理，以提升效能。 (NEO-50894) <!--OKKKK-->
* 修正了可能導致使用Xtkfolder的結構復寫失敗的問題。 (NEO-46787) <!--OKKKK-->
* 修正了導致「lastModified」自訂欄被拖放到NmsSubscription表格的問題。 (NEO-48402)

## 發行版本 8.4.2 {#release-8-4-2}

_2022 年 10 月 28 日_

**功能改進**

* 當使用 Adobe Campaign Enhanced MTA 時，成功傳送指標無法正確更新，該問題已修正。 (NEO-50462)

## 發行版本 8.4.1 {#release-8-4-1}

_2022 年 9 月 30 日_

**有哪些新功能？**

<table> 
<thead>
<tr> 
<th> <strong>Adobe Campaign 與 Adobe Experience Platform 整合</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>現在提供新的目標和來源連接器，可緊密整合 Adobe Campaign 和 Adobe Experience Platform：</p>
<ul><li>使用 Adobe Campaign Managed Cloud Services 目標連接器將 Experience Platform 區段傳送至 Adobe Campaign 以進行啟用，</li>
<li>使用 Adobe Campaign Managed Cloud Services 來源連接器將 Adobe Campaign 傳送和追蹤記錄傳送至 Adobe Experience Platform。</li>
</ul>
<p>如需詳細資訊，請參閱<a href="../connect/ac-aep.md">詳細文件</a>以瞭解詳情。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Twitter 頻道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>此 <a href="../send/twitter.md">Twitter 社交頻道</a> 現在可搭配 Campaign v8 使用。 您可以：</p>
<ul> 
<li><p>透過 Twitter 傳送訊息：Adobe Campaign 可讓您直接將訊息張貼至您的 twitter 帳戶。 您也可以傳送直接訊息給所有追隨者。
</p></li>
<li><p>收集新聯絡人：Adobe Campaign 可以自動復原設定檔資料，讓您執行目標定位行銷活動並實施跨管道策略。
</p></li>
</ul>
<p>在<a href="../connect/ac-tw.md">詳細文件</a>中瞭解如何連結 Campaign 和 Twitter。</p>
<p>在<a href="../connect/ac-tw.md">本頁</a>中瞭解如何發佈推文 (twitter) 及傳送訊息。</p>
</td> 
</tr> 
</tbody> 
</table>

**安全性增強功能**

為了最佳化安全性，已從 Campaign 產生的 URL 中移除安全性權杖：

* 此變更僅適用於 GET URL。 其他類型 (包括 POST URL) 則不受影響。
* 如果您使用自訂程式碼，則安全性權杖不再從 GET URL 安全性權杖參數中擷取。 您必須使用下列 JSSP 程式碼產生新的安全性權杖：

   ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

   您也可以使用登入 API 來擷取安全性權杖。
* 工作階段權杖管理中沒有變更。

**功能改進**

* Internet Explorer 11 生命週期結束後，主控台中的 HTML 轉譯引擎現在使用 **Microsoft Edge Chromium**。此外，**Microsoft Edge WebView 2** 的安裝現在在任何用戶端主控台安裝都需要執行階段。
* 改善工作流程高可用性的工作流程執行，可讓您跨不同容器同時執行工作流程，以防止工作流程服務遺失，並避免相關的執行錯誤。 **備註**：這項新功能僅在有限可用性的情況下發行給一組客戶。
* 隱私權請求現在會針對指定的隱私權命名空間以批次執行。 此項改善可增加 GDPR /隱私權刪除請求的執行時間。

**相容性更新**

* Campaign v8 SDK 現在支援 iOS16 的推播通知。

請參閱 [Campaign 相容性對照表](compatibility-matrix.md)。

**修補程式**

* 修正啟用 FeatureFlag_GZIP_Compression 選項時，影響 MID 執行個體上傳送記錄狀態更新的問題。 (NEO-49183)
* 修正了可能導致傳遞持續存在&#x200B;**待定**&#x200B;狀態的問題，即使已達到聯絡日期亦然。 (NEO-48079)
* 修正工作流程中，使用&#x200B;**資料載入 (檔案)** 活動可能阻止檔案更新的問題。 流程 100% 停止，但從未結束。 (NEO-47269)
* 修正日文環境升級後期間的問題。 (NEO-46640)
* 修正了在 MTA 流程期間，如果傳送達到精確大小時可能發生的問題。 (NEO-46097)
* 修正追蹤記錄無法傳回與收件者瀏覽器相關資料的問題。 (NEO-46612)
* 修正使用外部傳送模式傳送 SMS 訊息時，導致個人化問題的問題。 (NEO-46415)
* 修正了在追蹤記錄中可能產生重複項目的問題。 (NEO-46409)
* 修正即使在執行期間發生錯誤，仍然阻止 **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) 技術工作流程停止的問題。 (NEO-46280)
* 為了防止向種子地址傳送證明時速度變慢，現在種子成員的所有連續複製都分組到一個複製請求中。 (NEO-44844)
* 修正嘗試在任何「訊息中心」封存事件中預覽傳遞時，顯示錯誤的問題。 (NEO-43620)
* 修正使用 Campaign 將資料插入 Snowflake 雲端資料庫的問題&#x200B;**查詢**&#x200B;活動與&#x200B;**變更資料來源**&#x200B;活動：資料中出現反斜線字元時，流程會失敗。 來源字串未逸出，且資料在 Snowflake 時未正確處理。 (NEO-45549)
* 修正使用&#x200B;**查詢**&#x200B;活動和篩選表格時的問題。 當欄名稱包含「更新」一詞時，出現編譯錯誤，且識別碼無效，並出現以下訊息：「更新的列數」。(NEO-46485)
* 此 **資料庫清理** 技術工作流程現在也可處理自訂的準備結構。 (NEO-48974)
* 修正在排除已列入封鎖名單的收件者步驟期間，鎖定大量收件者時，可能會拖慢傳送分析的速度的問題。 (NEO-48019)
* 改善在 SOAP 呼叫期間處理無效 XML 字串時的穩定性。 (NEO-48027)
* 修正了當傳送使用日曆和分割模式時，導致建立不必要 DeliveryPart 的問題。 (NEO-48634)
* 修正使用日曆波段時的效能問題。 (NEO-48451)
* 修正在自訂架構上建立新目標對應後，傳送清單畫面中可能顯示錯誤訊息的問題。 (NEO-49237)
* 修正了在測試工作流程錯誤且保留期已完全通過時，可能導致資料遺失的問題。 (NEO-48975)

## 發行版本 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#download-ac-console)了解如何升級您的用戶端主控台。

_2022 年 10 月 7 日_

**功能改進**

* 修正啟用 FeatureFlag_GZIP_Compression 選項時，影響 MID 執行個體上傳送記錄狀態更新的問題。 (NEO-49183)
* 此 **資料庫清理** 技術工作流程現在也可處理自訂的準備結構。 (NEO-48974)
* 修正了可能導致傳遞持續存在&#x200B;**待定**&#x200B;狀態的問題，即使已達到聯絡日期亦然。 (NEO-48079、NEO-48251)
* 改善在 SOAP 呼叫期間處理無效 XML 字串時的穩定性。 (NEO-48027)
* 修正在排除已列入封鎖名單的收件者步驟期間，鎖定大量收件者時，可能會拖慢傳送分析的速度的問題。 (NEO-48019)
* 為了防止向種子地址傳送證明時速度變慢，現在種子成員的所有連續複製都分組到一個複製請求中。 (NEO-44844)
* 修正使用外部傳送模式傳送 SMS 訊息時，導致個人化問題的問題。 (NEO-46415)
* 修正嘗試在任何「訊息中心」封存事件中預覽傳遞時，顯示錯誤的問題。 (NEO-43620)
* 修正工作流程中，使用&#x200B;**資料載入 (檔案)** 活動可能阻止檔案更新的問題。 流程 100% 停止，但從未結束。 (NEO-47269)
* 修正了當傳送使用日曆和分割模式時，導致建立不必要 DeliveryPart 的問題。 (NEO-48634)
* 修正使用日曆波段時的效能問題。 (NEO-48451)
* 修正在自訂架構上建立新目標對應後，傳送清單畫面中可能顯示錯誤訊息的問題。 (NEO-49237)
* 修正了在 MTA 流程期間，如果傳送達到精確大小時可能發生的問題。 (NEO-46097)
* 修正追蹤記錄無法傳回與收件者瀏覽器相關資料的問題。 (NEO-46612)
* 修正日文環境升級後期間的問題。 (NEO-46640)
* 修正使用&#x200B;**查詢**&#x200B;活動和篩選表格時的問題。 當欄名稱包含「更新」一詞時，出現編譯錯誤，且識別碼無效，並出現以下訊息：「更新的列數」。(NEO-46485)
* 修正即使在執行期間發生錯誤，仍然阻止 **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) 技術工作流程停止的問題。 (NEO-46280)
* 修正了在測試工作流程錯誤且保留期已完全通過時，可能導致資料遺失的問題。 (NEO-48975)
* 修正使用 Campaign 將資料插入 Snowflake 雲端資料庫的問題&#x200B;**查詢**&#x200B;活動與&#x200B;**變更資料來源**&#x200B;活動：資料中出現反斜線字元時，流程會失敗。 來源字串未逸出，且資料在 Snowflake 時未正確處理。 (NEO-45549)

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
<td> <p>在 iOS15 ，Apple 增加了具時效性通知的概念，當通知被視為具時效性，需要即時聯絡使用者時，可以讓應用程式開發人員繞過專注模式。</p>
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
<p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?html?lang=zh-Hant#campaign-optimization">詳細文件</a>以瞭解詳情。</p>
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

* 先前已棄用的 Microsoft CRM 連接器 (Office 365 及內部部署) 已從介面移除。 [顯示全文](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=zh-Hant#configure-acc-for-microsoft)
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
