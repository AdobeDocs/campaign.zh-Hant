---
title: Campaign v8 2022 發行說明
description: 2022 Campaign v8 版本隨附的功能與改進清單
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 99%

---

# 2022 發行說明{#2022-rn}

本頁面列出 **2022 Campaign v8 版本**&#x200B;附帶的新功能、改善和修正。

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

* Internet Explorer 11 生命週期結束後，主控台中的 HTML 轉譯引擎現在使用 **Microsoft Edge Chromium**。此外，安裝 **Microsoft Edge WebView 2** 任何使用者端主控台安裝現在都需要執行階段。
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
