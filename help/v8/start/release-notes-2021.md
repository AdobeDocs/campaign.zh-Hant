---
title: Campaign v8 2021 發行說明
description: 2021 Campaign v8 版本隨附的功能與改進清單
feature: Release Notes
hide: true
exl-id: 5ac6bda9-86c8-4200-b285-6fee2a29039d
TQID: https://experienceleague.adobe.com/o497R5a6OnWWHLy-QJUic5Mps5OlRGrW7JvQCQJKhC0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1644
ht-degree: 97%

---

# 2021 發行說明{#2021-release}

本頁面列出 **2021 Campaign v8 版本**&#x200B;附帶的新功能、改善和修正。

## 發行版本 8.2.8 {#release-8-2-8}

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
<p>傳入頻道現在可使用 Real-time Interaction Management。 使用 Campaign 傳入互動模組，在客戶造訪您的網站或聯絡您的呼叫中心時，向客戶呈現最佳產品建議。 此功能作為 Campaign v8 提供的選項之一，且需要您執行個體的特定設定。 請洽詢您的 Adobe 代表，以存取傳入互動模組。</p>
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
<td> <p>行銷活動最佳化模組現已可使用。 此模組可讓您控制、篩選及檢視傳遞的傳送。 為了避免行銷活動之間發生衝突，Adobe Campaign 可以套用特定限制規則來測試各種組合。 這樣可確保傳送的訊息符合客戶和公司通訊政策的需求及期望。</p>
<p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=zh-Hant#campaign-optimization">詳細文件</a>以瞭解詳情。</p>
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


**功能改進**

* Snowflake 連接器效能已改善。
* 為了監視和測試之目的， **[!UICONTROL Replicate Staging data]** 工作流程現在包含已傳送至 FFDA (完整同盟資料存取) 資料庫的記錄數。
* SQL 代碼活動現在允許您選擇 SQL 指令碼將儲存於指定資料庫中：預設資料來源或所選的主要 FDA 外部帳戶。
* 預定義的倉庫組現在已可使用，並可用於並行執行各種查詢，如細分、ETL 或峰值。 [閱讀全文](../config/workflows.md)

**其他變更**

* 此 **[!UICONTROL Encrypted identifier]** 欄位已新增至訪客結構描述 (`nms:visitor`)。 此欄位已經過計算，將用於網路應用程式。
* 修正部分中間來源容器 (非所有) 中存在某些 IP 相關性時，導致傳遞分析失敗的問題。 現在，IP 相關性都會儲存在資料庫中，因此任何容器都可以存取其他所有容器中呈現的相關性。 (NEO-37564)
* 您現在可以匯入包含多個結構和導覽樹節點的套件。

**修補程式**

* 移除使用者後，在資料結構中，`<autoStg>`表格定義元素的屬性，或將其值從 `true` 變更為 `false`，將不會刪除相關的中繼表格。 此問題已修正。
* 修正 FFDA 資料來源的 ID 管理以專用表單建立記錄時發生錯誤的問題。
* 如果產品建議是由工作流程中的擴充活動管理，修正了此情況下無法將產品建議插入至傳遞的問題。
* 修正了可能會拖慢套件匯入速度的問題。
* 修正了無法傳送含種子地址之電子郵件的問題。
* 修正了無法將建議儲存在產品建議提案表格中的問題。
* 修復在網路逾時，導致不正確記錄為指令碼中斷而非網路錯誤的問題。 如果 HTTP 要求包含在 JavaScript 活動中，會發生此問題。
* 修正無法將產品建議複製到 Snowflake 上即時產品建議環境的問題。
* 修正了忽略非擴充內建結構之「autoStg」屬性的問題。
* 修正了使用者無法選取 **[!UICONTROL Country/Region]** 預覽輪廓時的連結的問題。
* 修正了自訂報告中的日期選擇器導致指令碼錯誤的問題。 (NEO-36345)
* 修正了在重新產生設定時，如果設定檔案錯誤，會導致系統當機的問題。
* 修正了無法成功升級行銷和控制執行個體的問題。
* 修正可能導致計費工作流程在行銷執行個體中造成當機的問題。
* 修正了 FFDA Snowflake 現成可用表格中可能重複金鑰的問題。 (NEO-38583)
* 修正了在逐一編輯兩個重複資料刪除活動時，可能導致工作流程臨時結構描述遺失的問題。 (NEO-34063)
* 修正了在嘗試提取時間元件時，執行 Amazon Redshift HoursDiff 和 MinutesDiff 函式時傳回錯誤結果的問題。(NEO-31673)
* 修正了由於 Proxy 組態問題，使用者無法登入主控台的問題。 (NEO-38388)
* 修正了妨礙&#x200B;**清除資料夾**&#x200B;功能正常運作的問題。 (NEO-37459)
* 修正可能導致您無法預覽附加至工作流程的行動傳遞問題。
* 修正了&#x200B;**讀取清單** 在資料庫中以負 ID 識別清單時，工作流程活動無法運作的問題。 (NEO-39607)

## 發行版本 8.1.20 {#release-8-1-20}

_2021 年 9 月 7 日_

**安全性改善功能**

* 修正安全性問題，以針對目錄周遊攻擊加強保護。 (NEO-28547)

**功能改進**

* Flash 的生命週期結束後，已從所有相關的 Campaign 功能和元件中移除，並更換為 HTML5。 **量測**&#x200B;類型圖表已移除。 (NEO-30330) [閱讀全文](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=zh-Hant)
* 在Windows上安裝使用者端主控台時，安裝程式現在會檢查是否有父代登入節點，如果缺少該節點，則會建立一個。 這可防止啟動主控台時發生潛在問題。 (NEO-34854)
* 追蹤簽章功能已經過改良，以防止連結至第三方工具 (電子郵件用戶端、網際網路瀏覽器等) 以處理 特殊字元的錯誤。 URL 參數現在已編碼。

**其他變更**

* 先前已棄用的 Microsoft CRM 連接器 (Office 365 及內部部署) 已從介面移除。 [閱讀更多](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)

* 遷移到 Tomcat 8 後，已更新 IIS 安裝指令碼，修正了 IIS 整合問題。 (NEO-31019)
* 已新增護欄，僅允許[帳單技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=zh-Hant#billing-report)在行銷執行個體上執行。
* 已在工作流程轉變&#x200B;**檢視群體**&#x200B;視窗的資料和結構描述標籤中改善資料來源識別。
* 已將缺少的資料庫索引新增到下列結構描述中，以防止資料庫更新問題：xtk:rights、nms:dlvExclusion、nms:seedMember、nms:trackingUrl

**修補程式**

* 修正當產品建議連結至傳遞時，**熱點擊**&#x200B;報告無法運作的問題。 (NEO-26295)
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

## 發行版本 8.1.14 {#release-8-1-14}

_2021 年 7 月 23 日_

**有哪些新功能？**

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
<p>使用 Campaign v8 時，主要輪廓表格會直接儲存在雲端資料庫中。 因此，查詢輪廓表格也會在雲端資料庫上建立工作表格。 在某些情況下，將工作表格移動到其他資料來源以執行特定操作是很合理的。</p>
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
<td> <p><a href="../send/line/line.md">LINE 頻道</a>現在可與 Campaign v8 搭配使用，包括與<a href="../send/transactional.md">異動訊息</a>模組結合時的下列增強功能：
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
* 修正搭配「ID不是空白」篩選使用工作流程查詢時，可能導致轉變群體中顯示空白項目的問題。
* 修正無法在新目標對應中建立其他欄位的問題。
